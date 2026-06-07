================================================================
  ChatJPT — Multi-Model AI Agent
  Version 1.6.0
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

  1. Download the file ChatJPT_1_6_0.html
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
  Version 1.6.0
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

  1. Téléchargez le fichier ChatJPT_1_6_0.html
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
