# Metanyx.ai static site

Pure HTML/CSS/JS. No build step and no framework dependencies.

## Deploy to AWS S3 + CloudFront
1. Create an S3 bucket (private is preferred when CloudFront uses Origin Access Control).
2. Upload the CONTENTS of this folder preserving paths.
3. Create a CloudFront distribution with the bucket as origin.
4. Set `index.html` as the default root object.
5. Configure 404 handling to `/404.html`.
6. Attach an ACM certificate for `metanyx.ai` (and optionally `www.metanyx.ai`) and point DNS to CloudFront.
7. Redirect `metanyx.com` permanently (301) to `https://metanyx.ai` and preserve useful old paths where possible.

## Deploy to Cloudflare Pages
Create a Pages project and deploy this repository as static assets. No build command is required. Add `metanyx.ai` as the custom domain.

## Deploy behind Bunny CDN
Upload to Bunny Storage (or your origin), enable the Pull Zone, set `index.html` as the default document, add the custom hostname and SSL.

## Before launch
- Replace `hello@metanyx.ai` if needed.
- Add privacy/terms pages before collecting user data.
- Add analytics only if wanted; consider a privacy-friendly option.
- Verify both domains in Google Search Console.
- Submit `/sitemap.xml`.
- Map important historical metanyx.com URLs to relevant new URLs with 301 redirects rather than redirecting everything blindly to the homepage.
- Keep claims about third-party networks/venues current.
