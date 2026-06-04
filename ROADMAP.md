# ROADMAP — ChatJPT (multi-fournisseurs + mode comparaison)

Document de **continuité** entre machines/sessions : état du chantier et plan du mode comparaison. Les détails d'architecture et la recette « ajouter un fournisseur » sont dans [CLAUDE.md](CLAUDE.md).

## Fait (intégré dans `main`)

- **Panneau de clés repliable** (accordéon) — pastilles de statut par fournisseur.
- **DeepSeek** (`deepseek-chat`, `deepseek-reasoner`) — compatible OpenAI.
- **Qwen chat** (`qwen-max`/`plus`/`turbo`, `qwen3-max`, `qwen3-coder-plus`) — compatible OpenAI, avec **sélecteur de région DashScope** (intl/mainland, clé `ai_qwen_region`).
- **Qwen image** (`qwen-image-max`, `qwen-image-2.0-pro`) — **synchrone**, renvoie l'URL OSS.

Mécanisme commun : `OPENAI_COMPATIBLE_ENDPOINTS` (résolveurs) + `callOpenAICompatibleStream` (sans `reasoning_effort`). Capacités image/vidéo **pilotées par les tables** (`IMAGE_MODELS`/`VIDEO_MODELS`) dans `updateProviderUI`.

## Conclusions CORS (testées en `file://`)

- DeepSeek chat ✅ · Qwen chat ✅ (intl + mainland) · Qwen image **synchrone** ✅ (URL directe → `<img src>`, zéro CORS).
- **Qwen vidéo (Wan) ❌** : le polling `/api/v1/tasks/{id}` est **bloqué par CORS** (confirmé avec un vrai `task_id`, réponse 200). Vidéo Wan **impossible sans proxy**. Sora/Veo restent les options vidéo (leurs endpoints de polling autorisent le CORS navigateur). → décision : **on n'ajoute pas la vidéo Qwen**.
- Le mode vidéo ne peut PAS être « débloqué » par un toggle dans l'app : le CORS est imposé par le navigateur, pas par un conflit de fournisseurs.

## Gotcha — historique partagé inter-fournisseurs

`conversationHistory` est commun à tous les fournisseurs ; `formatHistory` ne transmet que `{role, content}` (l'étiquette provider est retirée). En changeant de fournisseur **sans effacer**, le nouveau modèle reçoit les réponses de l'autre comme ses propres tours (ex. DeepSeek « insiste » qu'il est Claude). Comportement attendu, pas un bug. **À gérer dans le mode comparaison.**

## À faire — Mode comparaison (prochaine grosse étape)

Objectif : comparer **2 réponses de 2 modèles** au même prompt (ex. Opus vs Sonnet, Claude vs ChatGPT), côte à côte.

**Design v1 « pick-winner »** (garde `conversationHistory` linéaire, donc multi-tour/export/PDF/`loadHistory` inchangés) :
- Un prompt génère 2 réponses côte à côte ; **aucune** n'entre dans l'historique tout de suite.
- Bouton « Garder cette réponse » → pousse la **seule** réponse choisie dans `conversationHistory` + `saveHistory()`.

**Refactors nécessaires :**
1. **AbortController par requête** : aujourd'hui `currentAbortController` est un singleton lu en dur dans les 4 fonctions de stream → passer le `signal` en paramètre (2 flux parallèles via `Promise.all`). Bouton Stop = abort des deux.
2. Extraire un `streamInto(loadingDiv, provider, model, key, signal)` réutilisé par le mode normal et la comparaison.
3. **Rendu 2 colonnes** (`.compare-row` flex ; override de `.message{max-width:82%}` ; empilement sur mobile).
4. **Sélection** : 2 sélecteurs de modèle listant **tous** les modèles groupés par fournisseur (`<optgroup>`) → couvre Opus vs Sonnet ET Claude vs ChatGPT. Valider les 2 clés (`getKeyForProvider`).

Hors périmètre v1 : branching multi-fils, comparaison en mode image/vidéo, thinking réglable par colonne.

## Branches & workflow

`main` contient tout (fusions en fast-forward). Branches `feat/keys-panel`, `feat/deepseek`, `feat/qwen`, `feat/qwen-media` conservées comme historique (poussées sur `origin`).

Workflow convenu : créer `feat/<x>` depuis `main` → commits par étape livrable → **gate CORS avant tout nouveau fournisseur** → validation manuelle par l'utilisateur (vrais appels API) → commit → push → fusion FF dans `main`.

Note : la clé Qwen de l'auteur est **International (Singapour)**.
