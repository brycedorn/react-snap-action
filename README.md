# react-snap action

[![Test SSR](https://github.com/brycedorn/react-snap-action/actions/workflows/test.yml/badge.svg)](https://github.com/brycedorn/react-snap-action/actions/workflows/test.yml)

This action uses [react-snap](https://github.com/stereobooster/react-snap) to pre-render a web application into static, hydratable HTML.

If your node-based web application has a `build` script that outputs HTML, this action will render it and update the `index.html` within output directory with the result. This can then easily be deployed to GitHub pages, etc and you'll have some of the benefits of server-side rendering (SSR) without needing a server!

While you can include [react-snap](https://github.com/stereobooster/react-snap) as a dependency to directly your project, [puppeteer](https://github.com/puppeteer/puppeteer/tree/main) is heavy and headless Chrome is overkill for a simple web app. This also simplifies the configuration required to enable them to run in CI.

## Usage

```yml
jobs:
  prerender:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout 🛎️
        uses: actions/checkout@v3
      
      - name: Server-side render
        uses: brycedorn/react-snap-action@v1.0.2
```

For input options see [action.yml](https://github.com/brycedorn/react-snap-action/blob/main/action.yml).

## Why use this?

 - Enables SEO for SPAs. Web crawlers only care about `<meta>` tags in HTML markup, not those rendered client-side.
 - Better performance. As the server frontloads the expensive initial render once, clients only need to [hydrate](https://beta.reactjs.org/reference/react-dom/hydrate) to render the app.