# ZeroEyes

ZeroEyes is an AI-powered visual firearm detection company founded in 2018 by former U.S. Navy SEALs
and technologists, headquartered in Conshohocken, Pennsylvania. Its computer-vision platform layers
onto a customer's existing IP security cameras (any RTSP-capable camera, 720p or better, 2017 or
newer) to detect brandished firearms. Every AI detection is human-verified in the 24/7 ZeroEyes
Operations Center (ZOC) before an alert carrying imagery, camera location, and a first-responder link
is dispatched.

ZeroEyes sells into K-12 and higher education, commercial and industrial facilities, houses of
worship, gaming, smart cities and transit, and federal government (ZeroEyes Federal / ZEGS), and
complements detection with 3D site mapping and analytics.

## API posture

**ZeroEyes publishes no public API.** Contract discovery in this repo probed every ZeroEyes host for
OpenAPI/Swagger, GraphQL, MCP, and A2A surfaces and found none:

- No `api.`, `developer.`, `docs.`, `app.`, or `portal.` subdomain resolves in DNS.
- `/openapi.json`, `/swagger.json`, `/api-docs` return 404 on `zeroeyes.com`, `www.zeroeyes.com`,
  and `zegs.zeroeyes.com`.
- Every `/.well-known/*` path (security.txt, openid-configuration, oauth-authorization-server,
  api-catalog, ai-plugin.json, agent-card.json, agent.json) returns 404 on every host.
- No first-party packages on npm, PyPI, or GitHub; no `zeroeyes` GitHub organization exists.

Integration is delivered through partner ecosystems — VMS platforms, mass notification, mapping,
robotics, RapidSOS, and ATAK/iTAK — and through camera RTSP streams, not a self-serve developer API.

## What is captured here

| Artifact | Method | What it holds |
|---|---|---|
| `llms/zeroeyes-llms.txt` | searched | Provider-published `llms.txt`, saved verbatim |
| `conformance/zeroeyes-conformance.yml` | searched | FedRAMP Moderate, SOC 2 Type 2, ISO/IEC 27001:2013, DHS SAFETY Act, EU-U.S. DPF, RTSP/RapidSOS/TAK interoperability |
| `security/zeroeyes-trust-center.yml` | searched | Certifications & Designations page + named audits |
| `security/zeroeyes-domain-security.yml` | probed | TLS / HSTS / DNSSEC / CAA / SPF / DMARC posture |
| `well-known/zeroeyes-well-known.yml` | probed | Full `/.well-known/` probe record (all misses) |
| `lifecycle/zeroeyes-lifecycle.yml` | probed | Versioning / deprecation / SLA / status-page negatives — including a provisioned but **inactive** `zeroeyes.statuspage.io` tenant |

- https://zeroeyes.com/
- https://forgeglobal.com/zeroeyes_stock/
