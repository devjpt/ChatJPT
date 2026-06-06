================================================================
  CHANGELOG — ChatJPT
  By Jean-Philippe Theriault — https://www.devjpt.com/
================================================================


----------------------------------------------------------------
  ENGLISH
----------------------------------------------------------------

[1.3.0] — 2026-06-05
  Added
    - Grok (xAI) provider — placed between Gemini and DeepSeek (American
      models grouped together):
        - Chat: grok-4.3 (flagship), grok-4.20 (reasoning / non-reasoning),
          grok-build-0.1. OpenAI-compatible streaming.
        - Image: grok-imagine-image-quality (synchronous), with format and
          resolution selectors.
        - Video: grok-imagine-video (Grok Imagine) — 10s, 720p, native audio
          (submit + poll, like Sora/Veo). 3rd video provider after Sora/Veo.
    - "Clear keys" button in the API-keys panel: wipes all stored API keys from
      the browser in one click (with confirmation) — handy on a shared computer.
  Fixed
    - xAI errors (returned as a plain string, not an object) are now surfaced
      with their real message instead of a generic "HTTP Error 400" — e.g.
      content-moderation rejections are now clear (Grok chat, image and video).
  Changed
    - Removed a leftover third-party build script (MyNinja) that was loaded but
      unused: no more third-party JS or telemetry on the page where API keys
      are entered.
    - Source file renamed from ChatJPT_1_2_0.html to ChatJPT_1_3_0.html.
    - Version string updated to 1.3.0 (header and footer, FR/EN).

[1.2.0] — 2026-06-04
  Added
    - DeepSeek provider (DeepSeek V3 chat, DeepSeek R1 reasoning),
      OpenAI-compatible streaming.
    - Qwen provider (Alibaba DashScope): chat (qwen-max/plus/turbo,
      qwen3-max, qwen3-coder-plus) and image generation, with a selectable
      DashScope region (International / Mainland China).
    - Collapsible API-keys panel with per-provider status pills (saved key /
      missing key), now showing each provider's name next to its colour dot.
    - Compare Mode: run the same prompt on two models side by side (any
      providers, grouped by provider), with both responses streamed in
      parallel. Keep the answer you prefer in one click — or discard both;
      only the kept answer enters the conversation history. Available in
      Chat and Code modes.
    - Vibe Coder mode: a beginner-oriented mode for non-coders. A patient
      mentor that detects your language, asks one clarifying question at a
      time, presents a plain-language action plan and WAITS for your approval
      before building, then guides you step by step — pointing to the in-app
      preview/download buttons, offering concrete next steps, and pre-empting
      common mistakes.
    - Live HTML preview: any complete HTML page shows a 👁 preview button
      that renders it instantly in a sandboxed iframe (allow-scripts only, no
      same-origin access — the previewed code cannot read your stored API
      keys), plus an "open in a new tab" option. Available in every mode.
  Fixed
    - Large outputs (complete single-file HTML pages) are no longer truncated
      on Gemini and the OpenAI-compatible providers (DeepSeek, Qwen): their
      output-token budget is raised for code-heavy modes.
  Changed
    - Source file renamed from ChatJPT_1_1_1.html to ChatJPT_1_2_0.html.
    - Version string updated to 1.2.0 (header and footer, FR/EN).

[1.1.1] — 2026-06-01
  Added
    - Claude Opus 4.8 (claude-opus-4-8) — now the default and most
      capable Claude model.
    - Image quality selector for OpenAI (Low/Medium/High/Auto). Quality
      was previously hardcoded to "High", the slowest setting; it now
      defaults to "Medium" for faster generation and is user-adjustable.
    - Image size selector for OpenAI (Square/Landscape/Portrait/Auto),
      replacing the hardcoded 1024×1024. Both quality and size are saved
      and only shown for OpenAI.
    - Image format (aspect ratio) and resolution (1K/2K/4K) selectors for
      Gemini, applied to both Nano Banana and Imagen 4. Saved and only
      shown for Gemini. (Gemini has no Low/Medium/High "quality" knob;
      resolution is its equivalent lever.)
    - Per-message thumbs up/down rating on AI responses, saved with the
      conversation and restored on reload.
    - A dismissible "buy me a coffee" banner, shown at most once per
      session and only after a 👍 (never after a 👎).
    - Export of 👍-rated responses only (each preceded by its prompt),
      alongside the existing full-conversation export.
  Fixed
    - OpenAI (Sora) video generation: the duration menu now offers the
      values the Sora API actually accepts (8/12/16/20 s) instead of the
      Gemini Veo values (8/6/4 s), which were rejected.
    - Video polling no longer hangs silently for 20 minutes on an API
      error; the real error is now surfaced after a few failed attempts.
    - Sora 2 Pro now gets a longer generation timeout (~40 min) since Pro
      renders are much slower than the fast model; progress message no
      longer promises an unrealistic "1-3 min".
    - Video errors now also show the provider's exact message (and log it
      to the console), so moderation/parameter rejections are clear instead
      of being hidden behind a generic message.
  Changed
    - Claude Opus 4.7 is no longer marked as "Latest" (moved to legacy).
    - Source file renamed from ChatJPT_1_1.html to ChatJPT_1_1_1.html.
    - Version string updated to 1.1.1 (header and footer, FR/EN).

[1.1] — 2026
  Added
    - Initial public release.
    - Multi-provider support: OpenAI, Anthropic (Claude), Google (Gemini).
    - Chat, Code, Image, and Video modes.
    - Agent Mode and Thinking Mode.
    - Light / Dark theme and bilingual interface (EN/FR).
    - Local storage of API keys and preferences (no server).
    - File download support (code blocks, table CSV).


----------------------------------------------------------------
  FRANÇAIS
----------------------------------------------------------------

[1.3.0] — 2026-06-05
  Ajouté
    - Fournisseur Grok (xAI) — placé entre Gemini et DeepSeek (regroupement
      des modèles américains) :
        - Chat : grok-4.3 (flagship), grok-4.20 (raisonnement / non-raisonnement),
          grok-build-0.1. Streaming compatible OpenAI.
        - Image : grok-imagine-image-quality (synchrone), avec sélecteurs de
          format et de résolution.
        - Vidéo : grok-imagine-video (Grok Imagine) — 10 s, 720p, audio natif
          (submit + polling, comme Sora/Veo). 3e fournisseur vidéo après Sora/Veo.
    - Bouton « Effacer les clés » dans le panneau de clés : supprime toutes les
      clés API stockées du navigateur en un clic (avec confirmation) — pratique
      sur un ordinateur partagé.
  Corrigé
    - Les erreurs xAI (renvoyées sous forme de chaîne, et non d'objet) affichent
      désormais leur vrai message au lieu d'un « HTTP Error 400 » générique — les
      refus de modération de contenu sont maintenant clairs (Grok chat, image, vidéo).
  Modifié
    - Retrait d'un script de build tiers (MyNinja) chargé mais inutilisé : plus
      de JS tiers ni de télémétrie sur la page où l'on saisit les clés API.
    - Fichier source renommé de ChatJPT_1_2_0.html à ChatJPT_1_3_0.html.
    - Numéro de version mis à jour à 1.3.0 (en-tête et pied de page, FR/EN).

[1.2.0] — 2026-06-04
  Ajouté
    - Fournisseur DeepSeek (DeepSeek V3 chat, DeepSeek R1 raisonnement),
      streaming compatible OpenAI.
    - Fournisseur Qwen (Alibaba DashScope) : chat (qwen-max/plus/turbo,
      qwen3-max, qwen3-coder-plus) et génération d'images, avec une région
      DashScope au choix (International / Chine continentale).
    - Panneau de clés API repliable avec pastilles de statut par fournisseur
      (clé enregistrée / manquante), affichant désormais le nom de chaque
      fournisseur à côté de sa pastille de couleur.
    - Mode Comparaison : lancez le même prompt sur deux modèles côte à côte
      (tous fournisseurs, groupés par fournisseur), les deux réponses étant
      streamées en parallèle. Gardez celle que vous préférez en un clic — ou
      ignorez les deux ; seule la réponse gardée entre dans l'historique.
      Disponible en modes Chat et Code.
    - Mode Vibe Coder : un mode pour débutants (non-codeurs). Un mentor
      patient qui détecte votre langue, pose une question de clarification à
      la fois, présente un plan d'action en langage simple et ATTEND votre
      accord avant de construire, puis vous guide pas à pas — en pointant les
      boutons aperçu/téléchargement de l'app, en proposant des étapes
      suivantes concrètes et en anticipant les erreurs courantes.
    - Aperçu HTML en direct : toute page HTML complète affiche un bouton 👁
      qui la rend instantanément dans une iframe sandboxée (allow-scripts
      uniquement, sans accès same-origin — le code prévisualisé ne peut pas
      lire vos clés API stockées), avec une option « ouvrir dans un onglet ».
      Disponible dans tous les modes.
  Corrigé
    - Les grosses sorties (pages HTML complètes en un seul fichier) ne sont
      plus tronquées sur Gemini ni sur les fournisseurs compatibles OpenAI
      (DeepSeek, Qwen) : leur budget de tokens de sortie est relevé pour les
      modes générant beaucoup de code.
  Modifié
    - Fichier source renommé de ChatJPT_1_1_1.html à ChatJPT_1_2_0.html.
    - Numéro de version mis à jour à 1.2.0 (en-tête et pied de page, FR/EN).

[1.1.1] — 2026-06-01
  Ajouté
    - Claude Opus 4.8 (claude-opus-4-8) — désormais le modèle Claude
      par défaut et le plus performant.
    - Sélecteur de qualité d'image pour OpenAI (Basse/Moyenne/Haute/Auto).
      La qualité était figée sur « Haute » (le réglage le plus lent) ; elle
      est maintenant par défaut « Moyenne » pour une génération plus rapide
      et reste ajustable par l'utilisateur.
    - Sélecteur de taille d'image pour OpenAI (Carré/Paysage/Portrait/Auto),
      remplaçant le 1024×1024 figé. La qualité et la taille sont sauvegardées
      et affichées uniquement pour OpenAI.
    - Sélecteurs de format (ratio) et de résolution (1K/2K/4K) pour les
      images Gemini, appliqués à Nano Banana et Imagen 4. Sauvegardés et
      affichés uniquement pour Gemini. (Gemini n'a pas de réglage de
      « qualité » Basse/Moyenne/Haute ; la résolution en est l'équivalent.)
    - Notation pouce haut/bas par réponse IA, sauvegardée avec la
      conversation et restaurée au rechargement.
    - Un bandeau « offrez-moi un café » fermable, affiché au plus une fois
      par session et uniquement après un 👍 (jamais après un 👎).
    - Export des seules réponses notées 👍 (chacune précédée de sa
      question), en plus de l'export complet de la conversation.
  Corrigé
    - Génération vidéo OpenAI (Sora) : le menu Durée propose maintenant
      les valeurs réellement acceptées par l'API Sora (8/12/16/20 s) au
      lieu des valeurs Gemini Veo (8/6/4 s), qui étaient rejetées.
    - Le polling vidéo ne reste plus bloqué 20 minutes en silence en cas
      d'erreur API ; la vraie erreur est maintenant affichée après
      quelques tentatives échouées.
    - Sora 2 Pro dispose d'un délai d'attente plus long (~40 min), les
      rendus Pro étant bien plus lents que le modèle rapide ; le message
      de progression ne promet plus un irréaliste « 1-3 min ».
    - Les erreurs vidéo affichent désormais aussi le message exact du
      fournisseur (et le journalisent en console), pour que les refus de
      modération ou de paramètre soient clairs au lieu d'être masqués.
  Modifié
    - Claude Opus 4.7 n'est plus marqué « Dernier » (passé en legacy).
    - Fichier source renommé de ChatJPT_1_1.html à ChatJPT_1_1_1.html.
    - Numéro de version mis à jour à 1.1.1 (en-tête et pied de page, FR/EN).

[1.1] — 2026
  Ajouté
    - Première version publique.
    - Support multi-fournisseurs : OpenAI, Anthropic (Claude), Google (Gemini).
    - Modes Chat, Code, Image et Vidéo.
    - Mode Agent et Mode Thinking.
    - Thème clair / sombre et interface bilingue (FR/EN).
    - Sauvegarde locale des clés API et préférences (aucun serveur).
    - Téléchargement de fichiers (blocs de code, tableaux CSV).

================================================================
