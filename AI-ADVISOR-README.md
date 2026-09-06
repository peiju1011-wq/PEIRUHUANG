# PEIRU HUANG — Art Advisor v2

This version keeps the existing single-file React/Tailwind structure and naming style.

## Working now
- Private pricing: public artwork prices were removed from the front-end source.
- Art Advisor page: `#/advisor`
- Guided recommendations based on room, mood, artwork scale, and private budget preference.
- 3-artwork shortlist with direct links to artwork detail pages.
- Inquiry / collect flow pre-fills the contact form with artwork, budget range and room notes.
- Contact form still submits through the existing Formspree endpoint.
- Purchase intent can be selected without exposing a public artwork price.

## GPT integration
GitHub Pages is a static host. Do not put an OpenAI API key inside `index.html`, JavaScript, or GitHub Pages source.
A real GPT chat should call a server-side endpoint (for example a Supabase Edge Function, Vercel Function, or Cloudflare Worker) where the API key is stored as an environment secret.

The current advisor works immediately without a server and is designed as the front-end UX for that later GPT connection.

## Suggested secure flow
Browser -> secure server function -> OpenAI Responses API -> returns recommendations -> browser

Keep private prices only on the secure server/database if GPT needs to compare a collector's budget against actual prices.
