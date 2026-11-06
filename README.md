# Stacks — Library Catalog

A responsive React catalog for browsing books, filtering by genre, searching by
title or author, and opening a book's detail page.

## Requirements

- Node.js 18 or newer
- The [Library Catalog API](https://github.com/seenoinaurori/library-catalog-service)
  running locally on port `3000`

## Run locally

1. Start MongoDB and configure, seed, and run the API by following the
   [service setup instructions](https://github.com/seenoinaurori/library-catalog-service#setup).
2. In another terminal, clone this repository, then run:

   ```bash
   npm install
   npm run dev
   ```

3. Open the local URL printed by Vite (typically `http://localhost:5173`).

The Vite development server proxies `/books` and `/genres` to
`http://localhost:3000`. To use another API origin, update the proxy in
`vite.config.js`.

## Filtering and search

The client uses API-side filtering rather than downloading the full catalog.
It calls `GET /books` with the current `genre`, `search`, `page`, and `limit`
parameters, so genre and search narrow results together and pagination remains
server-backed. Genre options come from `GET /genres`. Search changes are
committed after a 400 ms debounce.

## Demo

Record a short screen capture or GIF showing browsing the catalog, selecting a
genre, searching while the genre remains selected, and opening a book detail
page. Add the recording link here or commit a GIF and embed it like this:

```md
![Catalog demo](./catalog-demo.gif)
```
