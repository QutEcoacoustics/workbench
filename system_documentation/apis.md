# APIs

The workbench is almost totally surfaced by a REST API. This API is documented
using [Swagger](https://swagger.io/). The API documentation is available at
`/api-docs` on the server.

We also include supplemental documentation here.

## Historical documentation

This documentation was historically located in the [baw-server Wiki](https://github.com/QutEcoacoustics/baw-server/wiki).
It will remain there for some time, until the migration to this repository is compelted.

## Authentication & Authorization

The server is designed to allow public access to data that is marked to be public.
Most actions a user can take are categorized into a few classes:

- reading of public data with requires _no authentication_
- writing data for things your create or own requires an _authenticated_ session
- reading of some important public data requires an _authenticated_ session
- reading or writing private data requires an _authenticated and authorized_ session

If authentication is required the API will return a `401 Unauthorized` response.
If authorization is required the API will return a `403 Not Authorized` response.

