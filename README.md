# docker-image-hugo

A Docker image that runs the Hugo CLI against a project's documentation.

The image expects the project to be mounted at `/src`, with a Hugo site at `/src/docs`. The
entrypoint is `hugo` itself, so any Hugo subcommand can be used. By default (no command override)
it runs `hugo server`, bound to `0.0.0.0:1313`.

## Usage

Run the development server:

```yaml
services:
  docs-webserver:
    image: ghcr.io/phppdf/docker-image-hugo:dev
    volumes:
      - ./:/src
    ports:
      - "1313:1313"
```

Run other Hugo commands by overriding the command, e.g. to build the site:

```sh
docker run --rm -v ./:/src ghcr.io/phppdf/docker-image-hugo:dev build
```
