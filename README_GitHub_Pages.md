# THSR Auto Archive | GitHub Pages website

Static, bilingual Chinese/English OAuth branding website for the personal Windows desktop tool THSR Auto Archive.

## 1. Important: no guaranteed Google OAuth verification on github.io

GitHub Pages is a free and practical place to host a public homepage and privacy policy. Some developers use github.io for Google OAuth consent pages, but 2026 Google Developer forum reports show some OAuth reviewers reject `github.io` hosting because the site is not on an independently owned domain.

Deploying these pages does NOT guarantee that Google will accept your OAuth Authorized Domain, publish your app, verify branding, or verify Gmail restricted scopes. Personal-use verification exceptions may apply separately.

If Google rejects the provider hostname, keep this very same site and add a custom domain you own via GitHub Pages Settings > Pages > Custom domain. You may then need to verify DNS ownership via Google Search Console.

## 2. Edit BEFORE publishing

1. Replace `REPLACE_WITH_CONTACT_EMAIL` across index.html, privacy.html, and terms.html with an email address you are comfortable displaying PUBLICLY. You can use a dedicated support alias. Never publish OAuth credentials or your Google App Password.
2. Confirm every privacy policy statement matches the CURRENT Windows application's behavior. The current sample describes Gmail API OAuth with `gmail.readonly`, not IMAP or App Password. If you switched to IMAP, do not use this privacy policy unchanged.
3. If archives are synced to a NAS or other cloud service, confirm the policy accurately explains that the user configures such synchronization.
4. You can leave the logo in the repository, but uploading an app logo to Google OAuth Branding is optional and may require additional verification.

## 3. Publish at username.github.io (simplest URL)

1. Visit https://github.com/new and create a PUBLIC repository with the exact name `YOUR_GITHUB_USERNAME.github.io` (replace with your actual GitHub username in lowercase).
2. Upload all website files in this folder to the ROOT of that repository. Do not upload the whole Windows Python program.
3. Open repository Settings > Pages > Build and deployment > Deploy from a branch. Select `main` and `/ (root)`, then Save.
4. After deployment, open `https://YOUR_GITHUB_USERNAME.github.io/` and confirm the links to `/privacy.html` and `/terms.html` work without logging in. GitHub says publication may take several minutes.

If you already have a GitHub user Pages site, instead use a new project repository, e.g. `thsr-oauth-site`. Its default URL is `https://YOUR_GITHUB_USERNAME.github.io/thsr-oauth-site/`. All links in this package are relative and work in either arrangement.

## 4. Optional Google Search Console URL-prefix verification

1. Go to https://search.google.com/search-console/ with the SAME Google account managing the Google Cloud project.
2. Add a URL-prefix property matching your PUBLIC website URL exactly, e.g. `https://YOUR_GITHUB_USERNAME.github.io/` (or the project path URL).
3. Choose HTML tag verification and paste the provided exact `<meta name="google-site-verification" ...>` inside `<head>` in `index.html`, where the included comment appears. Commit and wait for Pages to deploy, then click Verify. Alternatively upload the exact HTML verification file provided by Google to the published property root.
4. Search Console URL-prefix ownership is not necessarily sufficient for Google OAuth's separate domain ownership/branding review. Do not claim ownership of `github.io` itself.

## 5. Fill Google Cloud OAuth Branding

Open https://console.cloud.google.com/auth/branding with your THSR Auto Archive project selected.

| Field | For user Pages site |
| --- | --- |
| App name | THSR Auto Archive |
| Support email | Your real chosen Google account from the dropdown |
| Application home page | https://YOUR_GITHUB_USERNAME.github.io/ |
| Privacy policy | https://YOUR_GITHUB_USERNAME.github.io/privacy.html |
| Terms of service | https://YOUR_GITHUB_USERNAME.github.io/terms.html |
| Authorized domains | Follow Google Cloud's CURRENT accepted top-private-domain rules; try your verified host as allowed, do not falsely claim ownership of github.io |
| Developer contact email | A real address you monitor |

For project Pages, replace each root URL with `https://YOUR_GITHUB_USERNAME.github.io/thsr-oauth-site/` plus the corresponding filename.

After saving Branding, visit https://console.cloud.google.com/auth/audience and attempt Publish app. If Google blocks publishing or asks for domain ownership, do NOT assume Search Console URL-prefix verification automatically resolves OAuth verification. Consider a custom-owned domain or the other access approach you have evaluated.

A publish-state change, brand verification, and Gmail restricted-scope verification are DIFFERENT steps. A public information-only website does NOT expose Gmail data; the desktop program accesses Gmail via local OAuth.

## 6. Security

This repository should contain only the public static website files. NEVER upload `credentials.json`, `token.json`, App Passwords, `config.json` containing secrets, `.eml` emails, PDFs, `trips.sqlite`, or any private travel data. Free GitHub Pages typically publishes from a PUBLIC repository.

All HTML/CSS and logo assets are served statically. There are no forms, trackers, external scripts, analytics, cookies or executable code in this site. GitHub Pages may log network requests/IP addresses under GitHub's own policies.

## 7. Reference sources (reviewed 2026-11-09)

- GitHub Pages quickstart: https://docs.github.com/en/pages/quickstart
- Google OAuth branding: https://support.google.com/cloud/answer/15549049
- Google Search Console ownership verification: https://support.google.com/webmasters/answer/9008080
- Google OAuth brand verification: https://developers.google.com/identity/verification/authentication-verification
- Public 2026 forum showing github.io rejection: https://discuss.google.dev/t/oauth-verification-stuck-on-homepage-requirements-firebase-web-app-domain-not-recognized/333105
