FROM hugomods/hugo:exts AS development

WORKDIR /src/docs

COPY src/theme /hugo-themes/phppdf-docs

ENV HUGO_THEMESDIR=/hugo-themes

ENTRYPOINT ["hugo"]

CMD ["server", "--bind", "0.0.0.0", "--baseURL", "http://localhost:1313/", "--watch"]
