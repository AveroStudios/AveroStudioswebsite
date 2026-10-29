# Avero Studios website
Plain HTML/CSS/JS + one Cloudflare Pages Function. No build step.

## Deploy
1. Create a GitHub repo and upload everything in this folder (keep the structure).
2. Cloudflare > Workers & Pages > Create > Pages > Connect to Git > pick the repo.
3. Framework preset: None. Build command: leave empty. Build output directory: `/` (root).
4. Deploy, then add the custom domain under Custom domains (averostudios.co.za).

## Make the quote form deliver email
Sign up at resend.com (free tier exists), verify averostudios.co.za, create an API key.
In Cloudflare Pages > Settings > Variables and Secrets add (as secrets):
- `RESEND_API_KEY` – your key
- `QUOTE_TO_EMAIL` – daniel@averostudios.co.za
- `QUOTE_FROM_EMAIL` – e.g. `Avero Studios <quotes@averostudios.co.za>`
Redeploy, submit a test enquiry, confirm the email arrives. Until these are set the form shows an error (it never fakes success).

## Still to do
- Review the services and FAQ wording in index.html.
- Add case studies when approved. Review the privacy notice for POPIA.
- Optional: Turnstile (add widget + `TURNSTILE_SECRET`; set the site key in the form).
