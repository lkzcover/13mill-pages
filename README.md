# 13MILL legal pages

Standalone static pages for 13MILL:

- Privacy policy: https://legal.13mill.com/privacy/
- App support: https://legal.13mill.com/support/
The privacy page contains Russian and English versions and contact information for
Pavel Novokshonov: team@13mill.com. No build, dependencies, analytics or backend.

## Local preview

From this directory:

```sh
python3 -m http.server 8091 --bind 127.0.0.1
```

Open http://127.0.0.1:8091/privacy/. The language switch updates the `lang` query
parameter; no local storage is used. English is the default regardless of browser language. Use `?lang=ru` for a direct
Russian link. Without JavaScript, the English text remains visible.

## GitHub Pages

This repository contains only public legal pages for 13MILL. Application source code
is maintained separately in lkzcover/13mill.

In that repository, select Settings → Pages → Deploy from a branch → main → /(root).
Configure the custom domain as `legal.13mill.com` before pointing DNS at GitHub.
The tracked CNAME file contains that hostname.

At the DNS provider for 13mill.com:

| Type | Host | Target |
| --- | --- | --- |
| CNAME | legal | lkzcover.github.io |

Wait for GitHub's DNS check and certificate issuance, then enable Enforce HTTPS.
The main 13mill.com domain does not need to change. Verify the domain in the GitHub
account's Pages settings using the TXT record GitHub provides.

After deployment, verify HTTPS, RU/EN switching and mailto links on mobile and
desktop. Only then add the live URL to the app and App Store Connect.

## App Store Connect

Use https://legal.13mill.com/support/ as the Support URL and
https://legal.13mill.com/privacy/ as the Privacy Policy URL.
