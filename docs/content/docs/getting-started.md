---
title: "Getting started"
weight: 10
---

The image is based on [`hugomods/hugo:exts`](https://github.com/hugomods/docker) and expects the
project to be mounted at `/src`, with a Hugo site at `/src/docs`.

## Running the development server

By default (when no command is given), the image runs `hugo server`, bound to `0.0.0.0:1313`:

```yaml
services:
  docs-webserver:
    image: ghcr.io/phppdf/docker-image-hugo:dev
    volumes:
      - ./:/src
    ports:
      - "1313:1313"
```

With the example above, the site is available at `http://localhost:1313/`.

## Running other Hugo commands

The image's entrypoint is `hugo` itself, so any Hugo subcommand can be run by overriding the
container's command. For example, to build the site:

```sh
docker run --rm -v ./:/src ghcr.io/phppdf/docker-image-hugo:dev build
```

See [the CLI page](../cli/) for more details.
