# Rierie developer website

GitHub Pages root site: https://rierie501.github.io/

## Implementation plan

1. Publish the exact seller record from AdMob at `/app-ads.txt`.
2. Serve a small developer homepage from this repository's `main` branch, root folder.
3. Verify the deployed file is plain text and matches the AdMob record.
4. Add the developer website to each app's Google Play listing, then check AdMob authorization.

The seller record was read directly from the account's **Apps → app-ads.txt → How to set up app-ads.txt** dialog on 28 October 2026. It authorizes Google for publisher `pub-5833452649715240`. Add other sellers only after verifying their account-specific records.

## Publishing

Publish `main` from `/` in GitHub Pages settings. `.nojekyll` keeps the files static; no build dependencies or custom domain are required.

The existing privacy policy remains in the separate [`rierie501/policy`](https://github.com/rierie501/policy) repository, published from `master:/docs` at `/policy/`. This root site does not replace or copy that policy. Do not add a custom-domain redirect without reviewing both sites and the Play developer website URLs.

## Review and verification

- The deployed URL must be `https://rierie501.github.io/app-ads.txt`, with HTTP 200 and a plain-text response containing exactly the checked-in seller record.
- A file under `/policy/app-ads.txt` would not be the normal crawler target.
- Check the homepage and the existing recorder policy URL after deployment.
- The same root file can serve both apps when their Play listings use this developer website and their ad inventory uses this publisher account.
- A successful Pages deployment does not establish AdMob authorization; the Play listing and AdMob crawl must also complete.

## Next steps in Google Play and AdMob

For **Audio Recorder and Editor** (`rierie.media.audiorecorder`) and **Audio/Video Converter Android** (`roman10.media.converterv2`):

1. Set the store listing contact **Website** to `https://rierie501.github.io/`. Keep each app's privacy-policy URL in its separate privacy-policy field.
2. Verify the public Google Play listing's App support section exposes the website link.
3. In AdMob's app-ads.txt page, expand each app and select **Check for updates** when available.
4. Allow at least 24 hours for discovery/crawling, then confirm the file is found and the seller account is authorized for both apps.

Use the `rierie501@gmail.com` Chrome profile and Google account for this app's Play Console.

References: [AdMob setup](https://support.google.com/admob/answer/9363762?hl=en-GB), [GitHub Pages setup](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).
