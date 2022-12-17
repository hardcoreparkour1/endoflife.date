## API v1.0.0

### Summary

API v1 is a major rework of the API v0 with a lot of breaking changes. Compared to the API v0, API v1:

- feels more "Restful",
- is versioned using the `api/v1` prefix, making it easier to implement non-backward-compatible
  changes,
- is generated using a Jekyll Generator (see https://jekyllrb.com/docs/plugins/generators/).

API v1 resolves : #394, #759, #905, #2062, #2066, #2078, #2160, #2331, #2431, #2595. It also reverts
#2425 due to incompatibilities in redirect rules.

The API v0 is still generated to give time to users to migrate to API v1.

### Changes in the "All products" endpoint

- Path has been changed from `api/all.json` to `api/v1/products/`
- Response has been changed from a simple array to a JSON document. This made it possible to add endoflife-level data, such as the number of products.
- Array elements have been changed from a simple string to a full JSON document. This made it possible to expose new data, such as product category and tags (#2062).

### Changes in the "Product" endpoint

- Path has been changed from `api/<product>.json` to `api/v1/products/<product>/`.
- Response has been changed from a simple array to a JSON document. This made it possible to expose product-level data, such as product category and tags (#2062).
- Cycles data now always contain all the release cycles properties, even if they are null (example: `discontinued`, `latest`, `latestReleaseDate`, `support`...).

### Changes in the "Cycle" endpoint

- Path has been changed from `api/<product>/<cycle>.json` to `api/v1/products/<product>/cycles/<cycle>/`.
- Cycles data now always contain all the release cycles properties, even if they are null (example: `discontinued`, `latest`, `latestReleaseDate`, `support`...).
- A special `/api/v1/products/<product>/cycles/latest/` cycle, containing the same data as the latest cycle, has been added (#2078).

### Changes in 404 error responses

404 error JSON responses are not returned anymore. #2425 has been reverted because it conflicted
with the rule that rewrites the paths to add `/index.json` to all requests, which is also a global
rule and [takes precedence](https://docs.netlify.com/routing/redirects/#rule-processing-order).

### New endpoints

- `/api/v1/categories/` - list categories used on endoflife.date
- `/api/v1/categories/<category>` - list products having the given category
- `/api/v1/tags/` - list tags used on endoflife.date
- `/api/v1/tags/<tag>` - list products having the given tag



## API v0

On 2023-03-02 the v0 endpoints were:

- "All products" (`/api/all.json`) : Return a list of all products.
- "Product" (`/api/{product}.json`) : Get EoL dates of all cycles for a given product.
- "Cycle" (`/api/{product}/{cycle}.json`) : Details of a single release cycle of a given product.
