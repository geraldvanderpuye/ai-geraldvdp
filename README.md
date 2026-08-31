# Gerald Vanderpuye AI landing page

This directory contains the complete static landing page for `ai.geraldvdp.com`.

## Source

- `index.html` — the full site, including all HTML, CSS and JavaScript.
- `api/ask.js` — Vercel serverless function behind the Ask Gerald form (Claude-drafted first answer + email to Gerald; see CLAUDE.md for env vars).
- `assets/logo-horizontal.png` — masthead wordmark.
- `assets/logo-square.png` — favicon and social preview mark.
- `assets/gerald-teaching.jpg` — current workshop photograph.

There is no framework or build step.

## Current positioning

The page is about helping founders think AI-native about:

- what they build;
- what customers need;
- how they take products to market; and
- where growth can come from.

Gerald's entrepreneurship teaching, go-to-market and customer-development work provide the commercial foundation. His computer-science, Rackspace, Google/GCP, machine-learning, Birec and Loop experience provide the technical and builder foundation.

## Deployment

Current Vercel URL: <https://gvdp-site.vercel.app/>

Push to `main` on GitHub — the Vercel project **gvdp-site** (Impact Brixton team) auto-deploys production; branches get preview URLs. Do not use `vercel deploy` from the CLI: the local `.vercel/` folder points at a superseded project.

The custom domain `ai.geraldvdp.com` has not been connected yet.

## Remaining placeholders

The photography blocks are intentionally labelled placeholders for the planned shoot.

## Important logo detail

The horizontal logo must retain `height: auto`. Its original proportions are approximately 5.25:1. The `mix-blend-mode: multiply` rule removes the visible white rectangle against the warm paper background.
