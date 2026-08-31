# Gerald Vanderpuye AI landing page

This directory contains the complete static landing page for `ai.geraldvdp.com`.

## Source

- `index.html` — the full site, including all HTML, CSS and JavaScript.
- `assets/logo-horizontal.png` — masthead wordmark.
- `assets/logo-square.png` — favicon and social preview mark.
- `assets/gerald-teaching.jpg` — current workshop photograph.

There is no framework or build step. Serve this directory as a static site.

## Current positioning

The page is about helping founders think AI-native about:

- what they build;
- what customers need;
- how they take products to market; and
- where growth can come from.

Gerald's entrepreneurship teaching, go-to-market and customer-development work provide the commercial foundation. His computer-science, Rackspace, Google/GCP, machine-learning, Birec and Loop experience provide the technical and builder foundation.

## Deployment

Current Vercel URL: <https://ai-geraldvdp.vercel.app/>

The directory is linked to the existing Vercel project. Deploy updates from this directory with:

```sh
vercel deploy . --prod --yes --archive=tgz
```

The custom domain `ai.geraldvdp.com` has not been connected.

## Remaining placeholders

Before connecting the custom domain, replace both placeholders in `index.html`:

- `[FORM_ENDPOINT]` — the Formspree, Tally or equivalent form endpoint.
- `[EMAIL_ADDRESS]` — Gerald's fallback contact email.

The photography blocks are intentionally labelled placeholders for the planned shoot.

## Important logo detail

The horizontal logo must retain `height: auto`. Its original proportions are approximately 5.25:1. The `mix-blend-mode: multiply` rule removes the visible white rectangle against the warm paper background.
