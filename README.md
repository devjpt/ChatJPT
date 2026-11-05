================================================================
  ChatJPT — Multi-Model AI Agent
  Version 1.35.0
  By Jean-Philippe Theriault — https://www.devjpt.com/
================================================================


DESCRIPTION
-----------
ChatJPT is an all-in-one AI chat interface contained in a single
HTML file. It lets you interact with the leading AI models directly
from your browser — no installation required.


FEATURES
--------
  - Multi-provider support:
      • OpenAI     (GPT-6 Astra / Sol / Terra / Luna, GPT-5.6, GPT-5.x, etc.)
      • Anthropic  (Claude Fable 5.1, Opus 5.5, Sonnet 5.5, Haiku 5.5, etc.)
      • Google     (Gemini 4 Argon, Gemini 3.x, Gemini 2.5, Gemma 4, 🔬 Deep Research, etc.)
      • Grok       (xAI — chat, image, video, and voice; Grok Imagine)
      • Perplexity (web-grounded answers with sources, up to deep research)
      • Meta       (Muse Spark 1.3, Muse Wonder — reasoning summary, web search)
      • Augure     (Canada — Ossington 5, Rosedale One, Tofino 3, Ossington 4.1)
      • Cohere     (Canada — Command A+, A Reasoning, A Vision, North Mini Code, etc.)
      • Mistral    (France — Mistral Large 4, Medium 3.5, Small 4, Codestral)
      • DeepSeek   (DeepSeek V4 Pro, DeepSeek Flash)
      • Kimi       (Moonshot AI — Kimi K3.1 Pro, K3.1 Pro Highspeed, K3)
      • MiniMax    (M3.1 Flash, M3 — chat; Image-01; Hailuo video; voice)
      • Alibaba    (Qwen + Z.ai GLM — chat, image, video, and voice; International, Mainland China, US or Hong Kong key)
      • Upstage    (South Korea — Solar Pro 4, Solar Mini 4; very low cost, English)
      • Recraft    (United Kingdom — images only: vector SVG, styles, cutout, upscaling)
      • Bria       (Israel — images only: licensed, photo retouching, product photos, ads)

  - Conversation modes:
      • Chat       : general conversation
      • Vibe Coder : beginner-friendly mode for non-coders — asks one
                     question at a time, proposes a plan and waits for your
                     approval before building, then guides you step by step.
                     Generated web pages can be previewed live, right in the chat.
      • Code       : development assistance, syntax highlighting,
                     code block download
      • Image      : image generation — OpenAI GPT Image (adjustable
                     quality and size; 🎞️ animated GIF and SVG with GPT Image 2.6),
                     Google Gemini (14 formats including panoramic 1:4 to 8:1,
                     resolution up to 4K), Qwen, Grok, Recraft (vector SVG, styles), and Bria
                     (licensed images, retouching, product photos), and MiniMax
      • Video      : video generation (Google Gemini Omni, xAI Grok Imagine, MiniMax Hailuo, Alibaba Wan / HappyHorse);
                     ⏩ extend a video (Omni up to 40 s, Grok up to 20 s), ✏️ edit it (Omni, Grok)
      • Voice      : text-to-speech with MiniMax (emotions, effects, your own
                     designed or cloned voices), Google Gemini (1 or 2 voices, 150+ voices to search, your own designed, remixed or cloned voices),
                     Alibaba Qwen (120+ voices, 50+ languages, your own designed
                     or cloned voices), xAI Grok (expressive tags) and OpenAI
                     GPT-Audio; long texts joined
                     into a single MP3 / WAV file. 🎧 Podcast with all five:
                     a script written from your files or the conversation,
                     read by one or two hosts

  - Compare Mode: run the same prompt on two models side by side, then keep
    the answer you prefer (one click). Works in Chat and Code modes.

  - Multiple conversations: a left drawer (☰) to create, switch between,
    rename (double-click the title), delete, and export all your
    conversations. Stored locally; the oldest are never silently deleted —
    you are asked to free space if storage gets full.

  - In-conversation search: a 🔍 bar that highlights matches and lets you
    jump between them (case- and accent-insensitive).

  - Edit a sent message (✎) and have the AI answer the corrected prompt; edit an
    AI response in place; or regenerate any AI response with a different model (🔀).

  - Keyboard: Esc stops the current generation.

  - Smooth streaming: scrolling up to re-read doesn't fight the auto-scroll; a
    "scroll to bottom" button brings you back to the latest message.

  - Live HTML preview: complete HTML pages get a 👁 preview button that
    renders them instantly in a secure sandbox (works in any mode); a 💾
    button saves the file. Available wherever the AI returns a full page.

  - Collapsible API-keys panel with per-provider status (saved key /
    missing key) shown at a glance, plus a one-click button to clear all
    stored keys (handy on a shared computer).

  - Agent Mode: forces the AI to respond step-by-step in English,
    optimized for automated coding tools (Claude Code, Cursor, etc.)

  - Thinking Mode: shows the model's reasoning in a collapsible 🧠 block, with an
    adjustable depth or effort (Claude, OpenAI GPT-6, Gemini, Grok, Perplexity, DeepSeek, Qwen)

  - Light / Dark theme

  - Trilingual interface: English, French and Spanish

  - Rate AI responses (👍 / 👎): the rating is now also sent to the model as a
    signal (keep this approach / this missed). A 👎 reveals an "↻ Improve" box
    (with an optional reason) to get a better answer, plus a "report a bug"
    link. Export the full conversation, or only your 👍 responses.

  - Web search + Sources (optional 🌐 toggle, off by default): the model
    searches the web in real time and the answer is followed by a collapsible
    "Sources" list (each row fully clickable). Available for Gemini, Grok,
    Claude and OpenAI. A hint warns it uses more tokens (+ search fees).

  - 🔬 Gemini Deep Research (Google provider, "Deep Research" or "Deep Research
    Max" in the model list): Google's agent proposes a research plan you can
    edit, then searches the web for several minutes (up to 60) and writes a
    sourced report with charts. Progress is shown live and resumes after a
    reload; ⏹ stops it. About $1 to $3 per research ($3 to $7 for Max).

  - Claude extras: ⚡ Fast mode (Opus 5.5, Opus 5, Opus 4.8; up to 2.5× faster,
    2× the price), 📄 PDFs read as images (Claude sees the pages and gives the
    page of each quoted passage), automatic prompt caching (the history is
    reread at about 10% of the price, shown under each answer), and an
    automatic retry on another Claude model when a safety filter declines.

  - Grok extras: 𝕏 Search on X (posts and profiles, cited), Grok 4.20
    Multi-agent (4 or 16 agents), 🚀 Priority, adjustable thinking for Grok 4.3,
    videos from reference photos with a preset voice, expressive tags in Voice
    mode (laugh, whisper…), and the exact cost of each answer under it.

  - Alibaba extras: 🌐 web search with sources and 🔗 link reading (Qwen 3.7 /
    3.8, GLM-5.2), 📄 PDFs read directly by Qwen 3.8, explicit caching, Wan 2.7
    (up to 4K) and Z-Image images, 🔬 Qwen Deep Research (mainland China), and
    Qwen videos (Wan 3.0, HappyHorse) with a Qwen Cloud key from the US or Hong
    Kong region.

  - Read pasted links (optional 🔗 toggle, off by default, separate from web
    search): the model opens and reads the actual content of the URL(s) you paste,
    instead of guessing from the address; the page is shown as a clickable source.
    Fetching happens on the provider's server (no CORS). Available for Gemini
    (url_context), Claude (web_fetch), OpenAI and Grok (web_search). Not available
    for DeepSeek/Qwen.

  - Token counter: each response shows its exact usage (↑ input / ↓ output)
    and a per-conversation total in the footer bar — so you can see what each
    turn really costs.

  - Image editor (OpenAI, Gemini, Qwen, Grok, Recraft, Bria): under each image, ✏️ Edit
    (describe a change in your next message), ✂️ Remove background
    (transparent PNG, kept across later edits), ⬚ Format (square, portrait,
    story, photo, landscape, widescreen, cinematic, banner) and 💾 Download,
    each with a help tooltip. Drawing tools: 🧽 Erase (paint over an area to
    remove or replace it), 🖍️ Markup (draw on the image to show the changes)
    and 💬 Comment (pin numbered notes on precise spots). Edits use the
    selected provider if it can edit images, otherwise OpenAI. Your own
    photos can be edited too (Image mode). 🎬 Animate (Grok) turns the image
    into a 10-second video: with a prompt, quick animate or seamless loop
    (always Grok Imagine Video — requires an xAI key).

  - Attach files and PDFs (📎): text files, Word and Excel documents, images and PDFs. Scanned PDFs
    (pages made of images) can be transcribed to text once by the selected
    model (OCR, no page limit, estimated and actual cost shown), or attached
    as page images.

  - Image persistence: generated images are saved locally (IndexedDB) and
    survive page reloads and conversation switches. Use download (💾) for a
    permanent copy.

  - Your API keys and preferences are saved locally in your browser
    (no server, no data transmitted to the author)


INSTALLATION
------------
  No installation required.

  1. Download the file ChatJPT_1_35_0.html
  2. Open it in your browser (Chrome, Firefox, Edge, Safari)
  3. Enter your API keys in the configuration panel (left side)
  4. Choose your provider and model
  5. Start chatting

  To obtain your API keys, see: API_KEYS_GUIDE.txt


REQUIREMENTS
------------
  - A modern web browser (Chrome 90+, Firefox 88+, Edge 90+, Safari 15+)
  - A valid API key for at least one supported provider
  - An Internet connection


LICENSE
-------
  This software is distributed under the CC BY-ND 4.0 license.
  Free use and distribution are permitted.
  Modification and redistribution of modified versions are prohibited.
  See the LICENSE file for full details.


SUPPORT & CONTACT
-----------------
  Website  : https://www.devjpt.com/
  Bug report : via the "🐛 Bug" button inside the application


================================================================
  ChatJPT — Agent IA Multi-Modèles
  Version 1.35.0
  Par Jean-Philippe Theriault — https://www.devjpt.com/
================================================================


DESCRIPTION
-----------
ChatJPT est une interface de chat IA tout-en-un, contenue dans
un seul fichier HTML. Elle vous permet de discuter avec les
principaux modèles d'intelligence artificielle directement depuis
votre navigateur, sans installation requise.


FONCTIONNALITÉS
---------------
  - Support multi-fournisseurs :
      • OpenAI     (GPT-6 Astra / Sol / Terra / Luna, GPT-5.6, GPT-5.x, etc.)
      • Anthropic  (Claude Fable 5.1, Opus 5.5, Sonnet 5.5, Haiku 5.5, etc.)
      • Google     (Gemini 4 Argon, Gemini 3.x, Gemini 2.5, Gemma 4, 🔬 Deep Research, etc.)
      • Grok       (xAI — chat, image, vidéo et voix ; Grok Imagine)
      • Perplexity (réponses ancrées sur le web avec sources, jusqu'à la recherche approfondie)
      • Meta       (Muse Spark 1.3, Muse Wonder — résumé de la réflexion, recherche web)
      • Augure     (Canada — Ossington 5, Rosedale One, Tofino 3, Ossington 4.1)
      • Cohere     (Canada — Command A+, A Reasoning, A Vision, North Mini Code, etc.)
      • Mistral    (France — Mistral Large 4, Medium 3.5, Small 4, Codestral)
      • DeepSeek   (DeepSeek V4 Pro, DeepSeek Flash)
      • Kimi       (Moonshot AI — Kimi K3.1 Pro, K3.1 Pro Highspeed, K3)
      • MiniMax    (M3.1 Flash, M3 — chat ; Image-01 ; vidéo Hailuo ; voix)
      • Alibaba    (Qwen + Z.ai GLM — chat, image, vidéo et voix ; clé International, Chine continentale, États-Unis ou Hong Kong)
      • Upstage    (Corée du Sud — Solar Pro 4, Solar Mini 4 ; très économique, anglais)
      • Recraft    (Royaume-Uni — images seulement : SVG vectoriel, styles, détourage, agrandissement)
      • Bria       (Israël — images seulement : sous licence, retouche photo, photos de produits, pubs)

  - Modes de conversation :
      • Chat       : conversation générale
      • Vibe Coder : mode pour débutants (non-codeurs) — pose une question à
                     la fois, propose un plan et attend votre accord avant de
                     construire, puis vous guide pas à pas. Les pages web
                     générées peuvent être prévisualisées en direct dans le chat.
      • Code       : assistance au développement, coloration syntaxique,
                     téléchargement des blocs de code
      • Image      : génération d'images — OpenAI GPT Image (qualité et
                     taille ajustables ; 🎞️ GIF animé et SVG avec GPT Image 2.6),
                     Google Gemini (14 formats dont panoramiques 1:4 à 8:1,
                     résolution jusqu'à 4K), Qwen, Grok, Recraft (SVG vectoriel, styles) et Bria
                     (images sous licence, retouche, photos de produits) et MiniMax
      • Vidéo      : génération de vidéos (Google Gemini Omni, xAI Grok Imagine, MiniMax Hailuo, Alibaba Wan / HappyHorse) ;
                     ⏩ prolonger une vidéo (Omni jusqu'à 40 s, Grok jusqu'à 20 s), ✏️ la modifier (Omni, Grok)
      • Voix       : synthèse vocale avec MiniMax (émotions, effets, tes propres
                     voix créées ou clonées), Google Gemini (1 ou 2 voix, 150+ voix à rechercher, tes propres voix créées, remixées ou clonées),
                     Alibaba Qwen (120+ voix, 50+ langues, tes propres voix
                     créées ou clonées), xAI Grok (balises expressives) et
                     OpenAI GPT-Audio ; textes longs réunis en
                     un seul fichier MP3 / WAV. 🎧 Podcast avec les cinq : un
                     script écrit à partir de tes fichiers ou de la
                     conversation, lu par un ou deux animateurs

  - Mode Comparaison : lancez le même prompt sur deux modèles côte à côte,
    puis gardez la réponse que vous préférez (en un clic). Disponible en
    modes Chat et Code.

  - Conversations multiples : un panneau latéral (☰) pour créer, basculer,
    renommer (double-clic sur le titre), supprimer et tout exporter. Stockées
    localement ; les plus anciennes ne sont jamais effacées en silence — on
    vous demande de faire de la place si le stockage est plein.

  - Recherche dans la conversation : une barre 🔍 qui surligne les
    correspondances et permet d'y naviguer (insensible à la casse/aux accents).

  - Édition d'un message envoyé (✎) : l'IA répond au prompt corrigé ; édition
    d'une réponse de l'IA sur place ; ou régénération avec un autre modèle (🔀).

  - Clavier : Échap arrête la génération en cours.

  - Streaming fluide : remonter lire ne se bat plus avec le défilement
    automatique ; un bouton « revenir en bas » ramène au dernier message.

  - Aperçu HTML en direct : les pages HTML complètes affichent un bouton 👁
    qui les rend instantanément dans un bac à sable sécurisé (dans tous les
    modes) ; un bouton 💾 enregistre le fichier.

  - Panneau de clés API repliable, avec le statut de chaque fournisseur
    (clé enregistrée / manquante) visible d'un coup d'œil, plus un bouton
    pour effacer toutes les clés stockées en un clic (pratique sur un
    ordinateur partagé).

  - Mode Agent : force l'IA à répondre étape par étape en anglais,
    optimisé pour les outils de codage automatisés (Claude Code, Cursor, etc.)

  - Mode Thinking : affiche la réflexion du modèle dans un bloc 🧠 repliable, avec
    une profondeur ou un effort réglable (Claude, OpenAI GPT-6, Gemini, Grok,
    Perplexity, DeepSeek, Qwen)

  - Thème clair / sombre

  - Interface trilingue : français, anglais et espagnol

  - Notez les réponses de l'IA (👍 / 👎) : la note est désormais aussi transmise
    au modèle comme signal (garder cette approche / éviter cela). Un 👎 révèle
    une boîte « ↻ Améliorer » (raison facultative) pour obtenir une meilleure
    réponse, plus un lien « signaler un bug ». Exportez la conversation
    complète, ou seulement vos réponses 👍.

  - Recherche web + Sources (toggle 🌐 optionnel, désactivé par défaut) : le
    modèle cherche le web en temps réel et la réponse est suivie d'une liste
    « Sources » repliable (ligne entièrement cliquable). Disponible pour Gemini,
    Grok, Claude et OpenAI. Une mention prévient que ça consomme plus de tokens
    (+ frais de recherche).

  - 🔬 Deep Research de Gemini (fournisseur Google, « Deep Research » ou
    « Deep Research Max » dans la liste des modèles) : l'agent de Google propose
    un plan de recherche que tu peux modifier, puis cherche sur le web pendant
    plusieurs minutes (jusqu'à 60) et rédige un rapport sourcé avec graphiques.
    L'avancement s'affiche en direct et reprend après un rechargement ; ⏹
    l'arrête. Environ 1 à 3 $ la recherche (3 à 7 $ pour Max).

  - Bonus Claude : ⚡ Mode rapide (Opus 5.5, Opus 5, Opus 4.8 ; jusqu'à 2,5× plus
    rapide, 2× le prix), 📄 PDF lus en images (Claude voit les pages et indique
    la page de chaque passage cité), cache automatique (l'historique est relu à
    environ 10 % du prix, affiché sous chaque réponse) et relance automatique sur
    un autre modèle Claude quand un filtre de sécurité refuse.

  - Bonus Grok : 𝕏 Recherche sur X (publications et profils, cités), Grok 4.20
    Multi-agents (4 ou 16 agents), 🚀 Prioritaire, réflexion réglable pour
    Grok 4.3, vidéos à partir de photos de référence avec une voix préréglée,
    balises expressives en mode Voix (rire, chuchoter…) et coût exact de chaque
    réponse affiché dessous.

  - Bonus Alibaba : 🌐 recherche web avec sources et 🔗 lecture des liens
    (Qwen 3.7 / 3.8, GLM-5.2), 📄 PDF lus directement par Qwen 3.8, cache
    explicite, images Wan 2.7 (jusqu'à 4K) et Z-Image, 🔬 Qwen Deep Research
    (Chine continentale) et vidéos Qwen (Wan 3.0, HappyHorse) avec une clé Qwen
    Cloud de la région États-Unis ou Hong Kong.

  - Lire les liens collés (toggle 🔗 optionnel, désactivé par défaut, distinct de
    la recherche web) : le modèle ouvre et lit le contenu réel de la ou des URL que
    vous collez, au lieu de deviner d'après l'adresse ; la page est affichée comme
    source cliquable. La lecture se fait sur le serveur du fournisseur (aucun CORS).
    Disponible pour Gemini (url_context), Claude (web_fetch), OpenAI et Grok
    (web_search). Indisponible pour DeepSeek/Qwen.

  - Compteur de tokens : chaque réponse affiche sa consommation exacte
    (↑ entrée / ↓ sortie) et un total par conversation dans la barre du bas —
    pour voir ce que coûte réellement chaque échange.

  - Éditeur d'image (OpenAI, Gemini, Qwen, Grok, Recraft, Bria) : sous chaque image, ✏️ Modifier
    (décrivez le changement dans le message suivant), ✂️ Retirer le fond (PNG
    transparent, conservé lors des modifications suivantes), ⬚ Format (carré,
    portrait, story, photo, paysage, grand écran, cinéma, bannière) et
    💾 Télécharger, chacun avec une infobulle d'aide. Outils de dessin : 🧽 Effacer
    (peindre une zone pour la retirer ou la remplacer), 🖍️ Annoter (dessiner sur
    l'image pour montrer les changements) et 💬 Commenter (épingler des notes
    numérotées à des endroits précis). L'édition passe par le fournisseur
    sélectionné s'il sait éditer les images, sinon par OpenAI. Vos propres photos
    peuvent aussi être modifiées (mode Image). 🎬 Animer (Grok) transforme
    l'image en vidéo de 10 s : avec une consigne, animation rapide ou boucle
    continue (toujours Grok Imagine Vidéo — clé xAI requise).

  - Fichiers et PDF joints (📎) : fichiers texte, documents Word et Excel, images et PDF. Les PDF scannés
    (pages composées d'images) peuvent être transcrits en texte une seule fois
    par le modèle sélectionné (OCR, sans limite de pages, coût estimé puis réel
    affiché), ou joints comme images de pages.

  - Persistance des images : les images générées sont enregistrées localement
    (IndexedDB) et survivent aux rechargements et aux changements de
    conversation. Téléchargez (💾) pour une copie permanente.

  - Vos clés API et préférences sont sauvegardées localement
    dans votre navigateur (aucun serveur, aucune donnée transmise à l'auteur)


INSTALLATION
------------
  Aucune installation requise.

  1. Téléchargez le fichier ChatJPT_1_35_0.html
  2. Ouvrez-le dans votre navigateur (Chrome, Firefox, Edge, Safari)
  3. Entrez vos clés API dans le panneau de configuration (côté gauche)
  4. Choisissez votre fournisseur et votre modèle
  5. Commencez à discuter

  Pour obtenir vos clés API, consultez : API_KEYS_GUIDE.txt


PRÉREQUIS
---------
  - Un navigateur web moderne (Chrome 90+, Firefox 88+, Edge 90+, Safari 15+)
  - Une clé API valide pour au moins un des fournisseurs supportés
  - Une connexion Internet


LICENCE
-------
  Ce logiciel est distribué sous licence CC BY-ND 4.0.
  Utilisation et distribution gratuites autorisées.
  Modification et redistribution de versions modifiées interdites.
  Voir le fichier LICENSE pour les détails complets.


SUPPORT & CONTACT
-----------------
  Site web  : https://www.devjpt.com/
  Signaler un bug : via le bouton "🐛 Bug" dans l'application

================================================================


================================================================
  ChatJPT — Agente de IA Multimodelo
  Versión 1.35.0
  Por Jean-Philippe Theriault — https://www.devjpt.com/
================================================================


DESCRIPCIÓN
-----------
ChatJPT es una interfaz de chat de IA todo en uno, contenida en
un solo archivo HTML. Te permite conversar con los principales
modelos de inteligencia artificial directamente desde tu
navegador, sin necesidad de instalación.


CARACTERÍSTICAS
---------------
  - Soporte multiproveedor:
      • OpenAI     (GPT-6 Astra / Sol / Terra / Luna, GPT-5.6, GPT-5.x, etc.)
      • Anthropic  (Claude Fable 5.1, Opus 5.5, Sonnet 5.5, Haiku 5.5, etc.)
      • Google     (Gemini 4 Argon, Gemini 3.x, Gemini 2.5, Gemma 4, 🔬 Deep Research, etc.)
      • Grok       (xAI — chat, imagen, video y voz; Grok Imagine)
      • Perplexity (respuestas basadas en la web con fuentes, hasta investigación profunda)
      • Meta       (Muse Spark 1.3, Muse Wonder — resumen del razonamiento, búsqueda web)
      • Augure     (Canadá — Ossington 5, Rosedale One, Tofino 3, Ossington 4.1)
      • Cohere     (Canadá — Command A+, A Reasoning, A Vision, North Mini Code, etc.)
      • Mistral    (Francia — Mistral Large 4, Medium 3.5, Small 4, Codestral)
      • DeepSeek   (DeepSeek V4 Pro, DeepSeek Flash)
      • Kimi       (Moonshot AI — Kimi K3.1 Pro, K3.1 Pro Highspeed, K3)
      • MiniMax    (M3.1 Flash, M3 — chat; Image-01; video Hailuo; voz)
      • Alibaba    (Qwen + Z.ai GLM — chat, imagen, video y voz; clave Internacional, China continental, Estados Unidos o Hong Kong)
      • Upstage    (Corea del Sur — Solar Pro 4, Solar Mini 4; muy económico, inglés)
      • Recraft    (Reino Unido — solo imágenes: SVG vectorial, estilos, recorte, ampliación)
      • Bria       (Israel — solo imágenes: con licencia, retoque fotográfico, fotos de productos, anuncios)

  - Modos de conversación:
      • Chat       : conversación general
      • Vibe Coder : modo para principiantes (no programadores) — hace una
                     pregunta a la vez, propone un plan y espera tu aprobación
                     antes de construir, luego te guía paso a paso. Las páginas
                     web generadas se pueden previsualizar en vivo en el chat.
      • Código     : asistencia al desarrollo, resaltado de sintaxis,
                     descarga de bloques de código
      • Imagen     : generación de imágenes — OpenAI GPT Image (calidad y
                     tamaño ajustables; 🎞️ GIF animado y SVG con GPT Image 2.6),
                     Google Gemini (14 formatos incluidos panorámicos 1:4 a 8:1,
                     resolución hasta 4K), Qwen, Grok, Recraft (SVG vectorial, estilos) y Bria
                     (imágenes con licencia, retoque, fotos de productos) y MiniMax
      • Video      : generación de videos (Google Gemini Omni, xAI Grok Imagine, MiniMax Hailuo, Alibaba Wan / HappyHorse);
                     ⏩ extender un video (Omni hasta 40 s, Grok hasta 20 s), ✏️ editarlo (Omni, Grok)
      • Voz        : síntesis de voz con MiniMax (emociones, efectos, tus propias
                     voces creadas o clonadas), Google Gemini (1 o 2 voces, 150+ voces para buscar, tus propias voces creadas, remezcladas o clonadas),
                     Alibaba Qwen (120+ voces, 50+ idiomas, tus propias voces
                     creadas o clonadas), xAI Grok (etiquetas expresivas) y
                     OpenAI GPT-Audio; textos largos
                     unidos en un solo archivo MP3 / WAV. 🎧 Pódcast con los
                     cinco: un guion escrito a partir de tus archivos o de la
                     conversación, leído por uno o dos presentadores

  - Modo Comparación: ejecuta el mismo prompt en dos modelos lado a lado y
    conserva la respuesta que prefieras (con un clic). Disponible en los modos
    Chat y Código.

  - Conversaciones múltiples: un panel lateral (☰) para crear, cambiar,
    renombrar (doble clic en el título), eliminar y exportar todo. Se guardan
    localmente; las más antiguas nunca se borran en silencio — se te pide
    liberar espacio si el almacenamiento se llena.

  - Búsqueda web + Fuentes (interruptor 🌐 opcional, desactivado por defecto):
    el modelo busca en la web en tiempo real y la respuesta va seguida de una
    lista "Fuentes" plegable (cada línea es completamente clicable). Disponible
    para Gemini, Grok, Claude y OpenAI. Un aviso advierte que consume más
    tokens (+ costos de búsqueda).

  - 🔬 Deep Research de Gemini (proveedor Google, "Deep Research" o "Deep
    Research Max" en la lista de modelos): el agente de Google propone un plan
    de investigación que puedes modificar, luego busca en la web durante varios
    minutos (hasta 60) y redacta un informe con fuentes y gráficos. El avance se
    muestra en vivo y se retoma tras recargar; ⏹ lo detiene. Unos 1 a 3 US$ por
    investigación (3 a 7 US$ para Max).

  - Extras de Claude: ⚡ Modo rápido (Opus 5.5, Opus 5, Opus 4.8; hasta 2,5× más
    rápido, 2× el precio), 📄 PDF leídos como imágenes (Claude ve las páginas e
    indica la página de cada pasaje citado), caché automática (el historial se
    relee a cerca del 10 % del precio, indicado bajo cada respuesta) y
    reintento automático con otro modelo Claude cuando un filtro de seguridad
    rechaza.

  - Extras de Grok: 𝕏 Búsqueda en X (publicaciones y perfiles, citados), Grok
    4.20 Multiagente (4 o 16 agentes), 🚀 Prioritario, razonamiento ajustable
    para Grok 4.3, videos a partir de fotos de referencia con una voz
    predefinida, etiquetas expresivas en modo Voz (risa, susurro…) y costo exacto
    de cada respuesta indicado debajo.

  - Extras de Alibaba: 🌐 búsqueda web con fuentes y 🔗 lectura de enlaces
    (Qwen 3.7 / 3.8, GLM-5.2), 📄 PDF leídos directamente por Qwen 3.8, caché
    explícita, imágenes Wan 2.7 (hasta 4K) y Z-Image, 🔬 Qwen Deep Research
    (China continental) y videos de Qwen (Wan 3.0, HappyHorse) con una clave de
    Qwen Cloud de la región Estados Unidos o Hong Kong.

  - Leer enlaces pegados (interruptor 🔗 opcional, desactivado por defecto,
    distinto de la búsqueda web): el modelo abre y lee el contenido real de la(s)
    URL que pegas, en lugar de adivinar a partir de la dirección; la página se
    muestra como fuente clicable. La obtención se realiza en el servidor del
    proveedor (sin CORS). Disponible para Gemini (url_context), Claude (web_fetch),
    OpenAI y Grok (web_search). No disponible para DeepSeek/Qwen.

  - Contador de tokens: cada respuesta muestra su consumo exacto
    (↑ entrada / ↓ salida) y un total por conversación en la barra inferior —
    para ver lo que cuesta realmente cada intercambio.

  - Búsqueda en la conversación: una barra 🔍 que resalta las coincidencias y
    permite navegar entre ellas (sin distinción de mayúsculas ni acentos).

  - Edita un mensaje enviado (✎) y haz que la IA responda al prompt corregido;
    edita una respuesta de la IA en su lugar; o regenera cualquier respuesta con
    otro modelo (🔀).

  - Teclado: Esc detiene la generación en curso.

  - Editor de imágenes (OpenAI, Gemini, Qwen, Grok, Recraft, Bria): debajo de cada imagen,
    ✏️ Editar (describe el cambio en tu próximo mensaje), ✂️ Quitar el fondo
    (PNG transparente, conservado en las ediciones siguientes), ⬚ Formato
    (cuadrado, vertical, historia, foto, horizontal, panorámico, cine, banner)
    y 💾 Descargar, cada uno con una ayuda emergente. Herramientas de dibujo:
    🧽 Borrar (pinta una zona para quitarla o reemplazarla), 🖍️ Anotar (dibuja
    sobre la imagen para mostrar los cambios) y 💬 Comentar (fija notas
    numeradas en puntos precisos). La edición usa el proveedor seleccionado si
    edita imágenes; si no, OpenAI. También puedes editar tus propias fotos
    (modo Imagen). 🎬 Animar (Grok) convierte la imagen en un video de 10 s:
    con una indicación, animación rápida o bucle continuo (siempre Grok
    Imagine Video — requiere una clave de xAI).

  - Archivos y PDF adjuntos (📎): archivos de texto, documentos de Word y Excel, imágenes y PDF. Los PDF
    escaneados (páginas compuestas de imágenes) pueden transcribirse a texto una
    sola vez con el modelo seleccionado (OCR, sin límite de páginas, con costo
    estimado y real), o adjuntarse como imágenes de las páginas.

  - Persistencia de imágenes: las imágenes generadas se guardan localmente
    (IndexedDB) y sobreviven a las recargas de página y a los cambios de
    conversación. Usa descargar (💾) para una copia permanente.

  - Vista previa HTML en vivo: las páginas HTML completas muestran un botón 👁
    que las renderiza al instante en un entorno aislado y seguro (en todos los
    modos); un botón 💾 guarda el archivo.

  - Panel de claves API plegable, con el estado de cada proveedor (clave
    guardada / faltante) visible de un vistazo, más un botón para borrar todas
    las claves almacenadas con un clic (útil en una computadora compartida).

  - Modo Agente: obliga a la IA a responder paso a paso en inglés, optimizado
    para herramientas de codificación automatizadas (Claude Code, Cursor, etc.)

  - Modo Razonamiento: muestra el razonamiento del modelo en un bloque 🧠 plegable,
    con una profundidad o un esfuerzo ajustable (Claude, OpenAI GPT-6, Gemini,
    Grok, Perplexity, DeepSeek, Qwen)

  - Tema claro / oscuro

  - Interfaz trilingüe: francés, inglés y español

  - Califica las respuestas de la IA (👍 / 👎): la calificación también se envía
    al modelo como señal. Un 👎 revela una caja "↻ Mejorar" (con un motivo
    opcional) para obtener una mejor respuesta, más un enlace para reportar un
    error. Exporta la conversación completa, o solo tus respuestas 👍.

  - Tus claves API y preferencias se guardan localmente en tu navegador
    (sin servidor, sin datos transmitidos al autor)


INSTALACIÓN
-----------
  No requiere instalación.

  1. Descarga el archivo ChatJPT_1_35_0.html
  2. Ábrelo en tu navegador (Chrome, Firefox, Edge, Safari)
  3. Ingresa tus claves API en el panel de configuración (lado izquierdo)
  4. Elige tu proveedor y modelo
  5. Empieza a chatear

  Para obtener tus claves API, consulta: API_KEYS_GUIDE.txt


REQUISITOS
----------
  - Un navegador web moderno (Chrome 90+, Firefox 88+, Edge 90+, Safari 15+)
  - Una clave API válida para al menos uno de los proveedores soportados
  - Una conexión a Internet


LICENCIA
--------
  Este software se distribuye bajo la licencia CC BY-ND 4.0.
  Uso y distribución gratuitos permitidos.
  Modificación y redistribución de versiones modificadas prohibidas.
  Consulta el archivo LICENSE para los detalles completos.


SOPORTE Y CONTACTO
------------------
  Sitio web : https://www.devjpt.com/
  Reportar un error : con el botón "🐛 Bug" dentro de la aplicación

================================================================
