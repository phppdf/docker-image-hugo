FROM hugomods/hugo:exts AS development

WORKDIR /src/docs

ENTRYPOINT ["hugo"]

CMD ["server", "--bind", "0.0.0.0", "--baseURL", "http://localhost:1313/", "--watch"]
