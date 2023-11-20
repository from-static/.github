# static

Built on GitHub Pages, static enables the creation of basic microsites, targeting a variety of use cases.

## How it Works

Using a `static.json` file, our GitHub Action automatically deploys a static, single-page application based on the `type`.

Under the hood, we translate your `static.json` to a fully functional microsite built on Next.js.

Start with our minimum required configuration, then rely on the automatic deployments based on changes to your `static.json` file to enhance functionality.

## Features + Roadmap
- [x] Proof-of-Concept: `type: "RESUME"`
- [ ] Add initial theme for `type: "RESUME"`
- [ ] Provide JSON Schema for `static.json`
- [ ] Document `static.json`
- [ ] Add `static dev` CLI utility for local previews of `static.json`
- [ ] Support for `type: "RESEARCH_DATA_PORTAL`
- [ ] Add `static eject` CLI utility for "ejecting" from the static ecosystem
