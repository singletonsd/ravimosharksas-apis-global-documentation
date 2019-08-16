# RavimoShark SAS - APIS - Global - Documentation

> The **main repository** is hosted in [gitlab.com/ravimosharksas/apis/global/documentation](https://gitlab.com/ravimosharksas/apis/global/documentation.git) but it is automaticaly mirrored to [github.com](https://github.com/singletonsd/ravimosharksas-apis-global-documentation.git) and to [gitlab.com/singletonsd/ravimosharksas/apis/global/documentation](https://gitlab.com/singletonsd/ravimosharksas/apis/global/documentation.git). If you are in the Github page it may occur that is not updated to the last version.

## PROJECT INFORMATION

<img src="http://online.swagger.io/validator?url=https://ravimosharksas.gitlab.io/apis/global/documentation/swagger.yaml">

Swagger documentation of global API. See HTML documentation in
[https://ravimosharksas.gitlab.io/apis/global/documentation](https://ravimosharksas.gitlab.io/apis/global/documentation)

## Links

- [Reference Documentation (ReDoc)](https://ravimosharksas.github.io/apis/)
- [SwaggerUI](https://ravimosharksas.github.io/apis/swagger-ui/)
- OpenAPI Raw Files: [JSON](https://ravimosharksas.github.io/apis/openapi.json) [YAML](https://ravimosharksas.github.io/apis/openapi.yaml)

**Warning:** All above links are updated only after Travis CI finishes deployment

## Usage

### `npm start`

Starts the development server.

### `npm run build`

Bundles the spec and prepares web_deploy folder with static assets.

### `npm test`

Validates the spec.

### `npm run gh-pages`

Deploys docs to GitHub/Gitlab Pages.

## HOW TO WORK

### DEFINITIONS

- Write each path specification in separate file.
- The file name will be the object name with the same spelling and casing.

### PATHS

- Write each path specification in separate file
- Filename is mapped to path by replacing `@` with `/`, i.e. `user@{username}.yaml` matches to `user/{username}` path

### Global headers (only for OpenAPI 2)

When using OpenAPI 2 you can minimize headers duplications by using `headers` global object (similar to `definitions`, `responses`).
During build process all references to global `headers` will be inlined and `headers` will be removed from the resulting spec (global `headers` are not allowed by OpenAPI 2 spec). Example:

```yaml
...
headers:
  Rate-Limit-Limit:
    description: The number of allowed requests in the current period
    type: integer
...
paths:
  /api-keys:
    get:
      summary: Retrieve a list of api keys
      responses:
        200:
          description: A list of api keys was retrieved successfully
          headers:
            Rate-Limit-Limit:
              $ref: "#/headers/Rate-Limit-Limit"
```

## MODEL DIAGRAM

## CONTRIBUTING

Contributions to this repository are very welcome.

To contribute, please fork this repository on GitLab and send a pull request with a clear description of your changes. If appropriate, please ensure that the user documentation in this README is updated.

If you have submitted a PR and not received any feedback for a while, feel free to [ping me on Twitter](https://twitter.com/patoperpetua) [or find me on facebook](https://www.facebook.com/pato.arg)

## Code samples

[x-code-samples](https://github.com/Rebilly/ReDoc/blob/master/docs/redoc-vendor-extensions.md#x-code-samples)
Path `<lang>/<path>/<HTTP verb>.<extension>` where:

- `<lang>` - name of the language from [this](https://github.com/github/linguist/blob/master/lib/linguist/popular.yml) list.
- `<path>` - path of the target method, where all `/` are replaced with `@`.
- `<HTTP verb>` - verb of target method.
- `<extension>` - ignored.

## TODO

- [ ] Config tool to generate models diagram.
- [X] Config client libraries on commit.
- [ ] Config swagger hub integration.
- [X] Upload html documentation to gitlab pages.
- [ ] Upload html documentation to servers.
- [ ] Use scripts from remote repository.
- [ ] Gitlab ci-cd template from remote repository.
- [X] Split swagger.yaml into multiple files.
- [X] Use [ReDoc](https://github.com/Redocly/redoc) documentation framework.

## IMPROVES TO NEXT VERSION

----------------------

© [Singleton](http://www.singletonsd.com), Argentina, 2019.
