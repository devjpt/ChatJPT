================================================================
  ChatJPT — Multi-Model AI Agent
  Version 1.7.0
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
      • OpenAI     (GPT-5.x, GPT-4.1, o-series, etc.)
      • Anthropic  (Claude Opus 4.8, Sonnet 4.6, Haiku 4.5, etc.)
      • Google     (Gemini 3.x, Gemini 2.5, etc.)
      • Grok       (xAI — chat, image, and video; Grok Imagine)
      • DeepSeek   (DeepSeek V3 chat, DeepSeek R1 reasoning)
      • Qwen       (Alibaba — chat and image; selectable DashScope region)

  - Conversation modes:
      • Chat       : general conversation
      • Vibe Coder : beginner-friendly mode for non-coders — asks one
                     question at a time, proposes a plan and waits for your
                     approval before building, then guides you step by step.
                     Generated web pages can be previewed live, right in the chat.
      • Code       : development assistance, syntax highlighting,
                     code block download
      • Image      : image generation — OpenAI GPT Image (adjustable
                     quality and size), Google Gemini (adjustable format and
                     resolution), Qwen, and Grok
      • Video      : video generation (OpenAI Sora 2, Google Veo, xAI Grok Imagine)

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

  - Thinking Mode: enables extended reasoning (Claude, Gemini)

  - Light / Dark theme

  - Bilingual interface: English and French

  - Rate AI responses (👍 / 👎): the rating is now also sent to the model as a
    signal (keep this approach / this missed). A 👎 reveals an "↻ Improve" box
    (with an optional reason) to get a better answer, plus a "report a bug"
    link. Export the full conversation, or only your 👍 responses.

  - Web search + Sources (optional 🌐 toggle, off by default): the model
    searches the web in real time and the answer is followed by a collapsible
    "Sources" list (each row fully clickable). Available for Gemini, Grok,
    Claude and OpenAI. A hint warns it uses more tokens (+ search fees).

  - Read pasted links (optional 🔗 toggle, off by default, separate from web
    search): the model opens and reads the actual content of the URL(s) you paste,
    instead of guessing from the address; the page is shown as a clickable source.
    Fetching happens on the provider's server (no CORS). Available for Gemini
    (url_context), Claude (web_fetch), OpenAI and Grok (web_search). Not available
    for DeepSeek/Qwen.

  - Token counter: each response shows its exact usage (↑ input / ↓ output)
    and a per-conversation total in the footer bar — so you can see what each
    turn really costs.

  - Image persistence: generated images are saved locally (IndexedDB) and
    survive page reloads and conversation switches. Use download (💾) for a
    permanent copy.

  - Your API keys and preferences are saved locally in your browser
    (no server, no data transmitted to the author)


INSTALLATION
------------
  No installation required.

  1. Download the file ChatJPT_1_7_0.html
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
  Version 1.7.0
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
      • OpenAI     (GPT-5.x, GPT-4.1, série o, etc.)
      • Anthropic  (Claude Opus 4.8, Sonnet 4.6, Haiku 4.5, etc.)
      • Google     (Gemini 3.x, Gemini 2.5, etc.)
      • Grok       (xAI — chat, image et vidéo ; Grok Imagine)
      • DeepSeek   (DeepSeek V3 chat, DeepSeek R1 raisonnement)
      • Qwen       (Alibaba — chat et image ; région DashScope au choix)

  - Modes de conversation :
      • Chat       : conversation générale
      • Vibe Coder : mode pour débutants (non-codeurs) — pose une question à
                     la fois, propose un plan et attend votre accord avant de
                     construire, puis vous guide pas à pas. Les pages web
                     générées peuvent être prévisualisées en direct dans le chat.
      • Code       : assistance au développement, coloration syntaxique,
                     téléchargement des blocs de code
      • Image      : génération d'images — OpenAI GPT Image (qualité et
                     taille ajustables), Google Gemini (format et résolution
                     ajustables), Qwen et Grok
      • Vidéo      : génération de vidéos (OpenAI Sora 2, Google Veo, xAI Grok Imagine)

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

  - Mode Thinking : active le raisonnement étendu (Claude, Gemini)

  - Thème clair / sombre

  - Interface bilingue : français et anglais

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

  - Lire les liens collés (toggle 🔗 optionnel, désactivé par défaut, distinct de
    la recherche web) : le modèle ouvre et lit le contenu réel de la ou des URL que
    vous collez, au lieu de deviner d'après l'adresse ; la page est affichée comme
    source cliquable. La lecture se fait sur le serveur du fournisseur (aucun CORS).
    Disponible pour Gemini (url_context), Claude (web_fetch), OpenAI et Grok
    (web_search). Indisponible pour DeepSeek/Qwen.

  - Compteur de tokens : chaque réponse affiche sa consommation exacte
    (↑ entrée / ↓ sortie) et un total par conversation dans la barre du bas —
    pour voir ce que coûte réellement chaque échange.

  - Persistance des images : les images générées sont enregistrées localement
    (IndexedDB) et survivent aux rechargements et aux changements de
    conversation. Téléchargez (💾) pour une copie permanente.

  - Vos clés API et préférences sont sauvegardées localement
    dans votre navigateur (aucun serveur, aucune donnée transmise à l'auteur)


INSTALLATION
------------
  Aucune installation requise.

  1. Téléchargez le fichier ChatJPT_1_7_0.html
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
  Versión 1.7.0
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
      • OpenAI     (GPT-5.x, GPT-4.1, serie o, etc.)
      • Anthropic  (Claude Opus 4.8, Sonnet 4.6, Haiku 4.5, etc.)
      • Google     (Gemini 3.x, Gemini 2.5, etc.)
      • Grok       (xAI — chat, imagen y video; Grok Imagine)
      • DeepSeek   (DeepSeek V3 chat, DeepSeek R1 razonamiento)
      • Qwen       (Alibaba — chat e imagen; región DashScope a elegir)

  - Modos de conversación:
      • Chat       : conversación general
      • Vibe Coder : modo para principiantes (no programadores) — hace una
                     pregunta a la vez, propone un plan y espera tu aprobación
                     antes de construir, luego te guía paso a paso. Las páginas
                     web generadas se pueden previsualizar en vivo en el chat.
      • Código     : asistencia al desarrollo, resaltado de sintaxis,
                     descarga de bloques de código
      • Imagen     : generación de imágenes — OpenAI GPT Image (calidad y
                     tamaño ajustables), Google Gemini (formato y resolución
                     ajustables), Qwen y Grok
      • Video      : generación de videos (OpenAI Sora 2, Google Veo, xAI Grok Imagine)

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

  - Modo Razonamiento: activa el razonamiento extendido (Claude, Gemini)

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

  1. Descarga el archivo ChatJPT_1_7_0.html
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
