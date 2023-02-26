# react-snap action

[![Test server-side render](https://github.com/brycedorn/react-snap-action/actions/workflows/test.yml/badge.svg)](https://github.com/brycedorn/react-snap-action/actions/workflows/test.yml)

This action uses [react-snap](https://github.com/stereobooster/react-snap) to pre-render a web application into static, hydratable HTML.

If your node-based web application has a `build` script that outputs HTML, this action will render it and update the `index.html` within output directory with the result. This can then easily be deployed to GitHub pages etc and you'll have some of the benefits of SSR without needing a server!

```yml
jobs:
  prerender:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout 🛎️
        uses: actions/checkout@v3
      
      - name: Server-side render
        uses: brycedorn/react-snap-action@v1.0.1
```