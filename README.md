# WoodUltraSmooth3D-privacy

Public pages for the Android game **Woodturning Ultra Smooth 3D** (`com.canalgrid.WoodUltraSmooth3D`) by Canal Grid.
Static HTML, no build step, no dependencies — served by GitHub Pages.

| Page | File | URL once Pages is on |
|---|---|---|
| Privacy policy | `privacy/index.html` | `https://canalgrid.github.io/WoodUltraSmooth3D-privacy/privacy/` |
| Feedback & support | `privacy/feedback.html` | `https://canalgrid.github.io/WoodUltraSmooth3D-privacy/privacy/feedback.html` |
| Delete your data | `privacy/delete-account.html` | `https://canalgrid.github.io/WoodUltraSmooth3D-privacy/privacy/delete-account.html` |
| Root redirect | `index.html` | `https://canalgrid.github.io/WoodUltraSmooth3D-privacy/` → privacy policy |

## Turning on GitHub Pages

Repository → **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main`, folder `/ (root)` → **Save**.
The site is usually live a minute or two later.

## Where these URLs go in Play Console

- **App content → Privacy policy** — the privacy policy URL (required before you can publish)
- **Store listing → Support → Website** — either page works; the feedback page is friendlier
- **Store listing → Support → Email** — `vmwnpela@gmail.com`
- **App content → Data deletion** — the "Delete your data" URL (required once you declare the app collects any data)

## Check before you publish

Unlike Color Box, this game ships with real purchases and with diagnostics, so the policy
makes claims that have to match the build. Confirm each of these:

- [ ] **Analytics/crash SDK names.** The pages name **Firebase Crashlytics** and **Unity Analytics**.
      If the build actually uses something else (Unity Cloud Diagnostics only, GameAnalytics,
      Adjust, AppsFlyer…), replace the names and the two policy links in
      `privacy/index.html` §6 and `privacy/delete-account.html`. Naming an SDK you do not ship —
      or omitting one you do — is the most common cause of a Data Safety rejection.
- [ ] **Data Safety form matches.** Declaring analytics means you must tick *Analytics* / *Crash logs*
      and *App interactions* in Play Console, and *Purchase history* for the IAP.
      The Data Safety form and this policy have to tell the same story.
- [ ] **Ad format list.** §4 describes a banner, an occasional interstitial and rewarded video.
      Trim whatever the game does not show.
- [ ] **Saved-data list.** §2 lists projects, smoothness scores, stars, best times, gallery pieces,
      unlocked tools/woods/finishes, tutorial flag and settings. Delete any line the game
      does not actually store — an over-broad list is still an inaccurate one.
- [ ] **Restore Purchases exists.** Three pages tell players to tap it in the settings screen.
      If the button is not there, add it or remove those sentences.
- [ ] **Languages.** The feedback page asks for translation corrections without naming languages.
      Once the shipping language list is settled, name them there.

## Keeping it accurate

The policy describes what the app actually does, so it has to be revisited when the app changes.
Update it if any of these become true:

- an analytics, attribution or crash-reporting SDK is added, removed or swapped
- new in-app purchase types are added (subscriptions in particular — they need their own wording)
- cloud save or Google Play Games sign-in is enabled (there is none today; either one would add
  an account and change the deletion page substantially)
- ads are removed entirely, or a different ad provider replaces Unity LevelPlay
- the game starts saving photos of finished pieces to the device gallery (that touches storage permissions)

Change the "Last updated" date in `privacy/index.html` and `privacy/delete-account.html` whenever the text changes.
