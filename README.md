# Leeman Labs website

The homepage and Conjugator privacy policy are one buildless GitHub Pages site. This directory is the site root. The Android source stays in this repository; publish the website files to **tleeman/tleeman.github.io**.

| Local source | Published address |
| --- | --- |
| `index.html` | https://tleeman.github.io/ |
| `conjugator-privacy/index.html` | https://tleeman.github.io/conjugator-privacy/ |

Both pages share `styles.css`, branding and navigation. The policy wording and public URL are unchanged, so the app's `PRIVACY_POLICY_URL` and Play Console privacy link stay the same. The homepage's Google verification tag is retained.

## Publish the combined site

1. Open the existing public repository **tleeman/tleeman.github.io** using an account with write access.
2. Upload `index.html`, `styles.css`, `.nojekyll`, the complete `assets/` folder, and the complete `conjugator-privacy/` folder from this directory to the repository root. Do not upload the enclosing `websites` folder or the Android project. Preserve the folders and include `.nojekyll` when copying hidden files. This README is a maintenance guide and is not needed for the published site.
3. In **Settings → Pages**, choose **Deploy from a branch**, **main**, **/ (root)**, then save.
4. Wait for deployment and open https://tleeman.github.io/ signed out. Check both screenshots, support email and privacy links. Follow the one-time cutover below before treating the privacy page as migrated.

No install or build step is needed. The page uses local assets and system fonts, with no JavaScript, analytics, cookies or third-party embeds. GitHub's hosting itself logs visitor IP addresses for security; see https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#data-collection.

## One-time cutover from the separate privacy site

The old **tleeman/conjugator-privacy** project site owns the same public path as the new `conjugator-privacy/` folder. Uploading the combined site alone does not retire that project deployment.

1. Publish the complete combined site to **tleeman/tleeman.github.io** first. Confirm that the successful deployment contains `conjugator-privacy/index.html`, the shared stylesheet and icon. Preview the policy locally if needed; the public privacy URL may still show the old standalone page until the old site is unpublished.
2. In **tleeman/conjugator-privacy → Settings → Pages**, open the menu beside the live site address and choose **Unpublish site**. Keep the repository and its history. Under **Build and deployment**, select **Deploy from a branch**, set the branch to **None**, and save so a later commit cannot republish the old site. See GitHub's [unpublishing guide](https://docs.github.com/en/pages/getting-started-with-github-pages/unpublishing-a-github-pages-site) and [disabling the publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/deleting-a-github-pages-site#deleting-your-site-by-changing-the-source).
3. Allow GitHub's routing/cache to update, then open **https://tleeman.github.io/conjugator-privacy/** signed out. Confirm it now has the Leeman Labs header, shared cream/green styling, full policy text, and working links back to the homepage and Support. Check the homepage privacy links too.
4. If the policy does not load from the main site after propagation, check the combined deployment and folder layout. If necessary, re-enable Pages on the old privacy repository as a rollback while fixing the main site; do not change the app or Play Console URL to work around a deployment problem.

The cutover is complete only after the policy is served by the homepage repository. Future homepage and policy changes both go to **tleeman/tleeman.github.io**.

## Preview locally

Serve `websites/` as the web root with any static HTTP server, then open `/` and `/conjugator-privacy/`. Check desktop and narrow layouts, keyboard navigation, the support links and both directions of page navigation. No build or dependency installation is required.

## Verify ownership with Google

1. Sign in to https://search.google.com/search-console using the Google account that owns the Play Console account.
2. Add a **URL prefix** property for **https://tleeman.github.io/**. Do not choose Domain verification for the shared `github.io` domain.
3. Choose **HTML tag** verification. Copy the exact `<meta name="google-site-verification" ...>` tag Google supplies.
4. Keep the supplied tag inside `<head>` in `index.html`. Upload the updated file to the homepage repository and wait for Pages deployment.
5. Click **Verify** in Search Console. Keep the tag in the source and public page permanently.
6. In Play Console's account details, enter **https://tleeman.github.io/** and send the website verification request. Using the same Google account should approve the association automatically.

Google instructions: https://support.google.com/googleplay/android-developer/answer/13205715 and https://support.google.com/webmasters/answer/9008080.

The supplied Search Console verification tag is included in `index.html`. Keep it in the source and published homepage permanently so Google can continue confirming ownership. Verification is only complete after the updated page is published and Search Console confirms success.

## Maintenance

- The homepage uses Google's official [Get it on Google Play badge](https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png), saved unchanged as `assets/google-play-badge.png`. Keep it local, preserve its proportions and built-in clear space, and follow [Google's badge guidance](https://partnermarketinghub.withgoogle.com/brands/google-play/google-play/lockups-icons-badges/). Both store links use the Android application ID `com.leemanlabs.conjugator.it`.
- Publish all website changes to `tleeman/tleeman.github.io`; keep the old privacy site's Pages deployment disabled after cutover.
- The homepage uses launch-ready wording and links to the Google Play listing for `com.leemanlabs.conjugator.it`. Publish it when that listing is available to your intended audience; no launch-day copy replacement is needed.
- Use **Conjugator** for the app, **ConjuGATOR** only for the crocodile mascot, and **Leeman Labs** for the publisher. The privacy policy may use the full app title **Conjugator - Italian Verbs**.
- Product copy follows `docs/PRODUCT.md`. The page extends `DESIGN.md` using its warm cream, forest green, mint, serif headings and approved mascot. The hero mascot sits on the app's forest-green circle, with the same 172/192 artwork scale as `ConjugatorLogo`; the Android design system remains unchanged.
- Mascot and icon assets are copies of the approved artwork in `docs/images/`. `assets/practice.png` and `reference.png` are the original clean app captures from `.local/store-final-16/03-practice-feedback-light-screen.png` and `06-conjugation-table-light-screen.png`, retained here as website assets because `.local` is ignored. Use clean screen captures without the Play Store promotional headings or surrounds. Assets stay local so the homepage works independently of the Android repository; refresh them when the app changes.
- The app privacy policy covers the Android app. Keep its link and existing URL working.
