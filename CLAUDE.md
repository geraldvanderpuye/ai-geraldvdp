# www.gvdp.co.uk — project context

Editorial landing page for Gerald Vanderpuye's AI consultancy (brand: Gerald; company: GVDP Ltd; programme: Think AI-Native). Static page + one Vercel serverless function, no framework, no build step.

## Workflow
- `index.html` is the entire site (inline CSS/JS) + `assets/` + `api/ask.js` (the Ask Gerald form backend). Do not split the page into more files without being asked.
- Deploys: push to `main` → Vercel project **gvdp-site** (Impact Brixton team) auto-deploys production; branches get preview URLs. Never use `vercel deploy` from CLI — the `.vercel/` folder points at a superseded project.
- Domain: **www.gvdp.co.uk** (apex 308-redirects to www; attached to gvdp-site 2026-08-31, DNS at Squarespace). geraldvdp.com root stays his Substack; the earlier ai.geraldvdp.com plan was dropped in favour of the purchased gvdp.co.uk.

## Voice & design rules (do not violate)
- First person singular, honest, short sentences, em-dashes, concrete numbers, zero hype, no exclamation marks. "I work with", never "we help".
- Editorial magazine look: Fraunces serif at scale, warm paper background, pull-quote interludes. Orange→amber gradient ONLY in the masthead, the Ask Gerald button hover, and one accent word.
- Banned: gradient blobs, icon grids, feature cards, logo carousels, chat widgets, popups, stat counters, stock imagery, testimonial sliders.
- Never invent client quotes. No pricing on the page. No follower counts. Don't name universities. Keep the photography placeholders labelled until the real shoot happens.

## Form backend (`api/ask.js`, shipped 2026-08-31)
The Ask Gerald form POSTs JSON to `/api/ask`, which (a) drafts a first answer with Claude in Gerald's voice — clearly labelled as his AI on the page — and (b) emails the question + draft to Gerald via Resend. Each half degrades gracefully until its env var is set in Vercel (gvdp-site → Settings → Environment Variables): `ANTHROPIC_API_KEY` (Claude draft) and `RESEND_API_KEY` (email; optional `ASK_TO_EMAIL` defaults to gerald@hey.com, `ASK_FROM_EMAIL` defaults to Resend's onboarding sender). With neither set, the API returns 503 and the page falls back to a prefilled mailto:gerald@hey.com link — the form is never a dead end.

## Open work (in order)
1. Add `ANTHROPIC_API_KEY` and `RESEND_API_KEY` env vars in Vercel (see above). Resend test mode only delivers to the account owner's email — sign up with gerald@hey.com, or verify a sending domain.
2. Real client pull-quote when Gerald supplies one; company number in footer once the VCC Ltd → GVDP Ltd rename completes.

Domain went live 2026-08-31: Squarespace custom records A `@` → 216.150.1.1 and CNAME `www` → 6229057d74f646ff.vercel-dns-016.com; all three domains show Valid Configuration in Vercel.

Approved proof points: Brixton Brewery (part of Heineken; Gerald frames this as "helping companies like Heineken"), Levy Real Estate, Lambeth Council-funded programmes, Brixton BID, Stripe partnership, ~£15k saved / ~5x traffic rebuilding his own sites, shoDeck (previously BuyerDeck; award-winning venture startup he ran 13 years — NOT "Birec"), and the GVDP umbrella ventures: Loop (AI-native CRM, Claude at its heart, built with 4 businesses over 4 months, replaced 12 paid tools, starts from free, access via the site form), Brixton Culture Capital (agentic newsletter, 20,000 readers, thebcclist.com), the community rum (brixtonculture.com), CompanyBoard (agentic Companies House/HMRC tool, companyboard.org), Impact Brixton (AI-native coworking, impactbrixton.com).
