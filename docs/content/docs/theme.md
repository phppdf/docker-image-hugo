---
title: "Theme"
weight: 40
---

The image bundles the `phppdf-docs` Hugo theme, so projects don't need to vendor a copy of it
under `docs/themes/`.

The theme is copied into the image at `/hugo-themes/phppdf-docs`, and `HUGO_THEMESDIR` is set to
`/hugo-themes`. To use it, simply reference it by name in `hugo.toml`:

```toml
theme = "phppdf-docs"
```

No other configuration or local theme files are required.

## Site parameters

The theme reads a few values from `[params]` in `hugo.toml`:

- `tagline` &mdash; shown in the page title, meta description and topbar.
- `sourceURL` &mdash; if set, shows a "Source" link in the topbar pointing at the project's
  repository. If omitted, the link is hidden.
