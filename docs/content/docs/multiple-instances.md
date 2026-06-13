---
title: "Running multiple instances"
weight: 30
---

Because the image's entrypoint is `hugo` itself, the port the development server listens on can
be overridden by passing different arguments to `hugo server`. This makes it possible to run
several instances of the image at once, each serving a different project on its own port.

## Example

```yaml
services:
  docs-a:
    image: ghcr.io/phppdf/docker-image-hugo:dev
    volumes:
      - ./project-a:/src
    command: server --bind 0.0.0.0 --port 1313 --baseURL http://localhost:1313/ --watch
    ports:
      - "1313:1313"

  docs-b:
    image: ghcr.io/phppdf/docker-image-hugo:dev
    volumes:
      - ./project-b:/src
    command: server --bind 0.0.0.0 --port 1314 --baseURL http://localhost:1314/ --watch
    ports:
      - "1314:1314"
```

Each `command` overrides the image's default `CMD`, so the `--port` and `--baseURL` flags must be
set explicitly to match the port mapping for that service.
