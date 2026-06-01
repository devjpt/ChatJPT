================================================================
  CHANGELOG — ChatJPT
  By Jean-Philippe Theriault — https://www.devjpt.com/
================================================================


----------------------------------------------------------------
  ENGLISH
----------------------------------------------------------------

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
