# react-snap action

This action uses [react-snap](https://github.com/stereobooster/react-snap) to pre-render a web application into hydratable, static HTML.

If your node-based application has a `build` script this action will install dependencies, apply configuration and save the render result to your output directory. This can then easily be deployed to GitHub pages etc and you'll have some of the benefits of SSR without needing a server!

```yml
jobs:
  prerender:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout 🛎️
        uses: actions/checkout@v3
      
      - name: Server-side render
        uses: brycedorn/react-snap-action@v1.0
```