---
title: "docker-image-hugo documentation"
---

`docker-image-hugo` is a Docker image that runs [Hugo](https://gohugo.io/) against a project's
documentation site. It bundles the Hugo CLI (with extended/Sass support) and uses it directly as
the image's entrypoint, so it can be used both to serve docs during development and to run any
other Hugo command, such as `build`.
