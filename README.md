# Excession Labs public security APIs: Postman collection

A Postman collection (v2.1) for the public endpoints of [Excession Labs](https://excessionlabs.ai), a security lab. Each request has a description and tests. No credentials are needed.

## Requests

| Request | Endpoint |
| --- | --- |
| Check security headers | `GET https://penetrationtestservices.com/api/check-headers?url={{target}}` |
| MCP: tools/call check_security_headers | `POST https://penetrationtestservices.com/mcp` |
| Provider dataset (JSON) | `GET https://pentestcompare.com/data/providers.json` |
| Provider dataset (CSV) | `GET https://pentestcompare.com/data/providers.csv` |
| Search index | `GET https://pentestcompare.com/search-index.json` |
| API catalog | `GET https://pentestcompare.com/.well-known/api-catalog` |
| MCP: tools/list | `POST https://pentestcompare.com/mcp` |
| MCP: tools/call list_providers | `POST https://pentestcompare.com/mcp` |

## Use it

1. In Postman, choose Import and select `excession-labs-public-security-apis.postman_collection.json`.
2. Change the `target` collection variable if you want to check a URL other than `https://example.com`.
3. Send a request, or run the whole collection.

To run it from the command line:

```
npx -y newman run excession-labs-public-security-apis.postman_collection.json
```

Last run on 2026-11-09: 8 requests, 35 assertions, 0 failures.

## Limits

- The header checker allows 12 requests per minute per IP. One run of the collection sends two requests to it (REST and MCP).
- The checker reads response headers only. It is not a penetration test. Check only sites you own or have permission to check.

## Licenses

- The collection is MIT licensed (see `LICENSE`).
- The provider data from pentestcompare.com is CC BY 4.0. Credit: Excession Labs, pentestcompare.com.
