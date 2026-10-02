# BakeMemo legal site deployment package

Publish this directory as the HTTPS document root for `bakememo.cn`.

Required public routes:

- `/bakememo/privacy`
- `/bakememo/support`

The package is static HTML/CSS only. It contains no JavaScript, analytics, cookies, forms, external fonts, or third-party runtime assets. Each page carries Apple's native `apple-itunes-app` Smart App Banner meta tag (app-id 6792324050); it is a Safari feature, not a script or tracker. Before App Store submission, verify both URLs return HTTP 200 over HTTPS on a phone and that the certificate covers `bakememo.cn`.
