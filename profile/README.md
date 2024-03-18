# static

Built on GitHub Pages, static enables the creation of basic microsites, targeting a variety of use cases.

static is more of an application design approach rather than a framework or library.

A `static.json` makes reference to a **`generator`** package, which is responsible for processing the `static.json` file and producing a static site.

The `data` member of the `static.json` file acts as a data source for a static site generator, static assets produced by the generator are then hosted on GitHub Pages – _that's it_.

From a downstream consumer perspective, the `static.json` file becomes a build manifest, configuration file, and even content management system depending on target generator's usage.

---

🧪 **static is in early development preview.** There will likely be some churn of the `static.json` structure. Unless you are willing to accept some temporary maintenance burden, I don't suggest configuring a site just yet!

Questions/Feedback? [Open an Issue](https://github.com/from-static/.github/issues).

---

## How it Works

Using a `static.json` file, our reusable GitHub Action workflows automatically deploy a static, single-page application to GitHub Pages based on your configuration.

Our first-class applications translate your `static.json` to a fully functional microsite built on Next.js.

Start with our minimum required configuration, then rely on the automatic deployments based on changes to your `static.json` file to enhance functionality.

## Get Started

1. Create a new repository from one of our templates.
   - [from-static/example-resume](https://github.com/from-static/example-resume)
2. Enable GitHub Actions as your GitHub Pages Source in your new repository.
3. Edit the `static.json`
4. Wait for the GitHub Action to run...
5. View your generated microsite at your repository's GitHub Pages URL.

That's it! Any changes you make to `static.json` will automatically redeploy your site.

## `static.json`

A `static.json` file acts as a configuration object for an application. The most important property of this file is: `_static`.

### `_static`

Instructs our GitHub Action on how to build your application.

```json
{
  "_static": {
    "generator": "@from-static/static-resume",
  },
}
```
- `generator` should reference a static site generator (usually a Next.js application) that will process your `static.json` file.
  - The generator should match the name of a package found in the configured package ecosystem (see below).
  - In most cases, this will be a first-class application:
    - [from-static/static-resume](https://github.com/from-static/example-resume)
- `ecosystem` is an optional property that can be used to specify a package registry to use for the `generator` package. If not specified, the default registry (`npm`) is used.
  - Supported Values: `npm`


#### `data`

The `data` member of the `static.json` file acts as a data source for a static site generator.

```jsonc
{
  "data": {
    "version": "1.0.0",
    "attributes": {
      // Generator-defined properties
    }
  }
}
```
- `version` is a string that represents the version of the `data` object to be consumed (and enforced) by the generator.
- `attributes` is an object that contains all data that will be used to generate the static site.

### Additional Properties (`data.attributes`)

A `generator` dictates all additional properties in `data.attributes`

While there are some properties we suggest all applications treat the same, we do not currently enforce this standard outside of our first-class applications.

## Features + Roadmap

- [static GitHub Project](https://github.com/orgs/from-static/projects/1/views/1)
