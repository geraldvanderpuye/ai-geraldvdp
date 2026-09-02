# www.gvdp.co.uk — project context

Editorial landing page for Gerald Vanderpuye's AI consultancy (brand: Gerald; company: GVDP Ltd; programme: Think AI-Native). Static page + one Vercel serverless function, no framework, no build step.

## Handover to Claude — rebuild the AI test

> **Implemented 2026-09-02.** The test now follows `AI-READINESS-WORKING-MEMO.md`: seven questions verbatim, gate-based classification (no points score), whole-company scoring, higher-level pockets named separately without raising the level, and the first missing gate rendered as the next move. Public level names: Individual experimentation / Organisational adoption / Workflow transformation / Business reinvention; ladder Experiment—Adopt—Transform—Reinvent. Result stays an email capture for the report. Article placeholders renamed `ARTICLE_ADOPTION/WORKFLOW/REINVENTION_URL` (still `#`, matching the memo's three transition pieces). `AI-TEST-CLAUDE-BRIEF.md` and the section below describe the OLD six-question model — historical only.

Gerald wants the current five-question yes/no AI test replaced with a much stronger 60-second assessment. Your next task is to implement it in `index.html` using the complete specification in `AI-TEST-CLAUDE-BRIEF.md`.

The brief was produced after walking through GenAIPI's full AI Readiness Assessment, including its 24 questions, eight departments, score preview and lead-capture gate. Borrow the useful interaction principles—clear progress, behaviour-based answer choices, a named maturity result and one prioritised next action—but do not copy its wording, visuals, percentage score, 24-question length or mandatory contact gate.

The approved GVDP model is:

- **Level 0 — Write:** AI creates content; a person still carries the work.
- **Level 1 — Connect:** AI can see the business through connected systems.
- **Level 2 — Act:** agents complete work within human-set boundaries.
- **Level 3 — Become:** AI changes the product, customer promise or business model.

There are four diagnostic stages but three editorial next-step paths:

- Level 0 → `Connecting your existing systems with an AI brain`
- Level 1 → `Developing agents to work for you`
- Levels 2–3 → `Five companies that became completely AI-native`

Those articles have not been written yet. Keep their destinations as clearly named placeholder constants; do not invent or publish the articles.

Implementation boundaries:

- Read and follow every section of `AI-TEST-CLAUDE-BRIEF.md`; it contains the approved question copy, answer copy, scoring thresholds, guardrails, result copy, interaction details and acceptance criteria.
- Keep the site framework-free and make the change inside `index.html`.
- Preserve the editorial design and every section outside `#ai-test`, apart from the smallest change needed to pass the result level into the existing Ask Gerald form.
- Do not add a lead gate, phone field, popup, analytics vendor or external assessment service.
- Do not send individual assessment answers to Claude or any third party.
- Test all four result paths, the scoring guardrails, Back, retake, keyboard use, mobile width and reduced motion.
- Do not push, deploy or publish. Leave the working tree ready for Gerald to review.

At handover, report the files changed, score cases tested, the three placeholder article constants and any genuine remaining risk. Stop after the local implementation and verification.

## Workflow
- `index.html` is the entire site (inline CSS/JS) + `assets/` + `api/ask.js` (the Ask Gerald form backend). Do not split the page into more files without being asked.
- Deploys: push to `main` → Vercel project **gvdp-site** (Impact Brixton team) auto-deploys production; branches get preview URLs. Never use `vercel deploy` from CLI — the `.vercel/` folder points at a superseded project.
- Domain: **www.gvdp.co.uk** (apex 308-redirects to www; attached to gvdp-site 2026-08-31, DNS at Squarespace). geraldvdp.com root stays his Substack; the earlier ai.geraldvdp.com plan was dropped in favour of the purchased gvdp.co.uk.

## Voice & design rules (do not violate)
- First person singular, honest, short sentences, em-dashes, concrete numbers, zero hype, no exclamation marks. "I work with", never "we help".
- The customer is the subject of every value-proposition sentence ("Your team...", not "I...").
- "I" owns all promises and opinions. "We" only after the developers have been introduced by name/role; never an anonymous corporate "we".
- The page sells ONE offer: the training sessions. Build and advisory are sold in the room, never on the page. Gerald-as-builder stays as proof ("I still build every week", the venture stories).
- "Cowork", "Skills" and other vendor product names don't appear in copy (MCP is the one allowed term of art — the gotcha is intentional).
- Editorial magazine look: Fraunces serif at scale, warm paper background, pull-quote interludes. Orange→amber gradient ONLY in the masthead, the Ask Gerald button hover, the hero's "something new.", and one pull-quote accent word.
- Banned: gradient blobs, icon grids, feature cards, logo carousels, chat widgets, popups, stat counters, stock imagery, testimonial sliders.
- Never invent client quotes. No pricing on the page. No follower counts. Don't name universities. Keep the photography placeholders labelled until the real shoot happens.

## Form backend (`api/ask.js`, shipped 2026-08-31)
The Ask Gerald form POSTs JSON to `/api/ask`, which (a) drafts a first answer with Claude in Gerald's voice — clearly labelled as his AI on the page — and (b) emails the question + draft to Gerald via Resend. Each half degrades gracefully until its env var is set in Vercel (gvdp-site → Settings → Environment Variables): `ANTHROPIC_API_KEY` (Claude draft) and `RESEND_API_KEY` (email; optional `ASK_TO_EMAIL` defaults to gerald@hey.com, `ASK_FROM_EMAIL` defaults to Resend's onboarding sender). With neither set, the API returns 503 and the page falls back to a prefilled mailto:gerald@hey.com link — the form is never a dead end.

## Open work (in order)
0. AI test v2 deployed 2026-09-02 (six-question staged diagnostic per `AI-TEST-CLAUDE-BRIEF.md`; `assessment-level-*` topics flow through api/ask.js subject/body/AI-draft). Result screen is an EMAIL CAPTURE, not a booking push (Gerald's call): the reader asks for "the full report — the three stages of building, and the one I'd read first at your level", sent via /api/ask, arriving as "AI test Level N — AI test reader". Gerald sends the report personally. The three articles are still unwritten — the `LEVEL_*_ARTICLE_URL` constants remain as named placeholders for when they exist. Writing the report/articles is the top content task.
1. Add `ANTHROPIC_API_KEY` and `RESEND_API_KEY` env vars in Vercel (see above). Resend test mode only delivers to the account owner's email — sign up with gerald@hey.com, or verify a sending domain.
2. Stripe partnership band removed from the page 2026-08-31 (Gerald's call) — the Stripe mention in the evidence client-line stays; re-add a band only if he asks. Heineken-session photo still pending a real photo. Ratio Property pull-quote pending the founder's sign-off (drafts sent to Gerald).
3. Real client pull-quote when Gerald supplies one; company number in footer once the VCC Ltd → GVDP Ltd rename completes.

Copy overhaul done 2026-08-31: businesses positioning, four own-venture stories replace Duolingo/Intercom, diagnostic checklist ("fraction of what AI is worth" hook), single training offer in three formats. Form backend live (topics: question / workshop / loop).

Domain went live 2026-08-31: Squarespace custom records A `@` → 216.150.1.1 and CNAME `www` → 6229057d74f646ff.vercel-dns-016.com; all three domains show Valid Configuration in Vercel.

Approved proof points: Brixton Brewery (part of Heineken; Gerald frames this as "helping companies like Heineken"), Levy Real Estate, Lambeth Council-funded programmes, Brixton BID, Stripe partnership, ~£15k saved / ~5x traffic rebuilding his own sites, shoDeck (previously BuyerDeck; award-winning venture startup he ran 13 years — NOT "Birec"), and the GVDP umbrella ventures: Loop (AI-native CRM, Claude at its heart, built with 4 businesses over 4 months, replaced 12 paid tools, starts from free, access via the site form), Brixton Culture Capital (agentic newsletter, 20,000 readers, thebcclist.com), the community rum (brixtonculture.com), CompanyBoard (agentic Companies House/HMRC tool, companyboard.org), Impact Brixton (AI-native coworking, impactbrixton.com).
