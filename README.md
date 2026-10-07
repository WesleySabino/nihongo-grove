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
  assets/          # Visual assets used by the hub
  robots.txt       # Crawler access and sitemap location
  sitemap.xml      # Canonical hub URL
CONTRIBUTING.md
LICENSE
```

Serve the contents of `public` as the website root. Keep the HTTPS canonical URL, social metadata, and sitemap URL consistent when deploying the official site. Forks hosted elsewhere should replace those URLs with their own.

## Privacy

The hub does not collect account details, request payment information, or include analytics or advertising scripts. Links open separate learning apps, whose storage and account behavior are independent of the hub. The hosting service handles normal requests needed to deliver the website.

This public repository contains only learner-facing source and documentation. Domain administration, credentials, contact details, and private project management files belong outside it.

## Search and sharing

The homepage uses descriptive English text, a canonical URL, social preview metadata, and `WebSite` structured data. `robots.txt` allows crawling and identifies the sitemap. The hub sitemap lists only the hub's canonical homepage; the learning subdomains are separate sites and can publish their own sitemaps.

Search engines choose whether and when to index a site. These files make the hub accessible and describe its content; they do not guarantee rankings or immediate indexing.

## Contribute

See [CONTRIBUTING.md](CONTRIBUTING.md) for small improvements, accessible design guidelines, and review checks.

## License

The hub source is available under the [MIT License](LICENSE).
