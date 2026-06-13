---
title: "Using the Hugo CLI"
weight: 20
---

The image's `ENTRYPOINT` is `hugo`, and its working directory is `/src/docs`. This means the image
can be used as a drop-in Hugo CLI, as long as the project is mounted at `/src`.

## Examples

Build the site into `/src/docs/public`:

```sh
docker run --rm -v ./:/src ghcr.io/phppdf/docker-image-hugo:dev build
```

Scaffold a new content file:

```sh
docker run --rm -v ./:/src ghcr.io/phppdf/docker-image-hugo:dev new content docs/new-page.md
```

Print the Hugo version:

```sh
docker run --rm ghcr.io/phppdf/docker-image-hugo:dev version
```

Any arguments after the image name are passed straight to `hugo`, so the full set of Hugo
subcommands and flags is available. See the
[Hugo CLI documentation](https://gohugo.io/commands/hugo/) for the full reference.
