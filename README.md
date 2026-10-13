# WoodUltraSmooth3D-privacy

Public pages for the Android game **Woodturning Ultra Smooth 3D** (`com.canalgrid.WoodUltraSmooth3D`) by Canal Grid.
Static HTML, no build step, no dependencies — served by GitHub Pages.

| Page | File | URL |
|---|---|---|
| Privacy policy | `privacy/index.html` | `https://canalgrid.github.io/WoodUltraSmooth3D-privacy/privacy/` |
| Privacy policy (root copy) | `index.html` | `https://canalgrid.github.io/WoodUltraSmooth3D-privacy/` |
| Feedback & support | `privacy/feedback.html` | `https://canalgrid.github.io/WoodUltraSmooth3D-privacy/privacy/feedback.html` |
| Delete your data | `privacy/delete-account.html` | `https://canalgrid.github.io/WoodUltraSmooth3D-privacy/privacy/delete-account.html` |

`index.html` is `privacy/index.html` with its links pointing into `privacy/`. Edit `privacy/index.html`, then regenerate:

```sh
sed -e 's|href="delete-account.html"|href="privacy/delete-account.html"|g; s|href="feedback.html"|href="privacy/feedback.html"|g' privacy/index.html > index.html
```

## Where these URLs go in Play Console

- **App content → Privacy policy**: the privacy policy URL
- **Store listing → Support → Website**: the feedback page
- **Store listing → Support → Email**: `vmwnpela@gmail.com`
- **App content → Data deletion**: the "Delete your data" URL

## What the policy describes (v1.2.0, October 2026)

The game is a Capacitor (web) app. It ships:

- **Google AdMob**: banner, interstitial, app-open and rewarded ads, with Google's UMP consent form (EEA/UK/CH) and a Privacy Options button in Settings
- **Google Play Billing**: one product, `remove_ads` (one-time), with Restore Purchase in Settings
- **Local notifications**: a daily "free wood" reminder for Remove Ads owners only
- **Share**: a picture of a Collection piece, drawn on the device and handed to Android's share sheet

No analytics, crash-reporting or attribution SDK, no server, no account. Progress lives in the app's local storage.

Data Safety form to match: **Device or other IDs** (advertising ID), plus approximate location, app interactions and diagnostics collected by the AdMob SDK, for *Advertising or marketing*, *Analytics* and *Fraud prevention, security and compliance*. **Purchase history** for the IAP.

## Keeping it accurate

Revisit the pages when any of these change:

- an analytics, attribution or crash-reporting SDK is added
- ads are removed, or another ad network or mediation is added to AdMob
- new in-app products (subscriptions in particular)
- cloud save or Google Play Games sign-in (would add an account and change the deletion page)
- what the save holds (see `src/core/save.js` in the game)

Change the "Last updated" date in `privacy/index.html` and `privacy/delete-account.html` whenever the text changes.
