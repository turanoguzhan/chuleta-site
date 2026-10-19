# Chuleta — public site

Static pages for GitHub Pages: no build step, no dependencies. Light and dark follow the visitor's system.

| Path | Purpose |
|---|---|
| `index.html` | Landing page: what the app is, the daily See → Recognise → Recall path, a real card, screenshots, privacy, contact. Use the site root as the **Support URL** and **Marketing URL** in App Store Connect. |
| `privacy/index.html` | Privacy policy. This URL goes into App Store Connect → App Privacy → **Privacy Policy URL**. |
| `assets/` | Icon sizes and screenshots (iPhone 17 Pro Max simulator, dark, with `--no-tips` and a clean status bar). |

## Publish (one time)

The app repo is private, and GitHub Pages on a private repo needs a paid plan, so the site lives in its own **public** repo, as ValuVale's does:

1. Create a public repo `chuleta-site`.
2. Copy this folder's contents to its root and push.
3. Settings → Pages → Source: *Deploy from a branch* → `main` / `/ (root)`.
4. The pages are then at `https://<user>.github.io/chuleta-site/` and `…/chuleta-site/privacy/`.

## Keep in sync

- The in-app policy (`App/Chuleta/Features/Me/PrivacyPolicyView.swift`) and `privacy/index.html` carry the same sections and the same "Last updated" date. Change both together.
- **Before a version with in-app purchases or ads ships, update the policy** (and the App Store privacy answers): AdMob collects data, and the policy currently says nothing is collected.
- The card on the landing page is the app's own `bar.me_pones_un_cafe`, word for word. If that phrase changes, change it here.
- When the App Store page exists, replace the "Coming soon" badge with Apple's official "Download on the App Store" badge linking to the app, and add `<meta name="apple-itunes-app" content="app-id=…">`.

## Custom domain later

Buy the domain (e.g. `chuletaapp.com`, free on 2026-10-10), add a `CNAME` file with it, point its DNS at GitHub Pages, and update the URLs in App Store Connect. A rename of the app changes the name in these pages too.
