# Wodin static scrollytelling demo (Royal Society model)

This repo is a prototype static Wodin site.

- The odin model lives in `stores/viral_respiratory/model.R`.
- The scrollytelling page lives in `index.html`.
- GitHub Actions builds and publishes the site using `mrc-ide/wodin-builder-action`.

## How widgets are wired (high level)

- Wodin mounts Vue components into `div` placeholders in `index.html`. Placeholders are identified by CSS classes such as `w-run-graph`, `w-sens-graph`, and `w-par`.
- Every placeholder must include `data-w-store="STORE_NAME"`.
- `STORE_NAME` can include a suffix (for example `viral_respiratory:1`). The part before `:` must match a folder name under `stores/`.
- Placeholders that share the same `data-w-store` value share state (parameters and results). Use different suffixes (`:1`, `:2`, etc) to create independent instances.

## Build output

The build process compiles the odin model with `odin.api` and writes compiled artefacts into the published site under `stores/`.
