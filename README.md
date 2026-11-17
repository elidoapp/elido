# Elido

**Short links, QR codes and click analytics, built EU-first.**

[Website](https://elido.app) · [Docs](https://elido.app/docs) · [Pricing](https://elido.app/en/pricing) · [Changelog](https://elido.app/en/changelog)

Elido is a URL shortener for marketers, agencies and developers: branded short links on your own domain,
dynamic QR codes, link-in-bio pages, UTM campaigns and click analytics, with a REST API and official SDKs.

This repository is the public home of the Elido project on GitHub: start here for the SDKs, the API and
for reporting issues. The Elido service itself is closed source.

## Official SDKs and tools

| Package | Install | Repository |
| --- | --- | --- |
| TypeScript / JavaScript | `npm install @elido/sdk` | [elidoapp/elido-js](https://github.com/elidoapp/elido-js) |
| Python | `pip install elido-sdk` | [elidoapp/elido-python](https://github.com/elidoapp/elido-python) |
| Go | `go get github.com/elidoapp/elido-go@latest` | [elidoapp/elido-go](https://github.com/elidoapp/elido-go) |
| Ruby | not on RubyGems yet; build from source | [elidoapp/elido-ruby](https://github.com/elidoapp/elido-ruby) |
| MCP server (Claude, Cursor and other MCP clients) | `npx @elido/mcp-server` | [elidoapp/mcp-server](https://github.com/elidoapp/mcp-server) |

All SDKs are MIT-licensed.

## Quick start

Create an API key in the Elido dashboard (it starts with `elido_`), then:

```ts
import { ElidoApi } from "@elido/sdk";

const sdk = new ElidoApi({ baseUrl: "https://api.elido.app", token: process.env.ELIDO_TOKEN });

const link = await sdk.links.create(workspaceId, {
  domain_id: domainId,
  destination_url: "https://example.com/landing",
});

console.log(link.slug);
```

Or call the REST API directly with `Authorization: Bearer <key>` on `https://api.elido.app`.
The full API reference is in the [docs](https://elido.app/docs).

## Plans

Free for solo use (25 links, 500 tracked clicks a month), Pro from €3.50 a month, Business from €70 a month.
Current limits and prices: [elido.app/en/pricing](https://elido.app/en/pricing).

## Feedback and issues

- Bug in an SDK: open an issue in that SDK's repository.
- Anything else (the service, the API, feature requests): [open an issue here](https://github.com/elidoapp/elido/issues).
- Security reports: please do not open a public issue; email security@elido.app.
