================================================================
  CHANGELOG — ChatJPT
  By Jean-Philippe Theriault — https://www.devjpt.com/
================================================================


----------------------------------------------------------------
  ENGLISH
----------------------------------------------------------------

[1.14.0] — 2026-10-25
  Added
    - New provider: Mistral AI (France). Models: Mistral Large 4 (preview,
      paid plan), Mistral Medium 3.5 (agents, code), Mistral Small 4 (fast,
      low cost) and Codestral (code). Reasoning can be turned on or off;
      the model's thinking appears in the usual 🧠 block. Images can be
      attached to Large 4 and Medium 3.5. Mistral also works in Compare
      mode and for scanned PDF transcription.
  Changed / Improved
    - API keys are grouped by country: United States, France and China.
      The provider list uses the same groups.
    - Error messages now also show the provider's exact message in
      parentheses (e.g. a rate limit versus a model not included in your
      plan), which makes problems easier to understand.

[1.13.0] — 2026-10-23
  Added
    - The image editor now works with Gemini (Nano Banana), Qwen Image and
      Grok Imagine, not only OpenAI. Edits use the selected provider if it
      can edit images, otherwise OpenAI (or another provider with a key);
      the drawing editor shows which model will be used.
      - Gemini, Qwen and Grok have no mask and no transparent background:
        🧽 Erase sends the area painted in red, and ✂️ Remove background
        asks for a plain green background that is then removed in your
        browser (edges slightly less precise than with OpenAI).
      - An attached photo in Image mode is edited with all four providers.
    - Three new formats in ⬚ Format, as in Grok: Photo 3:2, Cinematic 21:9
      and Banner 5:2 (Banner is hidden for Gemini, which does not support
      it). Grok edits use the resolution chosen in the Image panel.
    - Alibaba: a second key field for the Mainland China region, under the
      International one. The "Region" dropdown picks both the key and the
      server; if only one key is filled in, the region follows it, and a
      warning appears if the chosen region has no key.
    - 🎬 Animate (Grok), under every image: turns it into a 10-second video
      whose first frame is your image, with Grok Imagine Video — always
      Grok, whichever provider is selected, so an xAI key is required (the
      button and its menu say so). Three choices, as in Grok:
      - ✏️ With a prompt: describe the motion in your next message.
      - ⚡ Quick animate: Grok animates the image on its own.
      - 🔁 Loop: your image is pinned again just before the end, so the
        video ends where it starts and loops seamlessly (it also replays
        continuously in the player).
  Fixed
    - Grok: the drawing tools failed on a freshly generated image ("the
      image may no longer be available"). Grok images are now received
      directly instead of through a temporary link, which also keeps them
      in the conversation for good.
    - Qwen (International region): its image storage does not let the
      browser read the pixels. The tools that need them are greyed out
      with an explanation instead of failing; Edit and Format still work.
    - Qwen edits keep the proportions of the source image, and Comment no
      longer leaves the numbered marker in the result.

[1.12.0] — 2026-10-23
  Added
    - Image editor, drawing tools (OpenAI GPT Image). Three new buttons under
      every image open a full-screen editor, with a help tooltip on each
      control:
      - 🧽 Erase: paint over what should go (in translucent red), and
        optionally say what to put there instead. A precise mask of the
        painted area is sent, so only that area changes.
      - 🖍️ Markup: draw on the image (6 colors, adjustable brush) and
        optionally explain your drawings. The model applies the changes and
        removes the annotations.
      - 💬 Comment: click to pin numbered notes on precise spots and write a
        request for each one. Each request is applied at its spot.
    - Every editor has Undo, Clear all, Cancel (or Esc) and Apply (enabled
      once there is something to apply). The result is a new image in the
      conversation that can be edited again; a removed background stays
      transparent.

[1.11.0] — 2026-10-23
  Added
    - Image editor (OpenAI GPT Image 2.5), in a toolbar under every image —
      whichever provider created it — with a help tooltip on each option:
      - ✏️ Edit: the image appears above the input box; your next message
        describes the change (e.g. "add a hat"). The result is a new image
        that can be edited again, so changes can be chained.
      - ✂️ Remove background: cuts out the subject on a transparent
        background (PNG). The transparency is kept in later edits.
      - ⬚ Format: Square 1:1, Portrait 3:4, Story 9:16, Landscape 4:3,
        Widescreen 16:9 — the model fills in the edges without distorting
        the subject.
      - 💾 Download.
    - In Image mode with OpenAI, an attached photo is now edited according to
      your message (it used to be ignored).
    - Transparent images are shown on a checkerboard, so a removed background
      is clearly visible.
  Changed / Improved
    - The image caption and the Download button are now translated (they were
      only in English / French).

[1.10.1] — 2026-10-18
  Added
    - Gemini 4 Argon (gemini-4-argon), Google's new flagship reasoning model
      (1M-token context), now first in the Gemini list. Thinking levels:
      Low, Medium, High. Its output limit is raised to 32,000 tokens
      (64,000 in Code and Vibe Coder modes), since its reasoning counts
      toward that limit. Web search, link reading, Compare mode and scanned
      PDF transcription work with it.

[1.10.0] — 2026-10-17
  Added
    - Scanned PDFs (pages made of images, no text) can now be read. When you
      attach one, a dialog offers two choices, with the cost shown upfront:
      - Transcribe to text (OCR): the selected model reads each page once and
        extracts its text. No page limit (pages are processed three at a
        time), a progress bar with the tokens used so far, a Stop button
        (the pages already done are kept), and the actual cost at the end.
        The text is then attached like a normal PDF, so follow-up questions
        are cheap.
      - Attach the pages as images: the model "sees" the pages (better for
        diagrams), but they are resent with every question (higher cost),
        and some providers refuse more than about 100 pages.
    - Models that cannot read images (DeepSeek, GLM, Qwen Coder…) are
      detected and the dialog explains why. With Perplexity, only the images
      option is offered (each transcription request would run web searches).

[1.9.2] — 2026-10-17
  Security
    - PDF.js (which reads the text of attached PDFs) updated from 3.11.174,
      no longer maintained, to 6.4.299. The new version no longer uses eval,
      which removes the CVE-2024-4367 issue at its root.
    - Both the PDF.js library and its background worker are now checked by
      their SHA-512 fingerprint (cross-checked on two CDNs); a modified file
      is refused. The old version did not check the worker.
  Changed / Improved
    - Faster PDF text extraction (about 3× faster on a 14-page document).
  Note
    - Scanned PDFs (pages made of images) still have no extractable text: the
      model is told the PDF is scanned, as before.

[1.9.1] — 2026-10-17
  Security
    - DOMPurify (which cleans AI answers before display) updated from 3.0.9 to
      3.4.17, fixing known bypasses (e.g. CVE-2024-45801), with a new SRI
      integrity hash.
    - PDF import: PDF.js now runs with isEvalSupported disabled, the official
      mitigation for CVE-2024-4367 (JavaScript execution through a crafted
      PDF font).
    - HTML preview "Open in new tab": the generated page now opens inside a
      sandboxed frame, like the in-chat preview, so it can no longer access
      ChatJPT's storage (API keys).
    - API keys guide: advice to use a separate key with a monthly spending
      limit, and to use ChatJPT on a trusted computer.
  Removed
    - Veo 3.1, Veo 3.1 Lite and Veo 3.1 Fast (Google shuts them down on
      2026-10-22). Gemini video now uses Gemini Omni 1.1 Flash.

[1.9.0] — 2026-10-17
  Added
    - New provider: Perplexity (Agent API). Answers always search the web and
      list their sources. Five levels, from fastest to deepest: Quick search
      (Fast), Search (Standard), Multi-source research (Medium), Deep research
      (High, several minutes) and Advanced research agent (X-High, very slow
      and costly).
    - The 🧠 block shows the research as it happens: the model's thoughts, the
      searches it runs (🔎) and the pages it opens (🌐).
    - Citation markers in the answer become small clickable links (¹ ²) to the
      matching source, and the sources are listed under the answer.
    - Works in Compare mode. The API keys guide has a new Perplexity section.

[1.8.2] — 2026-10-17
  Added
    - Z.ai GLM models: GLM-5.3 (always-on reasoning, shown in the 🧠 block),
      GLM-5.2 and GLM-5.1 (thinking toggle). They are served by Alibaba Cloud
      Model Studio with the same API key as Qwen. Z.ai's own API cannot be used
      from a browser (it blocks browser requests, CORS), so Alibaba is the way
      to use GLM in ChatJPT.
  Changed / Improved
    - The "Qwen (Alibaba)" provider is renamed "Alibaba (Qwen, GLM)". Your saved
      key and settings are kept.

[1.8.1] — 2026-10-16
  Added
    - Qwen: Qwen3.7 Max, Qwen3.7 Flash (very low cost), Qwen Flash and Qwen3
      Coder Flash. Thinking mode is available on Qwen3.7 Max, Qwen3.7 Flash and
      Qwen Flash.
    - Qwen images: Qwen Image 3.0 (faster, cheaper than 3.0 Pro), Qwen Image 2.1
      Pro and Qwen Image 2.1 Turbo (low cost).
  Removed
    - Qwen models no longer listed in the current Qwen catalog: Qwen Turbo
      (replaced by Qwen Flash), Qwen3 Max, Qwen3 Coder Plus (replaced by Qwen3
      Coder Flash) and Qwen Image Max.

[1.8.0] — 2026-10-06
  Added
    - Claude: Fable 5.1 (latest), Opus 5.5, Sonnet 5.5, Opus 5 and Sonnet 5. On
      models with always-on adaptive thinking, a readable summary of the
      reasoning is shown in the 🧠 block, and an effort selector (low → max)
      replaces the old token budget.
    - OpenAI: GPT-6 Astra (latest), GPT-6.1 Sol and GPT-6 Luna, routed through the
      Responses API so a summary of their reasoning is shown. Images: GPT Image
      2.5 Sunburst (quality) and Flare (fast).
    - Gemini: 3.8 Flash (latest), 3.7 Flash, 3.6 Flash and 3.5 Flash Lite.
      Images: Nano Banana 2.1 (latest) and Nano Banana 2 Lite. Video: Gemini Omni
      1.1 Flash (with generated audio), through the new Interactions API.
    - Grok: 4.7 (latest), 4.6 and 4.5, with visible reasoning (through the xAI
      Responses API) and an effort selector. Images: Grok Imagine 2.0. Video:
      Grok Imagine Video 1.5 and 1.5 Lite.
    - DeepSeek: V4 Pro and Flash, with a real thinking on/off toggle and an
      adjustable depth (reasoning effort).
    - Qwen: Qwen3.8 Max (latest), Qwen3.7 Plus and Qwen3.8 Flash. Thinking mode
      now works for Qwen (shown in the 🧠 block, with a thinking budget). Images:
      Qwen Image 3.0 Pro.
    - A clear message is shown when Claude declines a request (safety filter),
      instead of an empty reply.
  Changed / Improved
    - Higher output limit for models whose reasoning counts toward it (adaptive
      Claude, GPT-6, Grok 4.5+, DeepSeek with thinking), so long answers are no
      longer cut off.
    - Gemini 3.8 / 3.7 Flash: the "Minimal" thinking level, rejected by these
      models, is hidden.
    - Gemini Nano Banana 2 and Nano Banana Pro now use their stable model IDs.
    - Veo 3.1 models are labeled with their end date (Google shuts them down on
      2026-10-22; Gemini Omni replaces them).
  Removed
    - Models shut down (or about to be) by their providers: DeepSeek V3 / R1
      (deepseek-chat, deepseek-reasoner), Claude Opus 4.1, o3-pro, GPT Image 1.5
      and 1 Mini, Imagen 4, Veo 2.0, and the Gemini image previews.
    - OpenAI video (Sora 2): OpenAI shut down Sora 2 and its Videos API on
      2026-09-24, with no replacement. The Video tab is now disabled for OpenAI.
  Fixed
    - The "Show" button of the reasoning block never displayed the reasoning
      (for any provider). It now expands and collapses correctly.

[1.7.1] — 2026-06-09
  Added
    - Claude Fable 5 (claude-fable-5), Anthropic's most capable widely released
      model (1M-token context), added to the Claude model list and shown as the
      latest. It uses always-on adaptive thinking (no configurable thinking
      toggle). Web search and link reading work with it like other Claude models.

[1.7.0] — 2026-06-08
  Added
    - Read pasted links (optional toggle 🔗, off by default, separate from web
      search): the model opens and reads the actual content of the URL(s) you
      paste in your message, instead of guessing from the address. The fetched
      page is shown as a clickable source. The fetching happens on the provider's
      server (no CORS), so it works directly from the browser. A hint warns it
      uses more tokens (it reads the whole page). Available for Gemini
      (url_context tool), Claude (web_fetch tool), OpenAI and Grok (web_search
      tool, which also opens a specific URL). Not available for DeepSeek/Qwen
      (no link-reading tool). Also available in Compare mode.
  Changed / Improved
    - Link reading is reliable for OpenAI and Grok: those APIs have no dedicated
      URL-reading primitive (only web_search, which "decides" whether to open a
      page — previously intermittent). When reading a link (without a broad web
      search), the search is now restricted to the pasted URL's domain(s) via
      allowed_domains, forcing the model to open that exact page.

[1.6.2] — 2026-06-07
  Changed / Improved
    - Chart type labels are now fully localized (FR/EN/ES): the visible badge and
      the accessible name (aria-label) show the translated chart-type name
      (e.g. "Bar Chart" / "Graphique à barres" / "Gráfico de barras").

[1.6.1] — 2026-06-07
  Added
    - Spanish (Latin American) added as a third interface language. The language
      button now cycles FR → EN → ES and shows the current language. All UI
      strings, model labels and the Vibe Coder examples are translated; the
      README, API keys guide, LICENSE and this changelog include a Spanish
      section.

[1.6.0] — 2026-06-07
  Added
    - Token counter: each response shows its exact token usage (↑ input /
      ↓ output, as reported by the API), plus a per-conversation total in the
      footer bar. Tokens only (no price estimate). Helps see what each turn
      really costs.
    - Web search + Sources (optional toggle 🌐, off by default): the model
      searches the web in real time and the answer is followed by a collapsible
      "Sources" list (whole row clickable, readable label or domain). Available
      for Gemini (Google Search grounding), Grok (xAI Agent Tools / Responses
      API), Claude (web_search tool) and OpenAI (web_search via Responses API).
      A hint warns it uses more tokens (+ search fees). Sources persist across
      reloads. The toggle ("🌐 Web search + sources") is also available in
      Compare mode (each compared model uses it only if its provider supports
      it). Not available for DeepSeek (no native search) or Qwen (DashScope
      does not expose sources in OpenAI-compatible mode).
  Fixed
    - Compare mode: clearing the chat (or switching/creating a conversation)
      while a compare choice was still pending no longer blocks sending — the
      pending state is reset and any in-flight streams are aborted (previously
      required a page reload).
    - Charts are now produced only when a visualization is explicitly requested:
      a weak model could previously return a chart instead of a plain-text
      answer (clearer guard added to the chart system prompt).

[1.5.1] — 2026-06-07
  Added
    - Edit an AI response (✎): replace its text in place; it is re-rendered
      (code, tables, charts) with no regeneration or truncation. The corrected
      text becomes the context for the rest of the conversation. (Enter inserts a
      newline; Ctrl/Cmd+Enter saves.)

[1.5.0] — 2026-06-06
  Added
    - Image persistence (IndexedDB): generated images now survive page reloads
      and conversation switches. Image-mode turns are recorded in the
      conversation (so they appear in the list, search and export). Stored
      locally outside the localStorage quota; download (💾) remains the durable
      backup.
    - Thumbs-down now acts on the AI: a passive note tells the model the answer
      was unsatisfactory (it self-corrects on the next turn), and an "↻ Improve"
      box (with an optional reason) regenerates an informed, better answer.
    - Thumbs-up likewise signals the model to keep that approach.
    - "Report a bug" link inside the thumbs-down box, with a clarifying prompt
      to distinguish an app bug from a merely unsatisfying answer.

[1.4.1] — 2026-06-06
  Added
    - "Scroll to bottom" button: appears when you scroll up to re-read during
      streaming; one click returns to the latest message.
    - Rename a conversation: double-click its title in the drawer (Enter to
      confirm, Esc to cancel, empty restores the automatic title).
  Changed / Improved
    - Internal refactor: the five provider streaming functions now share a
      common postStream() core, and output token limits are centralized
      (TOKEN_LIMITS). No behavior change.

[1.4.0] — 2026-06-06
  Added
    - Multiple conversations: a left drawer (☰) to create, switch between,
      delete, and export all conversations. Key-per-conversation storage with
      automatic migration of the previous single conversation. The oldest are
      never silently deleted: generation is blocked with a clear message
      (delete/export) before the browser storage limit is reached.
    - In-conversation search (🔍): highlights matches with previous/next
      navigation; case- and accent-insensitive.
    - Edit a sent message (✎): the conversation is truncated from that point
      and the AI answers the corrected prompt.
    - Regenerate a response with another model (🔀): same prompt, different
      model, for quick comparison.
    - Keyboard shortcut: Esc stops the current generation.
  Changed / Improved
    - Streaming: sticky auto-scroll — scrolling up to re-read no longer fights
      the auto-scroll; syntax highlighting is deferred to the final render
      (much smoother streaming on large code blocks).
    - Charts now scale down to fit small screens (no overflow); each chart
      canvas has an accessible name (role=img + aria-label).

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

[1.14.0] — 2026-10-25
  Ajouté
    - Nouveau fournisseur : Mistral AI (France). Modèles : Mistral Large 4
      (aperçu, forfait payant), Mistral Medium 3.5 (agents, code), Mistral
      Small 4 (rapide, économique) et Codestral (code). La réflexion
      s'active ou se désactive ; elle s'affiche dans le bloc 🧠 habituel.
      Des images peuvent être jointes à Large 4 et Medium 3.5. Mistral
      fonctionne aussi en mode comparaison et pour la transcription des
      PDF scannés.
  Modifié / Amélioré
    - Les clés API sont regroupées par pays : États-Unis, France et Chine.
      La liste des fournisseurs utilise les mêmes groupes.
    - Les messages d'erreur affichent aussi, entre parenthèses, le message
      exact du fournisseur (par exemple une limite de débit plutôt qu'un
      modèle non inclus dans votre forfait), pour mieux comprendre le
      problème.

[1.13.0] — 2026-10-23
  Ajouté
    - L'éditeur d'image fonctionne maintenant avec Gemini (Nano Banana),
      Qwen Image et Grok Imagine, plus seulement OpenAI. L'édition passe par
      le fournisseur sélectionné s'il sait éditer les images, sinon par
      OpenAI (ou un autre fournisseur qui a une clé) ; l'éditeur de dessin
      indique le modèle utilisé.
      - Gemini, Qwen et Grok n'ont ni masque ni fond transparent : 🧽 Effacer
        envoie la zone peinte en rouge, et ✂️ Retirer le fond demande un fond
        vert uni, retiré ensuite dans votre navigateur (contours un peu moins
        fins qu'avec OpenAI).
      - En mode Image, une photo jointe est modifiée avec les quatre
        fournisseurs.
    - Trois nouveaux formats dans ⬚ Format, comme dans Grok : Photo 3:2,
      Cinéma 21:9 et Bannière 5:2 (Bannière masquée pour Gemini, qui ne la
      prend pas en charge). Les éditions Grok utilisent la résolution
      choisie dans le panneau Image.
    - Alibaba : un second champ de clé pour la région Chine continentale,
      sous celui de la région International. Le menu « Région » choisit à
      la fois la clé et le serveur ; si une seule clé est saisie, la région
      la suit, et un avertissement s'affiche si la région choisie n'a pas
      de clé.
    - 🎬 Animer (Grok), sous chaque image : la transforme en vidéo de
      10 secondes dont la première image est la vôtre, avec Grok Imagine
      Vidéo — toujours Grok, quel que soit le fournisseur sélectionné, donc
      une clé xAI est requise (le bouton et son menu l'indiquent). Trois
      choix, comme dans Grok :
      - ✏️ Avec une consigne : décrivez le mouvement dans le message suivant.
      - ⚡ Animation rapide : Grok anime l'image tout seul.
      - 🔁 Boucle : votre image est de nouveau imposée juste avant la fin, la
        vidéo finit donc là où elle commence et boucle sans coupure (elle se
        répète aussi en continu dans le lecteur).
  Corrigé
    - Grok : les outils de dessin échouaient sur une image tout juste
      générée (« l'image n'est peut-être plus disponible »). Les images Grok
      sont maintenant reçues directement plutôt que par un lien temporaire,
      ce qui les conserve aussi pour de bon dans la conversation.
    - Qwen (région International) : son stockage d'images interdit au
      navigateur d'en lire les pixels. Les outils qui en ont besoin sont
      grisés avec une explication au lieu d'échouer ; Modifier et Format
      fonctionnent toujours.
    - Les éditions Qwen gardent les proportions de l'image source, et
      Commenter ne laisse plus le marqueur numéroté dans le résultat.

[1.12.0] — 2026-10-23
  Ajouté
    - Éditeur d'image, outils de dessin (OpenAI GPT Image). Trois nouveaux
      boutons sous chaque image ouvrent un éditeur plein écran, avec une
      infobulle d'aide sur chaque contrôle :
      - 🧽 Effacer : peignez sur ce qui doit disparaître (en rouge
        translucide) et, si vous voulez, dites quoi mettre à la place. Un
        masque précis de la zone peinte est envoyé : seule cette zone change.
      - 🖍️ Annoter : dessinez sur l'image (6 couleurs, pinceau réglable) et,
        si besoin, expliquez vos dessins. Le modèle applique les changements
        et retire les annotations.
      - 💬 Commenter : cliquez pour épingler des notes numérotées à des
        endroits précis et écrivez une demande pour chacune. Chaque demande
        est appliquée à son endroit.
    - Chaque éditeur a Annuler le dernier trait, Tout effacer, Annuler (ou
      Échap) et Appliquer (actif dès qu'il y a quelque chose à appliquer). Le
      résultat est une nouvelle image dans la conversation, elle-même
      modifiable ; un fond retiré reste transparent.

[1.11.0] — 2026-10-23
  Ajouté
    - Éditeur d'image (OpenAI GPT Image 2.5), dans une barre d'outils sous
      chaque image — quel que soit le fournisseur qui l'a créée — avec une
      infobulle d'aide sur chaque option :
      - ✏️ Modifier : l'image s'affiche au-dessus de la zone de saisie ; votre
        message suivant décrit le changement (ex. « ajoute un chapeau »). Le
        résultat est une nouvelle image, elle-même modifiable : les
        modifications s'enchaînent.
      - ✂️ Retirer le fond : détoure le sujet sur fond transparent (PNG). La
        transparence est conservée lors des modifications suivantes.
      - ⬚ Format : Carré 1:1, Portrait 3:4, Story 9:16, Paysage 4:3, Grand
        écran 16:9 — le modèle complète les bords sans déformer le sujet.
      - 💾 Télécharger.
    - En mode Image avec OpenAI, une photo jointe est désormais modifiée selon
      votre message (elle était ignorée auparavant).
    - Les images transparentes s'affichent sur un damier : un fond retiré est
      clairement visible.
  Modifié / Amélioré
    - La légende des images et le bouton Télécharger sont maintenant traduits
      (ils n'existaient qu'en anglais / français).

[1.10.1] — 2026-10-18
  Ajouté
    - Gemini 4 Argon (gemini-4-argon), le nouveau modèle phare de raisonnement
      de Google (contexte de 1M tokens), désormais en tête de la liste Gemini.
      Niveaux de réflexion : Léger, Modéré, Profond. Sa limite de sortie est
      relevée à 32 000 tokens (64 000 en modes Code et Vibe Coder), car sa
      réflexion compte dans cette limite. La recherche web, la lecture de
      liens, le mode Comparaison et la transcription des PDF scannés
      fonctionnent avec lui.

[1.10.0] — 2026-10-17
  Ajouté
    - Les PDF scannés (pages composées d'images, sans texte) peuvent maintenant
      être lus. Quand vous en joignez un, une fenêtre propose deux choix, avec
      le coût affiché à l'avance :
      - Transcrire en texte (OCR) : le modèle sélectionné lit chaque page une
        seule fois et en extrait le texte. Aucune limite de pages (traitées
        trois par trois), une barre de progression avec les tokens déjà
        utilisés, un bouton Arrêter (les pages déjà faites sont conservées) et
        le coût réel à la fin. Le texte est ensuite joint comme un PDF normal :
        les questions suivantes coûtent peu.
      - Joindre les pages comme images : le modèle « voit » les pages (mieux
        pour les schémas), mais elles sont renvoyées à chaque question (coût
        plus élevé), et certains fournisseurs refusent au-delà d'environ
        100 pages.
    - Les modèles qui ne lisent pas les images (DeepSeek, GLM, Qwen Coder…)
      sont détectés et la fenêtre explique pourquoi. Avec Perplexity, seule
      l'option images est proposée (chaque requête de transcription lancerait
      des recherches web).

[1.9.2] — 2026-10-17
  Sécurité
    - PDF.js (qui lit le texte des PDF joints) passe de la 3.11.174, qui n'est
      plus maintenue, à la 6.4.299. La nouvelle version n'utilise plus eval, ce
      qui supprime à la racine le problème CVE-2024-4367.
    - La bibliothèque PDF.js et son worker (traitement en arrière-plan) sont
      désormais vérifiés par leur empreinte SHA-512 (recoupée sur deux CDN) ;
      un fichier modifié est refusé. L'ancienne version ne vérifiait pas le
      worker.
  Modifié / Amélioré
    - Extraction du texte des PDF plus rapide (environ 3× sur un document de
      14 pages).
  Note
    - Les PDF scannés (pages composées d'images) n'ont toujours pas de texte
      extractible : le modèle est prévenu que le PDF est scanné, comme avant.

[1.9.1] — 2026-10-17
  Sécurité
    - DOMPurify (qui nettoie les réponses des IA avant affichage) passe de la
      3.0.9 à la 3.4.17, ce qui corrige des contournements connus (ex.
      CVE-2024-45801), avec une nouvelle empreinte d'intégrité SRI.
    - Import de PDF : PDF.js fonctionne désormais avec isEvalSupported
      désactivé, la parade officielle à CVE-2024-4367 (exécution de
      JavaScript via une police de PDF piégée).
    - Aperçu HTML « Ouvrir dans un onglet » : la page générée s'ouvre
      maintenant dans un cadre sandboxé, comme l'aperçu intégré au chat ; elle
      ne peut plus accéder au stockage de ChatJPT (clés API).
    - Guide des clés API : conseil d'utiliser une clé distincte avec un
      plafond de dépenses mensuel, et d'utiliser ChatJPT sur un ordinateur de
      confiance.
  Retiré
    - Veo 3.1, Veo 3.1 Lite et Veo 3.1 Fast (arrêtés par Google le
      2026-10-22). La vidéo Gemini utilise désormais Gemini Omni 1.1 Flash.

[1.9.0] — 2026-10-17
  Ajouté
    - Nouveau fournisseur : Perplexity (Agent API). Les réponses cherchent
      toujours sur le web et citent leurs sources. Cinq niveaux, du plus rapide
      au plus approfondi : Recherche éclair (Fast), Recherche (Standard),
      Recherche multi-sources (Medium), Recherche approfondie (High, plusieurs
      minutes) et Agent de recherche avancé (X-High, très lent et coûteux).
    - Le bloc 🧠 montre la recherche en direct : les réflexions du modèle, les
      recherches lancées (🔎) et les pages ouvertes (🌐).
    - Les marqueurs de citation dans la réponse deviennent de petits liens
      cliquables (¹ ²) vers la source correspondante, et les sources sont
      listées sous la réponse.
    - Fonctionne en mode Comparaison. Le guide des clés API a une nouvelle
      section Perplexity.

[1.8.2] — 2026-10-17
  Ajouté
    - Modèles GLM de Z.ai : GLM-5.3 (réflexion toujours active, affichée dans le
      bloc 🧠), GLM-5.2 et GLM-5.1 (case thinking). Ils sont servis par Alibaba
      Cloud Model Studio, avec la même clé API que Qwen. L'API de Z.ai elle-même
      n'est pas utilisable depuis un navigateur (elle bloque les requêtes du
      navigateur, CORS) : passer par Alibaba est la façon d'utiliser GLM dans
      ChatJPT.
  Modifié / Amélioré
    - Le fournisseur « Qwen (Alibaba) » est renommé « Alibaba (Qwen, GLM) ». Votre
      clé et vos réglages enregistrés sont conservés.

[1.8.1] — 2026-10-16
  Ajouté
    - Qwen : Qwen3.7 Max, Qwen3.7 Flash (très économique), Qwen Flash et Qwen3
      Coder Flash. Le mode thinking est disponible sur Qwen3.7 Max, Qwen3.7 Flash
      et Qwen Flash.
    - Images Qwen : Qwen Image 3.0 (plus rapide et moins cher que 3.0 Pro), Qwen
      Image 2.1 Pro et Qwen Image 2.1 Turbo (économique).
  Retiré
    - Modèles Qwen absents du catalogue Qwen actuel : Qwen Turbo (remplacé par
      Qwen Flash), Qwen3 Max, Qwen3 Coder Plus (remplacé par Qwen3 Coder Flash)
      et Qwen Image Max.

[1.8.0] — 2026-10-06
  Ajouté
    - Claude : Fable 5.1 (dernier), Opus 5.5, Sonnet 5.5, Opus 5 et Sonnet 5. Sur
      les modèles à adaptive thinking toujours actif, un résumé lisible de la
      réflexion s'affiche dans le bloc 🧠, et un sélecteur d'effort (léger →
      maximum) remplace l'ancien budget de tokens.
    - OpenAI : GPT-6 Astra (dernier), GPT-6.1 Sol et GPT-6 Luna, passant par
      l'API Responses pour afficher un résumé de leur réflexion. Images : GPT
      Image 2.5 Sunburst (qualité) et Flare (rapide).
    - Gemini : 3.8 Flash (dernier), 3.7 Flash, 3.6 Flash et 3.5 Flash Lite.
      Images : Nano Banana 2.1 (dernier) et Nano Banana 2 Lite. Vidéo : Gemini
      Omni 1.1 Flash (avec audio généré), via la nouvelle Interactions API.
    - Grok : 4.7 (dernier), 4.6 et 4.5, avec réflexion visible (via l'API
      Responses de xAI) et sélecteur d'effort. Images : Grok Imagine 2.0. Vidéo :
      Grok Imagine Vidéo 1.5 et 1.5 Lite.
    - DeepSeek : V4 Pro et Flash, avec une vraie case thinking (activé /
      désactivé) et une profondeur réglable (reasoning effort).
    - Qwen : Qwen3.8 Max (dernier), Qwen3.7 Plus et Qwen3.8 Flash. Le mode
      thinking fonctionne désormais pour Qwen (affiché dans le bloc 🧠, avec un
      budget de réflexion). Images : Qwen Image 3.0 Pro.
    - Un message clair s'affiche quand Claude décline une demande (filtre de
      sécurité), au lieu d'une réponse vide.
  Modifié / Amélioré
    - Limite de sortie relevée pour les modèles dont la réflexion compte dans
      cette limite (Claude adaptatif, GPT-6, Grok 4.5+, DeepSeek avec thinking) :
      les longues réponses ne sont plus coupées.
    - Gemini 3.8 / 3.7 Flash : le niveau de réflexion « Minimal », refusé par ces
      modèles, est masqué.
    - Gemini Nano Banana 2 et Nano Banana Pro utilisent désormais leurs
      identifiants stables.
    - Les modèles Veo 3.1 indiquent leur date de fin (Google les arrête le
      2026-10-22 ; Gemini Omni les remplace).
  Retiré
    - Modèles arrêtés (ou sur le point de l'être) par leur fournisseur :
      DeepSeek V3 / R1 (deepseek-chat, deepseek-reasoner), Claude Opus 4.1,
      o3-pro, GPT Image 1.5 et 1 Mini, Imagen 4, Veo 2.0 et les previews d'images
      Gemini.
    - Vidéo OpenAI (Sora 2) : OpenAI a arrêté Sora 2 et son API Videos le
      2026-09-24, sans remplaçant. L'onglet Vidéo est désormais désactivé pour
      OpenAI.
  Corrigé
    - Le bouton « Afficher » du bloc de réflexion n'affichait jamais la réflexion
      (pour tous les fournisseurs). Il déplie et replie maintenant correctement.

[1.7.1] — 2026-06-09
  Ajouté
    - Claude Fable 5 (claude-fable-5), le modèle le plus capable d'Anthropic en
      disponibilité générale (contexte 1M tokens), ajouté à la liste des modèles
      Claude et affiché comme le dernier. Il utilise un adaptive thinking toujours
      actif (pas de case de réflexion configurable). La recherche web et la lecture
      de liens fonctionnent comme pour les autres modèles Claude.

[1.7.0] — 2026-06-08
  Ajouté
    - Lire les liens collés (case optionnelle 🔗, désactivée par défaut, distincte
      de la recherche web) : le modèle ouvre et lit le contenu réel de la ou des
      URL que vous collez dans votre message, au lieu de deviner d'après l'adresse.
      La page lue est affichée comme source cliquable. La récupération se fait sur
      le serveur du fournisseur (aucun CORS), donc ça fonctionne directement depuis
      le navigateur. Un avertissement signale que ça consomme plus de tokens (il
      lit toute la page). Disponible pour Gemini (outil url_context), Claude (outil
      web_fetch), OpenAI et Grok (outil web_search, qui sait aussi ouvrir une URL
      précise). Indisponible pour DeepSeek/Qwen (pas d'outil de lecture). Disponible
      aussi en mode comparaison.
  Modifié / Amélioré
    - Lecture de lien fiable pour OpenAI et Grok : ces API n'ont pas de primitive
      de lecture d'URL dédiée (seulement web_search, qui « décide » d'ouvrir une
      page ou non — lecture auparavant intermittente). En lecture de lien (sans
      recherche web large), la recherche est désormais restreinte au(x) domaine(s)
      de l'URL collée via allowed_domains, forçant le modèle à ouvrir cette page.

[1.6.2] — 2026-06-07
  Modifié / Amélioré
    - Les libellés de types de graphiques sont désormais entièrement localisés
      (FR/EN/ES) : le badge visible et le nom accessible (aria-label) affichent le
      nom traduit du type (ex. « Graphique à barres » / « Bar Chart » / « Gráfico
      de barras »).

[1.6.1] — 2026-06-07
  Ajouté
    - Espagnol (latino-américain) ajouté comme troisième langue d'interface. Le
      bouton de langue cycle désormais FR → EN → ES et affiche la langue
      actuelle. Toutes les chaînes de l'UI, les libellés de modèles et les
      exemples Vibe Coder sont traduits ; le README, le guide des clés API, la
      LICENSE et ce changelog comportent une section espagnole.

[1.6.0] — 2026-06-07
  Ajouté
    - Compteur de tokens : chaque réponse affiche sa consommation exacte
      (↑ entrée / ↓ sortie, telle que rapportée par l'API), plus un total par
      conversation dans la barre du bas. Tokens uniquement (pas d'estimation en
      $). Permet de voir ce que coûte réellement chaque échange.
    - Recherche web + Sources (toggle optionnel 🌐, désactivé par défaut) : le
      modèle cherche le web en temps réel et la réponse est suivie d'une liste
      « Sources » repliable (ligne entièrement cliquable, libellé lisible ou
      domaine). Disponible pour Gemini (grounding Google Search), Grok (xAI
      Agent Tools / API Responses), Claude (outil web_search) et OpenAI
      (web_search via l'API Responses). Une mention prévient que ça consomme
      plus de tokens (+ frais de recherche). Les sources persistent après
      rechargement. Le toggle (« 🌐 Recherche web + sources ») est aussi
      disponible en mode Comparaison (chaque modèle comparé l'utilise seulement
      si son fournisseur le supporte). Indisponible pour DeepSeek (pas de
      recherche native) et Qwen (DashScope n'expose pas les sources en mode
      compatible OpenAI).
  Corrigé
    - Mode comparaison : effacer le chat (ou changer/créer une conversation)
      alors qu'un choix de comparaison était encore en attente ne bloque plus
      l'envoi — l'état en attente est réinitialisé et les flux en cours sont
      arrêtés (il fallait auparavant recharger la page).
    - Les graphiques ne sont produits que lorsqu'une visualisation est
      explicitement demandée : un petit modèle pouvait auparavant renvoyer un
      graphique au lieu d'une réponse en texte (garde-fou ajouté au prompt).

[1.5.1] — 2026-06-07
  Ajouté
    - Édition d'une réponse de l'IA (✎) : remplace son texte sur place ; elle est
      re-rendue (code, tableaux, graphiques), sans régénération ni troncature. Le
      texte corrigé devient le contexte pour la suite. (Entrée = nouvelle ligne ;
      Ctrl/Cmd+Entrée = enregistrer.)

[1.5.0] — 2026-06-06
  Ajouté
    - Persistance des images (IndexedDB) : les images générées survivent
      désormais aux rechargements et aux changements de conversation. Les tours
      du mode image sont enregistrés dans la conversation (donc visibles dans la
      liste, la recherche et l'export). Stockées localement hors du quota
      localStorage ; le téléchargement (💾) reste la sauvegarde durable.
    - Le pouce 👎 agit sur l'IA : une note passive signale au modèle que la
      réponse n'a pas convenu (il se corrige au tour suivant), et une boîte
      « ↻ Améliorer » (raison facultative) régénère une meilleure réponse
      informée.
    - Le pouce 👍 signale de même au modèle de garder cette approche.
    - Lien « signaler un bug » dans la boîte du 👎, avec une confirmation pour
      distinguer un bug de l'app d'une simple réponse insatisfaisante.

[1.4.1] — 2026-06-06
  Ajouté
    - Bouton « revenir en bas » : apparaît quand on remonte lire pendant le
      streaming ; un clic ramène au dernier message.
    - Renommer une conversation : double-clic sur son titre dans le panneau
      (Entrée pour valider, Échap pour annuler, vide = titre auto).
  Modifié / Amélioré
    - Refactor interne : les cinq fonctions de streaming partagent un tronc
      commun postStream(), et les plafonds de tokens sont centralisés
      (TOKEN_LIMITS). Comportement inchangé.

[1.4.0] — 2026-06-06
  Ajouté
    - Conversations multiples : un panneau latéral (☰) pour créer, basculer,
      supprimer et tout exporter. Stockage clé-par-conversation avec migration
      automatique de l'ancienne conversation unique. Les plus anciennes ne
      sont jamais effacées en silence : la génération est bloquée avec un
      message clair (supprimer/exporter) avant d'atteindre la limite du
      navigateur.
    - Recherche dans la conversation (🔍) : surligne les correspondances avec
      navigation précédent/suivant ; insensible à la casse et aux accents.
    - Édition d'un message envoyé (✎) : la conversation est tronquée à partir
      de ce point et l'IA répond au prompt corrigé.
    - Régénérer une réponse avec un autre modèle (🔀) : même prompt, modèle
      différent, pour comparer rapidement.
    - Raccourci clavier : Échap arrête la génération en cours.
  Modifié / Amélioré
    - Streaming : auto-défilement « collant » — remonter lire ne se bat plus
      avec le défilement ; la coloration syntaxique est différée au rendu
      final (streaming bien plus fluide sur les gros blocs de code).
    - Les graphiques se réduisent pour tenir sur petit écran (plus de
      débordement) ; chaque canvas a un nom accessible (role=img + aria-label).

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


----------------------------------------------------------------
  ESPAÑOL
----------------------------------------------------------------

[1.14.0] — 2026-10-25
  Añadido
    - Nuevo proveedor: Mistral AI (Francia). Modelos: Mistral Large 4
      (vista previa, plan de pago), Mistral Medium 3.5 (agentes, código),
      Mistral Small 4 (rápido, económico) y Codestral (código). El
      razonamiento se activa o desactiva; aparece en el bloque 🧠
      habitual. Se pueden adjuntar imágenes a Large 4 y Medium 3.5.
      Mistral también funciona en modo comparación y para la
      transcripción de PDF escaneados.
  Cambiado / Mejorado
    - Las claves API se agrupan por país: Estados Unidos, Francia y
      China. La lista de proveedores usa los mismos grupos.
    - Los mensajes de error también muestran, entre paréntesis, el mensaje
      exacto del proveedor (por ejemplo, un límite de solicitudes frente a
      un modelo no incluido en tu plan), para entender mejor el problema.

[1.13.0] — 2026-10-23
  Añadido
    - El editor de imágenes ahora funciona con Gemini (Nano Banana), Qwen
      Image y Grok Imagine, no solo con OpenAI. La edición usa el proveedor
      seleccionado si edita imágenes; si no, OpenAI (u otro proveedor con
      clave). El editor de dibujo indica qué modelo se usará.
      - Gemini, Qwen y Grok no tienen máscara ni fondo transparente:
        🧽 Borrar envía la zona pintada de rojo, y ✂️ Quitar el fondo pide un
        fondo verde liso que luego se quita en tu navegador (bordes algo
        menos precisos que con OpenAI).
      - En modo Imagen, una foto adjunta se edita con los cuatro
        proveedores.
    - Tres formatos nuevos en ⬚ Formato, como en Grok: Foto 3:2, Cine 21:9 y
      Banner 5:2 (Banner se oculta para Gemini, que no lo admite). Las
      ediciones con Grok usan la resolución elegida en el panel Imagen.
    - Alibaba: un segundo campo de clave para la región China continental,
      debajo del de la región Internacional. El menú "Región" elige a la
      vez la clave y el servidor; si solo hay una clave, la región la sigue,
      y aparece un aviso si la región elegida no tiene clave.
    - 🎬 Animar (Grok), debajo de cada imagen: la convierte en un video de
      10 segundos cuyo primer cuadro es tu imagen, con Grok Imagine Video —
      siempre Grok, sea cual sea el proveedor seleccionado, así que se
      requiere una clave de xAI (el botón y su menú lo indican). Tres
      opciones, como en Grok:
      - ✏️ Con una indicación: describe el movimiento en tu próximo mensaje.
      - ⚡ Animación rápida: Grok anima la imagen por sí solo.
      - 🔁 Bucle: tu imagen se fija de nuevo justo antes del final, así el
        video termina donde empieza y se repite sin cortes (también se
        reproduce en bucle en el reproductor).
  Corregido
    - Grok: las herramientas de dibujo fallaban con una imagen recién
      generada ("la imagen quizá ya no esté disponible"). Las imágenes de
      Grok ahora se reciben directamente en lugar de por un enlace temporal,
      lo que además las conserva en la conversación.
    - Qwen (región Internacional): su almacenamiento de imágenes no deja que
      el navegador lea los píxeles. Las herramientas que los necesitan
      aparecen en gris con una explicación en lugar de fallar; Editar y
      Formato siguen funcionando.
    - Las ediciones con Qwen conservan las proporciones de la imagen de
      origen, y Comentar ya no deja el marcador numerado en el resultado.

[1.12.0] — 2026-10-23
  Añadido
    - Editor de imágenes, herramientas de dibujo (OpenAI GPT Image). Tres
      botones nuevos debajo de cada imagen abren un editor a pantalla
      completa, con una ayuda emergente en cada control:
      - 🧽 Borrar: pinta sobre lo que debe desaparecer (en rojo translúcido)
        y, si quieres, di qué poner en su lugar. Se envía una máscara precisa
        de la zona pintada: solo esa zona cambia.
      - 🖍️ Anotar: dibuja sobre la imagen (6 colores, pincel ajustable) y, si
        hace falta, explica tus dibujos. El modelo aplica los cambios y quita
        las anotaciones.
      - 💬 Comentar: haz clic para fijar notas numeradas en puntos precisos y
        escribe un pedido para cada una. Cada pedido se aplica en su lugar.
    - Cada editor tiene Deshacer, Borrar todo, Cancelar (o Esc) y Aplicar
      (activo en cuanto hay algo que aplicar). El resultado es una nueva
      imagen en la conversación, que también se puede editar; un fondo
      quitado sigue transparente.

[1.11.0] — 2026-10-23
  Añadido
    - Editor de imágenes (OpenAI GPT Image 2.5), en una barra de herramientas
      debajo de cada imagen — sin importar qué proveedor la creó — con una
      ayuda emergente en cada opción:
      - ✏️ Editar: la imagen aparece sobre el cuadro de texto; tu próximo
        mensaje describe el cambio (p. ej. "agrega un sombrero"). El resultado
        es una nueva imagen que también se puede editar: los cambios se
        encadenan.
      - ✂️ Quitar el fondo: recorta el sujeto sobre un fondo transparente
        (PNG). La transparencia se conserva en las ediciones siguientes.
      - ⬚ Formato: Cuadrado 1:1, Vertical 3:4, Historia 9:16, Horizontal
        4:3, Panorámico 16:9 — el modelo completa los bordes sin deformar el
        sujeto.
      - 💾 Descargar.
    - En el modo Imagen con OpenAI, una foto adjunta ahora se edita según tu
      mensaje (antes se ignoraba).
    - Las imágenes transparentes se muestran sobre un tablero de cuadros: un
      fondo quitado se ve claramente.
  Cambiado / Mejorado
    - La leyenda de las imágenes y el botón Descargar ahora están traducidos
      (solo existían en inglés / francés).

[1.10.1] — 2026-10-18
  Añadido
    - Gemini 4 Argon (gemini-4-argon), el nuevo modelo insignia de
      razonamiento de Google (contexto de 1M tokens), ahora primero en la
      lista de Gemini. Niveles de razonamiento: Bajo, Medio, Alto. Su límite
      de salida sube a 32 000 tokens (64 000 en los modos Código y Vibe
      Coder), porque su razonamiento cuenta dentro de ese límite. La búsqueda
      web, la lectura de enlaces, el modo Comparación y la transcripción de
      PDF escaneados funcionan con él.

[1.10.0] — 2026-10-17
  Añadido
    - Ahora se pueden leer los PDF escaneados (páginas compuestas de imágenes,
      sin texto). Al adjuntar uno, una ventana ofrece dos opciones, con el
      costo mostrado de antemano:
      - Transcribir a texto (OCR): el modelo seleccionado lee cada página una
        sola vez y extrae su texto. Sin límite de páginas (se procesan de tres
        en tres), una barra de progreso con los tokens ya usados, un botón
        Detener (las páginas ya hechas se conservan) y el costo real al final.
        Luego el texto se adjunta como un PDF normal: las preguntas siguientes
        cuestan poco.
      - Adjuntar las páginas como imágenes: el modelo "ve" las páginas (mejor
        para diagramas), pero se reenvían con cada pregunta (costo más alto),
        y algunos proveedores rechazan más de unas 100 páginas.
    - Se detectan los modelos que no leen imágenes (DeepSeek, GLM, Qwen
      Coder…) y la ventana explica por qué. Con Perplexity solo se ofrece la
      opción de imágenes (cada solicitud de transcripción lanzaría búsquedas
      web).

[1.9.2] — 2026-10-17
  Seguridad
    - PDF.js (que lee el texto de los PDF adjuntos) pasa de la 3.11.174, que ya
      no recibe mantenimiento, a la 6.4.299. La nueva versión ya no usa eval,
      lo que elimina de raíz el problema CVE-2024-4367.
    - La biblioteca PDF.js y su worker (procesamiento en segundo plano) ahora
      se verifican mediante su huella SHA-512 (contrastada en dos CDN); un
      archivo modificado se rechaza. La versión anterior no verificaba el
      worker.
  Cambiado / Mejorado
    - Extracción del texto de los PDF más rápida (unas 3 veces en un documento
      de 14 páginas).
  Nota
    - Los PDF escaneados (páginas compuestas de imágenes) siguen sin texto
      extraíble: se avisa al modelo de que el PDF está escaneado, como antes.

[1.9.1] — 2026-10-17
  Seguridad
    - DOMPurify (que limpia las respuestas de las IA antes de mostrarlas) pasa
      de la 3.0.9 a la 3.4.17, lo que corrige omisiones conocidas (p. ej.
      CVE-2024-45801), con una nueva huella de integridad SRI.
    - Importación de PDF: PDF.js ahora funciona con isEvalSupported
      desactivado, la mitigación oficial de CVE-2024-4367 (ejecución de
      JavaScript mediante una fuente de PDF manipulada).
    - Vista previa HTML "Abrir en una pestaña": la página generada ahora se
      abre dentro de un marco aislado (sandbox), como la vista previa del
      chat; ya no puede acceder al almacenamiento de ChatJPT (claves API).
    - Guía de claves API: consejo de usar una clave distinta con un límite de
      gasto mensual, y de usar ChatJPT en una computadora de confianza.
  Eliminado
    - Veo 3.1, Veo 3.1 Lite y Veo 3.1 Fast (Google los retira el 2026-10-22).
      El video de Gemini ahora usa Gemini Omni 1.1 Flash.

[1.9.0] — 2026-10-17
  Añadido
    - Nuevo proveedor: Perplexity (Agent API). Las respuestas siempre buscan en
      la web y citan sus fuentes. Cinco niveles, del más rápido al más
      profundo: Búsqueda rápida (Fast), Búsqueda (Estándar), Investigación
      multifuente (Medium), Investigación profunda (High, varios minutos) y
      Agente de investigación avanzado (X-High, muy lento y costoso).
    - El bloque 🧠 muestra la investigación en vivo: los razonamientos del
      modelo, las búsquedas que hace (🔎) y las páginas que abre (🌐).
    - Los marcadores de cita en la respuesta se convierten en pequeños enlaces
      clicables (¹ ²) hacia la fuente correspondiente, y las fuentes se
      listan debajo de la respuesta.
    - Funciona en el modo Comparación. La guía de claves API tiene una nueva
      sección Perplexity.

[1.8.2] — 2026-10-17
  Añadido
    - Modelos GLM de Z.ai: GLM-5.3 (razonamiento siempre activo, mostrado en el
      bloque 🧠), GLM-5.2 y GLM-5.1 (casilla de razonamiento). Los sirve Alibaba
      Cloud Model Studio, con la misma clave API que Qwen. La API propia de Z.ai
      no se puede usar desde un navegador (bloquea las solicitudes del
      navegador, CORS): usar Alibaba es la forma de usar GLM en ChatJPT.
  Cambiado / Mejorado
    - El proveedor "Qwen (Alibaba)" pasa a llamarse "Alibaba (Qwen, GLM)". Tu
      clave y tus ajustes guardados se conservan.

[1.8.1] — 2026-10-16
  Añadido
    - Qwen: Qwen3.7 Max, Qwen3.7 Flash (muy económico), Qwen Flash y Qwen3 Coder
      Flash. El modo de razonamiento está disponible en Qwen3.7 Max, Qwen3.7
      Flash y Qwen Flash.
    - Imágenes Qwen: Qwen Image 3.0 (más rápido y más barato que 3.0 Pro), Qwen
      Image 2.1 Pro y Qwen Image 2.1 Turbo (económico).
  Eliminado
    - Modelos Qwen que ya no figuran en el catálogo actual de Qwen: Qwen Turbo
      (reemplazado por Qwen Flash), Qwen3 Max, Qwen3 Coder Plus (reemplazado por
      Qwen3 Coder Flash) y Qwen Image Max.

[1.8.0] — 2026-10-06
  Añadido
    - Claude: Fable 5.1 (el más reciente), Opus 5.5, Sonnet 5.5, Opus 5 y
      Sonnet 5. En los modelos con adaptive thinking siempre activo, un resumen
      legible del razonamiento se muestra en el bloque 🧠, y un selector de
      esfuerzo (bajo → máximo) reemplaza el antiguo presupuesto de tokens.
    - OpenAI: GPT-6 Astra (el más reciente), GPT-6.1 Sol y GPT-6 Luna, a través
      de la API Responses para mostrar un resumen de su razonamiento. Imágenes:
      GPT Image 2.5 Sunburst (calidad) y Flare (rápido).
    - Gemini: 3.8 Flash (el más reciente), 3.7 Flash, 3.6 Flash y 3.5 Flash Lite.
      Imágenes: Nano Banana 2.1 (el más reciente) y Nano Banana 2 Lite. Video:
      Gemini Omni 1.1 Flash (con audio generado), mediante la nueva Interactions
      API.
    - Grok: 4.7 (el más reciente), 4.6 y 4.5, con razonamiento visible (mediante
      la API Responses de xAI) y selector de esfuerzo. Imágenes: Grok Imagine
      2.0. Video: Grok Imagine Video 1.5 y 1.5 Lite.
    - DeepSeek: V4 Pro y Flash, con una verdadera casilla de razonamiento
      (activado / desactivado) y una profundidad ajustable (reasoning effort).
    - Qwen: Qwen3.8 Max (el más reciente), Qwen3.7 Plus y Qwen3.8 Flash. El modo
      de razonamiento ahora funciona con Qwen (mostrado en el bloque 🧠, con un
      presupuesto de razonamiento). Imágenes: Qwen Image 3.0 Pro.
    - Se muestra un mensaje claro cuando Claude rechaza una solicitud (filtro de
      seguridad), en lugar de una respuesta vacía.
  Cambiado / Mejorado
    - Límite de salida más alto para los modelos cuyo razonamiento cuenta dentro
      de ese límite (Claude adaptativo, GPT-6, Grok 4.5+, DeepSeek con
      razonamiento): las respuestas largas ya no se cortan.
    - Gemini 3.8 / 3.7 Flash: el nivel de razonamiento "Mínimo", rechazado por
      estos modelos, se oculta.
    - Gemini Nano Banana 2 y Nano Banana Pro usan ahora sus identificadores
      estables.
    - Los modelos Veo 3.1 indican su fecha de fin (Google los retira el
      2026-10-22; Gemini Omni los reemplaza).
  Eliminado
    - Modelos retirados (o a punto de serlo) por sus proveedores: DeepSeek V3 / R1
      (deepseek-chat, deepseek-reasoner), Claude Opus 4.1, o3-pro, GPT Image 1.5
      y 1 Mini, Imagen 4, Veo 2.0 y las previews de imágenes de Gemini.
    - Video de OpenAI (Sora 2): OpenAI retiró Sora 2 y su API Videos el
      2026-09-24, sin reemplazo. La pestaña Video ahora está desactivada para
      OpenAI.
  Corregido
    - El botón "Mostrar" del bloque de razonamiento nunca mostraba el
      razonamiento (para todos los proveedores). Ahora se despliega y se pliega
      correctamente.

[1.7.1] — 2026-06-09
  Añadido
    - Claude Fable 5 (claude-fable-5), el modelo más capaz de Anthropic en
      disponibilidad general (contexto de 1M tokens), añadido a la lista de modelos
      Claude y mostrado como el más reciente. Usa adaptive thinking siempre activo
      (sin casilla de razonamiento configurable). La búsqueda web y la lectura de
      enlaces funcionan como con los demás modelos Claude.

[1.7.0] — 2026-06-08
  Añadido
    - Leer enlaces pegados (casilla opcional 🔗, desactivada por defecto, distinta
      de la búsqueda web): el modelo abre y lee el contenido real de la(s) URL que
      pegas en tu mensaje, en lugar de adivinar a partir de la dirección. La página
      leída se muestra como fuente en la que se puede hacer clic. La obtención se
      realiza en el servidor del proveedor (sin CORS), por lo que funciona
      directamente desde el navegador. Un aviso indica que consume más tokens (lee
      toda la página). Disponible para Gemini (herramienta url_context), Claude
      (herramienta web_fetch), OpenAI y Grok (herramienta web_search, que también
      abre una URL específica). No disponible para DeepSeek/Qwen (sin herramienta
      de lectura). También disponible en el modo comparación.
  Cambiado / Mejorado
    - Lectura de enlaces fiable para OpenAI y Grok: estas API no tienen una
      primitiva dedicada de lectura de URL (solo web_search, que «decide» si abre
      una página o no — antes intermitente). Al leer un enlace (sin búsqueda web
      amplia), la búsqueda ahora se restringe al/los dominio(s) de la URL pegada
      mediante allowed_domains, forzando al modelo a abrir esa página.

[1.6.2] — 2026-06-07
  Cambiado / Mejorado
    - Las etiquetas de tipos de gráficos ahora están completamente localizadas
      (FR/EN/ES): el badge visible y el nombre accesible (aria-label) muestran el
      nombre traducido del tipo (p. ej. « Gráfico de barras » / « Bar Chart » /
      « Graphique à barres »).

[1.6.1] — 2026-06-07
  Añadido
    - Español (latinoamericano) agregado como tercer idioma de la interfaz. El
      botón de idioma ahora alterna FR → EN → ES y muestra el idioma actual.
      Todas las cadenas de la interfaz, las etiquetas de modelos y los ejemplos
      de Vibe Coder están traducidos; el README, la guía de claves API, la
      LICENSE y este changelog incluyen una sección en español.

[1.6.0] — 2026-06-07
  Añadido
    - Contador de tokens: cada respuesta muestra su consumo exacto (↑ entrada /
      ↓ salida, según lo reportado por la API), más un total por conversación en
      la barra inferior. Solo tokens (sin estimación de precio). Ayuda a ver lo
      que cuesta realmente cada intercambio.
    - Búsqueda web + Fuentes (interruptor opcional 🌐, desactivado por defecto):
      el modelo busca en la web en tiempo real y la respuesta va seguida de una
      lista "Fuentes" plegable (línea completamente clicable, etiqueta legible o
      dominio). Disponible para Gemini (grounding de Google Search), Grok (xAI
      Agent Tools / API Responses), Claude (herramienta web_search) y OpenAI
      (web_search vía API Responses). Un aviso advierte que consume más tokens
      (+ costos de búsqueda). Las fuentes persisten tras recargar. El interruptor
      ("🌐 Búsqueda web + fuentes") también está disponible en el modo
      Comparación (cada modelo comparado lo usa solo si su proveedor lo soporta).
      No disponible para DeepSeek (sin búsqueda nativa) ni Qwen (DashScope no
      expone las fuentes en modo compatible con OpenAI).
  Corregido
    - Modo comparación: borrar el chat (o cambiar/crear una conversación)
      mientras una elección de comparación seguía pendiente ya no bloquea el
      envío — el estado pendiente se reinicia y los flujos en curso se cancelan
      (antes había que recargar la página).
    - Los gráficos solo se producen cuando se solicita explícitamente una
      visualización: antes, un modelo débil podía devolver un gráfico en lugar
      de una respuesta en texto (se añadió una salvaguarda al prompt).

[1.5.1] — 2026-06-07
  Añadido
    - Editar una respuesta de la IA (✎): reemplaza su texto en el lugar; se
      vuelve a renderizar (código, tablas, gráficos), sin regeneración ni
      truncamiento. El texto corregido se vuelve el contexto para el resto de la
      conversación. (Enter = nueva línea; Ctrl/Cmd+Enter = guardar.)

[1.5.0] — 2026-06-06
  Añadido
    - Persistencia de imágenes (IndexedDB): las imágenes generadas ahora
      sobreviven a las recargas y a los cambios de conversación. Los turnos del
      modo imagen se registran en la conversación (visibles en la lista, la
      búsqueda y la exportación). Almacenadas localmente fuera de la cuota de
      localStorage; la descarga (💾) sigue siendo la copia duradera.
    - El pulgar 👎 ahora actúa sobre la IA: una nota pasiva le indica al modelo
      que la respuesta no satisfizo (se corrige en el siguiente turno), y una
      caja "↻ Mejorar" (con un motivo opcional) regenera una mejor respuesta.
    - El pulgar 👍 le indica al modelo que mantenga ese enfoque.
    - Enlace "reportar un error" en la caja del 👎, con una confirmación para
      distinguir un error de la app de una respuesta simplemente insatisfactoria.

[1.4.1] — 2026-06-06
  Añadido
    - Botón "volver abajo": aparece cuando subes a releer durante el streaming;
      un clic regresa al último mensaje.
    - Renombrar una conversación: doble clic en su título en el panel (Enter
      para confirmar, Esc para cancelar, vacío restaura el título automático).
  Cambiado / Mejorado
    - Refactorización interna: las cinco funciones de streaming comparten un
      núcleo común postStream(), y los límites de tokens de salida están
      centralizados (TOKEN_LIMITS). Sin cambio de comportamiento.

[1.4.0] — 2026-06-06
  Añadido
    - Conversaciones múltiples: un panel lateral (☰) para crear, cambiar,
      eliminar y exportar todo. Almacenamiento clave-por-conversación con
      migración automática de la conversación única anterior. Las más antiguas
      nunca se borran en silencio: la generación se bloquea con un mensaje claro
      (eliminar/exportar) antes de llegar al límite del navegador.
    - Búsqueda en la conversación (🔍): resalta las coincidencias con navegación
      anterior/siguiente; sin distinción de mayúsculas ni acentos.
    - Editar un mensaje enviado (✎): la conversación se trunca desde ese punto y
      la IA responde al prompt corregido.
    - Regenerar una respuesta con otro modelo (🔀): mismo prompt, modelo
      diferente, para comparar rápidamente.
    - Atajo de teclado: Esc detiene la generación en curso.
  Cambiado / Mejorado
    - Streaming: autodesplazamiento "adherente" — subir a releer ya no pelea con
      el desplazamiento; el resaltado de sintaxis se difiere al render final
      (streaming mucho más fluido en bloques de código grandes).
    - Los gráficos se reducen para caber en pantallas pequeñas (sin
      desbordamiento); cada lienzo tiene un nombre accesible (role=img +
      aria-label).

[1.3.0] — 2026-06-05
  Añadido
    - Proveedor Grok (xAI) — ubicado entre Gemini y DeepSeek (modelos
      estadounidenses agrupados):
        - Chat: grok-4.3 (insignia), grok-4.20 (razonamiento / sin
          razonamiento), grok-build-0.1. Streaming compatible con OpenAI.
        - Imagen: grok-imagine-image-quality (síncrono), con selectores de
          formato y resolución.
        - Video: grok-imagine-video (Grok Imagine) — 10 s, 720p, audio nativo
          (submit + polling, como Sora/Veo). 3.er proveedor de video tras
          Sora/Veo.
    - Botón "Borrar las claves" en el panel de claves: elimina todas las claves
      API almacenadas del navegador con un clic (con confirmación) — útil en una
      computadora compartida.
  Corregido
    - Los errores de xAI (devueltos como cadena, no como objeto) ahora muestran
      su mensaje real en lugar de un genérico "HTTP Error 400" — los rechazos de
      moderación de contenido ahora son claros (Grok chat, imagen, video).
  Cambiado
    - Se eliminó un script de compilación de terceros (MyNinja) cargado pero sin
      usar: ya no hay JS de terceros ni telemetría en la página donde se
      ingresan las claves API.
    - Archivo fuente renombrado de ChatJPT_1_2_0.html a ChatJPT_1_3_0.html.
    - Número de versión actualizado a 1.3.0 (encabezado y pie de página, FR/EN).

[1.2.0] — 2026-06-04
  Añadido
    - Proveedor DeepSeek (DeepSeek V3 chat, DeepSeek R1 razonamiento),
      streaming compatible con OpenAI.
    - Proveedor Qwen (Alibaba DashScope): chat (qwen-max/plus/turbo, qwen3-max,
      qwen3-coder-plus) y generación de imágenes, con una región DashScope a
      elegir (Internacional / China continental).
    - Panel de claves API plegable con indicadores de estado por proveedor
      (clave guardada / faltante), mostrando ahora el nombre de cada proveedor
      junto a su punto de color.
    - Modo Comparación: ejecuta el mismo prompt en dos modelos lado a lado
      (cualquier proveedor, agrupados por proveedor), con ambas respuestas
      transmitidas en paralelo. Conserva la que prefieras con un clic — o
      descarta ambas; solo la respuesta conservada entra en el historial.
      Disponible en los modos Chat y Código.
    - Modo Vibe Coder: un modo para principiantes (no programadores). Un mentor
      paciente que detecta tu idioma, hace una pregunta de aclaración a la vez,
      presenta un plan de acción en lenguaje simple y ESPERA tu aprobación antes
      de construir, luego te guía paso a paso — señalando los botones de
      vista previa/descarga de la app, proponiendo próximos pasos concretos y
      anticipando errores comunes.
    - Vista previa HTML en vivo: cualquier página HTML completa muestra un botón
      👁 que la renderiza al instante en un iframe aislado (solo allow-scripts,
      sin acceso same-origin — el código previsualizado no puede leer tus claves
      API almacenadas), con una opción "abrir en una pestaña". Disponible en
      todos los modos.
  Corregido
    - Las salidas grandes (páginas HTML completas en un solo archivo) ya no se
      truncan en Gemini ni en los proveedores compatibles con OpenAI (DeepSeek,
      Qwen): su presupuesto de tokens de salida se eleva para los modos con
      mucho código.
  Cambiado
    - Archivo fuente renombrado de ChatJPT_1_1_1.html a ChatJPT_1_2_0.html.
    - Número de versión actualizado a 1.2.0 (encabezado y pie de página, FR/EN).

[1.1.1] — 2026-06-01
  Añadido
    - Claude Opus 4.8 (claude-opus-4-8) — ahora el modelo Claude por defecto y
      más capaz.
    - Selector de calidad de imagen para OpenAI (Baja/Media/Alta/Auto). La
      calidad estaba fijada en "Alta" (lo más lento); ahora es "Media" por
      defecto para una generación más rápida y es ajustable por el usuario.
    - Selector de tamaño de imagen para OpenAI (Cuadrado/Horizontal/Vertical/
      Auto), reemplazando el 1024×1024 fijo. Calidad y tamaño se guardan y se
      muestran solo para OpenAI.
    - Selectores de formato (relación) y resolución (1K/2K/4K) para las imágenes
      de Gemini, aplicados a Nano Banana e Imagen 4. Guardados y mostrados solo
      para Gemini. (Gemini no tiene una perilla de "calidad" Baja/Media/Alta; la
      resolución es su equivalente.)
    - Calificación pulgar arriba/abajo por respuesta de la IA, guardada con la
      conversación y restaurada al recargar.
    - Un banner "invítame un café" descartable, mostrado a lo sumo una vez por
      sesión y solo después de un 👍 (nunca después de un 👎).
    - Exportación de solo las respuestas calificadas con 👍 (cada una precedida
      de su pregunta), además de la exportación completa de la conversación.
  Corregido
    - Generación de video OpenAI (Sora): el menú Duración ahora ofrece los
      valores que la API de Sora realmente acepta (8/12/16/20 s) en lugar de los
      valores de Gemini Veo (8/6/4 s), que eran rechazados.
    - El polling de video ya no se queda bloqueado 20 minutos en silencio ante
      un error de la API; el error real se muestra tras algunos intentos
      fallidos.
    - Sora 2 Pro recibe un tiempo de espera más largo (~40 min), ya que los
      renders Pro son mucho más lentos que el modelo rápido; el mensaje de
      progreso ya no promete un irreal "1-3 min".
    - Los errores de video ahora también muestran el mensaje exacto del
      proveedor (y lo registran en la consola), para que los rechazos de
      moderación o de parámetros sean claros en lugar de quedar ocultos.
  Cambiado
    - Claude Opus 4.7 ya no está marcado como "Último" (pasó a legacy).
    - Archivo fuente renombrado de ChatJPT_1_1.html a ChatJPT_1_1_1.html.
    - Número de versión actualizado a 1.1.1 (encabezado y pie de página, FR/EN).

[1.1] — 2026
  Añadido
    - Primera versión pública.
    - Soporte multiproveedor: OpenAI, Anthropic (Claude), Google (Gemini).
    - Modos Chat, Código, Imagen y Video.
    - Modo Agente y Modo Razonamiento.
    - Tema claro / oscuro e interfaz bilingüe (FR/EN).
    - Almacenamiento local de claves API y preferencias (sin servidor).
    - Descarga de archivos (bloques de código, tablas CSV).

================================================================
