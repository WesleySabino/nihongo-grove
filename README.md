# Nihongo Grove

A free Japanese learning hub with a retro handheld console style. Discover focused kana practice and short minigames, with guidance in English.

**Live site:** [nihongogrove.top](https://nihongogrove.top/)

## Learning projects

- [Japanese Core · Kana Mastery](https://kana.nihongogrove.top/): hiragana and katakana practice through reading, writing with tiles, listening, and spaced review.
- [Kana Rain](https://kana-rain.nihongogrove.top/): read falling kana and type their sounds before they reach the pond.

These apps run on their own subdomains. This repository contains the hub, not the app implementations. Future projects are marked as in development until they have working destinations.

## Run locally

The hub is a static website. There are no packages to install and no build step.

With Python 3 installed, run this command from the repository root:

```sh
python -m http.server 8000 --directory public
```

Then open [localhost:8000](http://localhost:8000/). Any static web server can serve the `public` directory.

## Files

```text
public/
  index.html       # English hub, metadata, and structured data
  privacy.html     # Shared privacy notice and analytics controls
  assets/          # Visual assets used by the hub
  robots.txt       # Crawler access and sitemap location
  sitemap.xml      # Canonical hub URL
CONTRIBUTING.md
LICENSE
```

Serve the contents of `public` as the website root. Keep the HTTPS canonical URL, social metadata, and sitemap URL consistent when deploying the official site. Forks hosted elsewhere should replace those URLs with their own.

## Privacy

The hub does not collect account details or request payment information. Optional Google Analytics 4 measures page visits and clicks into the two learning apps after a visitor explicitly accepts analytics. Advertising features are disabled. Links open separate learning apps, whose storage and account behavior are independent of the hub. The hosting service handles normal requests needed to deliver the website. See the [privacy notice](https://nihongogrove.top/privacy) for details.

### Analytics

The locally served `assets/nihongo-analytics.js` module loads Google's library only after opt-in, and only on the three exact HTTPS production hostnames. Local previews and forks do not transmit analytics. The shared functional consent cookie lasts 180 days across `nihongogrove.top` and its subdomains; visitors can change their choice through **Analytics settings**. DNT/GPC keeps analytics off. Withdrawal disables transmission and clears accessible GA cookies without reloading the page.

All three sites use the public measurement ID `G-F69S8JDW5M`. The hub sends manual `page_view` events and `app_open` events with `target_app` set to `core` or `rain`; `site_app` is `hub`. Unknown event fields are rejected. Queries, fragments, typed answers, learner IDs, usernames, access keys, scores, and exports are excluded. Page URLs and titles come from fixed allowlists. Enhanced Measurement is disabled in GA4, and user/event retention is two months; these provider settings must also be maintained in the Analytics administration interface.

The consent module, styles, and privacy notice are shared with the app repositories. Keep their copies synchronized. Verify the consent/event boundary using Node 22 or later:

```sh
node --test analytics.test.mjs
```

Analytics represents visitors who opt in and whose browsers allow collection; counts are observations of use, not proof of learning outcomes. No account is needed to use the hub.

This public repository contains only learner-facing source and documentation. Domain administration, credentials, contact details, and private project management files belong outside it.

## Search and sharing

The homepage uses descriptive English text, a canonical URL, social preview metadata, and `WebSite` structured data. `robots.txt` allows crawling and identifies the sitemap. The hub sitemap lists only the hub's canonical homepage; the learning subdomains are separate sites and can publish their own sitemaps.

Search engines choose whether and when to index a site. These files make the hub accessible and describe its content; they do not guarantee rankings or immediate indexing.

## Contribute

See [CONTRIBUTING.md](CONTRIBUTING.md) for small improvements, accessible design guidelines, and review checks.

## License

The hub source is available under the [MIT License](LICENSE).
