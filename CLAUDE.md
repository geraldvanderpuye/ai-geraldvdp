# ai.geraldvdp.com — project context

Editorial landing page for Gerald Vanderpuye's AI consultancy (brand: Gerald; company: GVDP Ltd; programme: Think AI-Native). Single static page, no framework, no build step.

## Workflow
- `index.html` is the entire site (inline CSS/JS) + `assets/`. Do not split into multiple files without being asked.
- Deploys: push to `main` → Vercel project **gvdp-site** (Impact Brixton team) auto-deploys production; branches get preview URLs. Never use `vercel deploy` from CLI — the `.vercel/` folder points at a superseded project.
- Target domain: **ai.geraldvdp.com** (not yet attached). geraldvdp.com root stays his Substack.

## Voice & design rules (do not violate)
- First person singular, honest, short sentences, em-dashes, concrete numbers, zero hype, no exclamation marks. "I work with", never "we help".
- Editorial magazine look: Fraunces serif at scale, warm paper background, pull-quote interludes. Orange→amber gradient ONLY in the masthead, the Ask Gerald button hover, and one accent word.
- Banned: gradient blobs, icon grids, feature cards, logo carousels, chat widgets, popups, stat counters, stock imagery, testimonial sliders.
- Never invent client quotes. No pricing on the page. No follower counts. Don't name universities. Keep the photography placeholders labelled until the real shoot happens.

## Open work (in order)
1. Replace `[FORM_ENDPOINT]` and `[EMAIL_ADDRESS]` in index.html (launch blocker).
2. Attach ai.geraldvdp.com in Vercel → Settings → Domains; CNAME at the DNS host.
3. v1.1 "AI-native": keep the page static; add a Vercel serverless function (`api/ask.js`) so the Ask Gerald form returns an instant Claude-drafted first answer in Gerald's voice (grounded on his Substack + proof points, clearly labelled as his AI), and emails the full thread to Gerald.
4. Compress assets/gerald-teaching.jpg (~306KB → ~100KB); real client pull-quote when Gerald supplies one; company number in footer once the VCC Ltd → GVDP Ltd rename completes.

Approved proof points: Brixton Brewery (part of Heineken), Levy Real Estate, Lambeth Council-funded programmes, Brixton BID, Stripe partnership, Loop (£5k first 10 days, built solo), ~£15k saved / ~5x traffic rebuilding his own sites.
