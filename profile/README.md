## Overview

- `from-static` enables the creation of ready-to-serve web applications and websites, targeting a variety of use cases.
- `from-static` is more of an application design approach rather than a framework or library.
- A `static.json` file references a **`generator`** package, which is responsible for processing the file and producing a static site (i.e., a static site generator).
- The `data` member of the `static.json` file acts as a data source for a static site generator.
- Generated assets produced by the generator are then hosted on GitHub Pages – _that's it_.

From a downstream consumer perspective, the `static.json` file acts as a build manifest, configuration file, and even content management system depending on the target generator's usage.

---

Questions/Feedback? [Open an Issue](https://github.com/from-static/.github/issues).

---

## How it Works

Using a `static.json` file, our reusable GitHub Action workflows automatically deploy a single-page application to GitHub Pages based on your configuration.

Our first-class applications ("generators") translate your `static.json` to a fully functional microsite built on Next.js.

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
- `generator` should reference a static site generator (usually a Next.js application) that will process your `static.json` file and build the resulting application.
  - The generator should match the name of a package found in the configured package ecosystem (see below).
  - In most cases, this will be a first-class application:
    - [from-static/static-resume](https://github.com/from-static/example-resume)
- `ecosystem` is an optional property that specifies a package registry for the `generator` package. If not specified, the default registry (`npm`) is used.
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
- `version` –  A string representing the version of the data object. The generator can use this value to identify the expected shape of attributes.
- `attributes` – An object containing data the generator will use to generate the application.

### Additional Properties (`data.attributes`)

A `generator` dictates all additional properties in `data.attributes`

While there are some properties we suggest all applications treat the same, we do not currently enforce this standard outside of our first-class applications.

## Features + Roadmap

- [static GitHub Project](https://github.com/orgs/from-static/projects/1/views/1)
