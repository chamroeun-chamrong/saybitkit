# SabayKit privacy policy page

Public hosting for the privacy policy that the Play Store listing points at. The
Play Console requires a privacy policy at a URL anyone can open without signing
in, and this repository is what serves it.

**Live:** https://chamroeun-chamrong.github.io/saybitkit/

## What is here

| Path | What it is |
| --- | --- |
| `index.md` | **The policy itself — this is the canonical copy.** Edit this file, nothing else. |
| `_layouts/default.html` | Page template (header, footer, contact line). |
| `assets/style.css` | Styling. Light and dark, mobile-first. |
| `_config.yml` | GitHub Pages / Jekyll configuration. |
| `provenance/privacy-policy-generator-export.md` | The untouched export from [App Privacy Policy Generator](https://app-privacy-policy-generator.nisrulz.com/), kept as a record of what was generated. Do not edit it and do not treat it as the policy — `index.md` is the policy. |

## Editing the policy

1. Edit `index.md`. Keep the front matter block (`---` … `---`) at the top.
2. Commit and push to `main`. GitHub Pages rebuilds automatically in about a
   minute — there is no build step to run locally.
3. Confirm the change is actually live rather than trusting the push:

```sh
curl -s https://chamroeun-chamrong.github.io/saybitkit/ | grep -i "the phrase you changed"
```

If the change does not appear, check the Pages build status:

```sh
gh api repos/chamroeun-chamrong/saybitkit/pages/builds/latest --jq '.status'
```

## Using it in Play Console

Play Console → **Policy and program** → **App content** → **Privacy policy** →
paste the live URL. The same URL is recorded in the app repository at
`store/CONSOLE-SETUP.md`.

Google fetches that URL and shows it to users, so it has to stay reachable,
public, and free of anything that needs a login or a redirect through a consent
wall.

## A note on languages

The page is English, which is what Play requires. The app itself ships Khmer and
English, so a Khmer version of the policy can be added later as `km.md` with
`lang: km` in its front matter and a link between the two pages — the stylesheet
already carries a Khmer font stack. Nothing is served at `/km/` today.
