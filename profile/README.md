# static

Built on GitHub Pages, static enables the creation of basic microsites, targeting a variety of use cases.

---

🧪 **static is in early development preview.** There will likely be some churn of the `static.json` structure. Unless you are willing to accept some temporary maintenance burden, I don't suggest configuring a site just yet!

Questions/Feedback? [Open an Issue](https://github.com/from-static/.github/issues).

---

## How it Works

Using a `static.json` file, our GitHub Action automatically deploys a static, single-page application to GitHub Pages based on your configuration.

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
    "application": "git@github.com:from-static/static-resume.git",
    "version": "0.1.0"
  },
}
```
- `application` should reference a Next.js application that will process your `static.json` file. 
  - In most cases, this will be one of our first-class applications:
    - [git@github.com:from-static/static-resume.git](from-static/static-resume)
- `version` is an optional version tag that our GitHub Action will use for checkout and validation.

### Additional Properties

An `application` dictates all additional properties in a `static.json`. 

While there are some properties we suggest all applications treat the same, we cannot enforce this standard outside of our first-class applications.


## Features + Roadmap

- [static GitHub Project](https://github.com/orgs/from-static/projects/1/views/1)
