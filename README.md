# Stoplight - Spectral CLI

A simple example running
[spectral-cli](https://github.com/stoplightio/spectral)
on docker to validade using default
[OpenAPI Rules](https://meta.stoplight.io/docs/spectral/4dec24461f3af-open-api-rules).

```bash
docker run --rm -it -v $(pwd):/tmp stoplight/spectral lint \
  --ruleset "/tmp/.spectral.yaml" \
  "/tmp/docs/petstore.yaml"
```

Output:

```bash
2:6    warning  info-contact           Info object must have "contact" object.
2:6    warning  info-description       Info "description" must be present and non-empty string.
11:9   warning  operation-description  Operation "description" must be present and non-empty string.
15:11  warning  operation-tag-defined  Operation tags must be defined in global tags.
42:10  warning  operation-description  Operation "description" must be present and non-empty string.
46:11  warning  operation-tag-defined  Operation tags must be defined in global tags.
57:9   warning  operation-description  Operation "description" must be present and non-empty string.
61:11  warning  operation-tag-defined  Operation tags must be defined in global tags.

✖ 8 problems (0 errors, 8 warnings, 0 infos, 0 hints)
```

[Full documentation](https://meta.stoplight.io/docs/spectral)
