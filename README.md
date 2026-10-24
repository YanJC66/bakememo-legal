# BakeMemo legal site deployment package

Publish this directory as the HTTPS document root for `bakememo.cn`.

Public routes:

- `/` — product homepage (zh-Hans), `/en/` — English homepage
- `/guide/`, `/en/guide/` — baking guide index; each guide has a zh page at `/guide/<slug>/` and an en page at `/en/guide/<slug>/`
- `/calculator/`, `/en/calculator/` — baker's percentage calculator (runs entirely in the browser)
- `/404.html` — bilingual not-found page (GitHub Pages serves it automatically)
- `/bakememo/privacy` (required by App Store)
- `/bakememo/support` (required by App Store)

Homepage images in `assets/img/` are generated from real Simulator captures by `build_images.py` in the app repo (`docs/legal/site`; sources: App Store screenshot sets, `src/`); the script and sources are not published. Rerun it after recapturing; do not hand-edit the WebP files. `sitemap.xml` and `robots.txt` list every public page for search engines; add new pages to both. `.nojekyll` keeps GitHub Pages from processing the tree. `198e2f71b6e71e6aceedab76b9a02cad.txt` is the IndexNow key (Bing and other IndexNow engines). `CNAME` binds the custom domain.

The package is static HTML/CSS. JavaScript is inline only: a few lines that pick zh or en from the visitor's system language (`navigator.languages`, remembered in `localStorage` after a manual switch), and the calculator page's arithmetic. Nothing is sent anywhere and nothing else is stored. There are no analytics, cookies, forms, external fonts, or third-party runtime assets. Each page carries Apple's native `apple-itunes-app` Smart App Banner meta tag (app-id 6792324050); it is a Safari feature, not a script or tracker. Before App Store submission, verify both URLs return HTTP 200 over HTTPS on a phone and that the certificate covers `bakememo.cn`.
