# CLAUDE.md — ChatJPT

Guide pour travailler dans ce dépôt. ChatJPT est une interface de chat IA multi-modèles **entièrement contenue dans un seul fichier HTML** : [ChatJPT_1_1_1.html](ChatJPT_1_1_1.html) (~6300 lignes). Aucun build, aucun serveur, aucune dépendance npm — on ouvre le fichier directement dans un navigateur.

Auteur : Jean-Philippe Theriault (https://www.devjpt.com/). Licence CC BY-ND 4.0 (modification/redistribution de versions modifiées interdites — voir [LICENSE](LICENSE)).

## Architecture du fichier unique

Tout vit dans `ChatJPT_1_1_1.html`, dans cet ordre :

| Zone | Lignes (approx.) | Contenu |
|------|------------------|---------|
| En-tête + `<style>` | 1–1665 | Variables CSS (`:root`), thème clair (`[data-theme="light"]`), tout le CSS |
| Dépendances CDN | 1668–1676 | DOMPurify, pdf.js, highlight.js (chargés depuis cdnjs) |
| `<body>` (markup) | 1678–1883 | Structure de l'UI (panneau config à gauche, zone chat à droite) |
| `<script>` principal | 1884–fin | Toute la logique applicative |

Le script suit ce découpage logique :
- **Refs DOM + état global** (~1894–1950) : `$()` helper, `currentMode`, `conversationHistory`, `uploadedFiles`, `isProcessing`, `currentAbortController`, `currentLang`.
- **`I18N`** (~1952) : toutes les chaînes FR/EN.
- **Tables de config** (~2188–2380) : `MODELS`, `IMAGE_MODELS`, `VIDEO_MODELS`, `VIDEO_DURATIONS`, `THINKING_SUPPORT`, `RESPONSES_API_MODELS`, `THINKING_BUDGETS`, `THINKING_LEVELS`, `GEMINI3_MODELS`, `CHART_SYSTEM_INSTRUCTION`, `SYSTEM_PROMPTS`.
- **Helpers, rendu, appels API, charts** : voir la carte des fonctions ci-dessous.

## Conventions

- **Vanilla JS pur**, pas de framework. IIFE-free, fonctions globales dans un seul `<script>`. Accès DOM via le helper `$(id)`.
- **Bilingue partout** : toute chaîne visible passe par `I18N[currentLang]` (`fr`/`en`) ou par des objets `{ fr, en }`. Ne jamais coder une chaîne UI en dur sans entrée I18N correspondante.
- **CSS par variables** : utiliser les variables `--xxx` de `:root`. Les couleurs par fournisseur sont `--openai`, `--claude`, `--gemini`. Le thème clair surcharge dans `[data-theme="light"]`.
- **Persistance via `localStorage`** (voir clés ci-dessous). Aucune donnée n'est envoyée à l'auteur ; les appels vont directement aux API des fournisseurs depuis le navigateur.
- **Sécurité du rendu** : les réponses IA passent par `formatResponse()` puis sont assainies avec **DOMPurify**. Conserver l'assainissement pour tout nouveau HTML injecté.

## Modèle de données / fournisseurs

Fournisseurs : `openai`, `claude` (Anthropic), `gemini` (Google), `deepseek` + `qwen` (compatibles OpenAI). Quatre modes : `chat`, `code`, `image`, `video`. Les capacités sont **pilotées par les tables** : `updateProviderUI` active l'onglet Image/Vidéo selon la présence du fournisseur dans `IMAGE_MODELS` / `VIDEO_MODELS`. Donc : OpenAI/Gemini = image+vidéo ; **Qwen = chat + image** (pas de vidéo) ; Claude/DeepSeek = texte seul.

Endpoints appelés directement depuis le navigateur :
- OpenAI : `https://api.openai.com/v1/chat/completions`, `/v1/responses` (modèles `RESPONSES_API_MODELS`), `/v1/images/generations`, `/v1/videos`.
- Anthropic : `https://api.anthropic.com/v1/messages` — nécessite les en-têtes `anthropic-version: 2023-06-01` **et** `anthropic-dangerous-direct-browser-access: true`.
- Gemini : `https://generativelanguage.googleapis.com/v1beta/...` (clé passée en query param `?key=`).
- DeepSeek / Qwen (compatibles OpenAI) : endpoint **résolu à l'exécution** par `OPENAI_COMPATIBLE_ENDPOINTS[provider]()` (valeurs = fonctions), appelé par `callOpenAICompatibleStream(endpoint, ...)`. Qwen a 2 régions DashScope (`QWEN_REGIONS` : intl/mainland) ; le choix utilisateur est dans `ai_qwen_region` et le sélecteur n'apparaît que pour Qwen.

`formatHistory()` + `HISTORY_STRATEGIES` convertissent `conversationHistory` au format propre à chaque fournisseur. Le streaming a une fonction par fournisseur : `callOpenAIStream`, `callOpenAICompatibleStream` (DeepSeek/Qwen…), `callOpenAIResponsesStream`, `callClaudeStream`, `callGeminiStream`, toutes consommées par `readStream()`.

**Ajouter un fournisseur compatible OpenAI** (même format Chat Completions + SSE, ex. Qwen) : ① champ de clé dans le markup + `<option>` ; ② `keyInputs` + `PROVIDER_PILLS` ; ③ tableau dans `MODELS` ; ④ alias `HISTORY_STRATEGIES.<p> = HISTORY_STRATEGIES.openai` ; ⑤ `THINKING_SUPPORT.<p>` (modèles à `reasoning_content` → `native`) ; ⑥ une ligne dans `OPENAI_COMPATIBLE_ENDPOINTS` (le routage et le stream sont déjà génériques) ; ⑦ `updateProviderUI` (texte seul → brancher avec `claude`) ; ⑧ couleur CSS `--<p>` + `.provider-indicator`/`.model-badge`/`.label`. ⚠️ Ne PAS envoyer `reasoning_effort` (propre à OpenAI).

## Clés localStorage

- `ai_key_<provider>` — clé API **chiffrée** (AES-GCM via `CryptoKeys`, préfixe `enc:`). Les anciennes clés en clair sont migrées au chargement.
- `ai_crypto_salt` — sel PBKDF2 (la passphrase dérive de `location.origin` + `navigator.userAgent`).
- `ai_provider`, `ai_model`, `ai_agent_mode`, `ai_theme`, `chatjpt_lang`.
- `ai_thinking_enabled`, `ai_thinking_budget`, `ai_thinking_level`.
- `ai_image_quality`, `ai_image_size` (OpenAI), `ai_image_format`, `ai_image_resolution` (Gemini).
- `ai_qwen_region` — région DashScope pour Qwen (`intl` | `mainland`, défaut `intl`).
- `ai_qwen_image_size` — taille image Qwen (ex. `1024*1024`, format `largeur*hauteur`).
- Historique de conversation (persisté par `saveHistory()`, qui **retire les images** ; repli `_pruneAndRetrySaveHistory()` si quota dépassé).

## Carte des fonctions clés

- **Entrée** : `init()` (bootstrap), `setupEventListeners()`, `handleSend()`, `handleRegenerate()`.
- **Génération** : `handleTextGeneration()`, `handleImageGeneration()` → `generateImageOpenAI`/`generateImageGemini`, `handleVideoGeneration()`.
- **Thinking** : `getThinkingSupport()`, `updateThinkingUI()`, `populateThinkingBudget()`, `initThinking()`.
- **Rendu** : `addMessage()`, `updateMessageContent()`, `formatResponse()` (markdown→HTML + DOMPurify), `buildCodeBlock()`, `highlightCode()`, `parseMarkdownTable()`, `attachRatingButtons()` (👍/👎), `maybeShowCoffeeNudge()`.
- **Charts** (moteur de rendu canvas maison) : `parseChartConfig()`, `renderAllCharts()`, `renderChart()` + `renderBarChart`/`LineChart`/`PieChart`/`Histogram`/`ScatterPlot`/`BoxPlot`/`Treemap`/`Pictograph`/`Heatmap`. Les modèles génèrent des blocs ` ```chart ` (voir `CHART_SYSTEM_INSTRUCTION`).
- **Export / fichiers** : `exportHistory(likedOnly)`, `exportPDF()`, `downloadFile()`, `handleFiles()` + `extractPdfText()` (pdf.js).
- **Robustesse** : `fetchWithRetry()`, `translateApiError()`, `showVideoError()`.

## Recettes courantes

**Ajouter un modèle** : ajouter une entrée `{ id, name: { fr, en } }` dans `MODELS`/`IMAGE_MODELS`/`VIDEO_MODELS`. Si le modèle supporte le thinking, l'inscrire dans `THINKING_SUPPORT[provider].native` ou `.configurable`. Modèle OpenAI nécessitant l'API Responses → l'ajouter à `RESPONSES_API_MODELS`. Modèle Gemini 3 → l'ajouter à `GEMINI3_MODELS` (utilise `thinkingLevel` au lieu de `thinkingBudget`).

**Durées vidéo** : `VIDEO_DURATIONS` est spécifique au fournisseur — Sora accepte `8/12/16/20`, Veo `8/6/4`. Des valeurs croisées sont **rejetées par l'API** (régression déjà corrigée en 1.1.1).

**Texte UI** : ajouter la clé dans `I18N.fr` ET `I18N.en`.

## Tester / lancer

Pas de toolchain. Ouvrir `ChatJPT_1_1_1.html` dans un navigateur moderne (Chrome/Firefox/Edge/Safari récents) et tester manuellement avec une vraie clé API. Vérifier les changements dans **les deux langues** et **les deux thèmes**.

## Versioning

- Le numéro de version apparaît à **4 endroits** : commentaire d'en-tête HTML, `<title>`/en-tête visible, pied de page, et FR+EN. Mettre à jour partout en cas de bump.
- Documenter chaque release dans [CHANGELOG.md](CHANGELOG.md) (sections **EN puis FR**) et mettre à jour [README.md](README.md).
- Le fichier source est versionné dans son nom (`ChatJPT_1_1_1.html`) ; un bump majeur/mineur renomme le fichier.
