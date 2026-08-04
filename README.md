# NSW Land Registry Services (nsw-land-registry)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

NSW Land Registry Services (NSW LRS) operates the Torrens Title Register for New South Wales, Australia's largest property market, under a concession granted by the NSW Government on 1 July 2017 and held by Australian Registry Investments Pty Ltd (ACN 617 926 020) as trustee for the Australian Registry Investments Trust. It is a privatised operator of a public record: the Registrar General retains the statutory authority and the Office of the Registrar General regulates the concession, while NSW LRS runs the register, examines and registers dealings and plans, and sells access to the resulting data. It sits at the legal foundation of the Australian value chain — beneath the REA Group and Domain portal duopoly, beneath PropTrack and CoreLogic valuation, and beneath PEXA and Sympli, the Electronic Lodgment Network Operators through which every Real Property Act dealing must now be lodged. Its API posture is the sharpest example in this study of a registry that is technically modern and commercially closed. There is no developer portal, no developer or docs subdomain, no published API programme, no OpenAPI or Swagger document, no SDK, no Postman workspace, no webhook catalogue and no GitHub organization. Access to the register itself is gated behind a licence: the site states plainly that "Only an information broker we've authorised can access our records". What does exist, and what this profile records, are three genuinely reachable machine-readable surfaces that NSW LRS never advertises to developers — a Cantaloupe IIIF Image API 2.0 Level 2 endpoint, an anonymously callable Elasticsearch search proxy over 7,160,622 indexed historical documents, and a publicly downloadable W3C XML Schema for the NSW ePlan LandXML vocabulary. The contracts are open; the licence is not.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/nsw-land-registry/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/nsw-land-registry/refs/heads/main/apis.yml)

## Tags

- Real Estate
- Australia
- Land Registry
- Title
- Conveyancing
- Property Records
- Torrens Title
- eConveyancing
- Government
- Geospatial
- PropTech

## Timestamps

- **Created:** 2026-07-26
- **Modified:** 2026-07-26

## APIs

### NSW LRS Historical Land Records Viewer IIIF Image API

A live Cantaloupe Image Server exposing the International Image Interoperability Framework (IIIF) Image API 2.x over the scanned NSW land record images behind the Historical Land Records Viewer. Verified anonymously on 2026-07-26: the endpoint root returned HTTP 200 with the Cantaloupe "IIIF Image API 2.x Endpoint" documentation page, an image information document returned HTTP 200 declaring compliance profile `http://iiif.io/api/image/2/level2.json`, and a derivative render at `/full/200,/0/default.jpg` returned HTTP 200 with `Content-Type: image/jpeg` and 16,798 bytes of a real scanned NSW land record. Identifiers are constructed by the HLRV client as URL-encoded `location + "/" + fileName` over JPEG2000 masters. NSW LRS publishes no documentation, no OpenAPI, no key issuance and no rate-limit statement for this endpoint.

- **Human URL:** [https://hlrv.nswlrs.com.au/](https://hlrv.nswlrs.com.au/)
- **Base URL:** `https://api.lrsnative.com.au/hlrv/iiif/2`

#### Tags

- Land Registry
- Historical Records
- IIIF
- Images
- Australia

#### Properties

- [Schema](openapi/nsw-land-registry-hlrv-iiif-image-information.json) — IIIF Image API 2.0 image information document
- [Documentation](https://hlrv.nswlrs.com.au/)
- [Documentation](https://nswlrs.com.au/services/record-searches/historical-research)
- [Standard](https://iiif.io/api/image/2.1/)
- [Terms of Service](https://nswlrs.com.au/about-us/policies/terms-conditions)

### NSW LRS Historical Land Records Viewer Document Search API

An Elasticsearch search proxy that backs the Historical Land Records Viewer and answers anonymously. `POST https://api.lrsnative.com.au/hlrv/documents/_msearch` with an ndjson body returned HTTP 200 with `hits.total` 7,160,622 across three shards, with no credential supplied (2026-07-26). Returned documents carry `collectionId`, `collectionName`, `documentId`, `imageType`, `imageName`, `bookAndNumber`, `scanTimestamp` and an `images` array of JPEG2000 files — the exact fields needed to build IIIF identifiers. Sibling routes are not open: `GET /hlrv/documents` returned 503, `POST /hlrv/documents/_search` returned 400, `POST /hlrv/lotsearch/search` returned 500. There is no published contract and no terms permitting programmatic use.

- **Human URL:** [https://hlrv.nswlrs.com.au/](https://hlrv.nswlrs.com.au/)
- **Base URL:** `https://api.lrsnative.com.au/hlrv/documents`

#### Tags

- Land Registry
- Historical Records
- Search
- Elasticsearch
- Australia

#### Properties

- [Documentation](https://hlrv.nswlrs.com.au/)
- [Documentation](https://nswlrs.com.au/services/record-searches/how-to-find-a-record)
- [Terms of Service](https://nswlrs.com.au/about-us/policies/terms-conditions)

## RESO Posture

**No RESO reference found. Not certified.**

RESO's full published certified-organizations list at [https://www.reso.org/certificates/](https://www.reso.org/certificates/) (HTTP 200, 416,233 bytes, fetched 2026-07-26) contains zero occurrences of "Austral" in any form and no NSW Land Registry Services entry. RESO's own Certification and MLS Map page frames the standard's geography as "489 functioning MLS systems in the United States, more than 30 in Canada and a small but increasing number in Central America, South America, Europe and West Asia" — Australia is not named, and RESO publishes a dedicated Canadian membership roster with no Australian equivalent.

From the NSW LRS side, every harvested page was scanned for RESO, OData, Data Dictionary, `$metadata`, Universal Property Identifier and UPI; the only hits were the substring "reso" inside "resources". Direct OData probes failed in every case: `https://www.nswlrs.com.au/$metadata` → 404, `https://api.nswlrs.com.au/$metadata` → 403, `https://api.lrsnative.com.au/$metadata` → 400. No UPI is used; NSW keys land on the Torrens folio identifier derived from lot and plan number (for example `1/12345`).

The absence is structurally expected. RESO is a NAR-driven North American MLS construct; Australia has no MLS at all, and NSW LRS is a statutory land registry operator rather than a listings body. The real machine-readable vocabulary here is **LandXML 1.2 constrained by the ICSM ePlan Cadastral Information File schema** — harvested to `openapi/nsw-land-registry-eplan-cif-enumerated-types-4-0.xsd`.

## Access Gate

**broker-or-agent-only** — a developer cannot obtain NSW Torrens Title Register data from NSW LRS directly.

> "Information brokers deliver and on-sell land titling and related property information through an official licence agreement with NSW LRS. ... Only an information broker we've authorised can access our records."
>
> — [nswlrs.com.au/services/record-searches/how-to-find-an-information-broker](https://nswlrs.com.au/services/record-searches/how-to-find-an-information-broker)

The same page invites "interested parties to apply to become a broker at any time" — and that link resolves to the generic contact page. There is no application form, no eligibility criteria, no technical requirements and no fee schedule. The authorised broker and reseller network named on the site includes InfoTrack / InfoTrackGO, Dye & Durham, Equifax, CITEC Confirm, TriSearch, Hazlett, LegalStream, Landchecker, Fynd, PSI Global, Directinfo, Australian Land Title Search, CheckThatProperty, Citylegal, Landtitles.com.au, Title Check and Trustdeed.com, with a published single-transaction price table (last updated 1 April 2026) ranging from **AUD 19.49 to AUD 98.00** for the same statutory title search.

Three gates in total:

1. **Reads** — authorised information broker under a licence agreement, or purchase from one.
2. **Writes** — ELNO subscriber registration with [PEXA](https://www.pexa.com.au/) or [Sympli](https://www.sympli.com.au/) under the Electronic Conveyancing National Law, restricted to conveyancers, lawyers, councils and banks, with seven-year record retention and compliance examinations by NSW LRS under delegated section 33 ECNL authority. Plan lodgment runs exclusively through LRS Connect (Mandate 1, 1 July 2025).
3. **Wholesale data** — Property Alerts, Lease Notifications, Mortgage Insights and Mortgage Verifications are sold by emailing `datasolutions@nswlrs.com.au`. No self-serve path, no pricing, no schema, no delivery mechanism published.

## Open Data

**None.** NSW LRS is not a publishing organization on [data.nsw.gov.au](https://data.nsw.gov.au) — CKAN `package_search` returned count 0 for `organization:nsw-land-registry-services`, count 0 for `"NSW LRS"` and count 0 for `nswlrs` on 2026-07-26, and the 243-organization list contains no land-registry entry. The NSW Land Parcel and Property Theme layers on the portal belong to Spatial Services (DCS), a separate agency.

Free is not open. The Online Portal offers free web-form searches (street address inquiry, reverse street address inquiry, water access licence inquiry, document inquiry, plan inquiry, deed name and number search, land value search for owners) behind a portal session with no API and no licence grant. The Historical Land Records Viewer is free and account-free, but its click-through terms are a licence that prohibits precisely the use its open backend permits:

> "2.1 Unless otherwise agreed in writing by NSW LRS, you are prohibited from: (a) on-selling, or on-supplying, or sub-licensing products in any form ... (d) rebroadcasting, reformatting, making available online or reconstructing products or part thereof; or (e) otherwise publishing, blending or dealing with the products, or (f) data aggregating, data matching, marketing, compilation of mailing lists, list brokering ..."
>
> "3.6 You agree that you will not use any device, software or routine to abuse the service of HLRV or emulate human interaction and operation."

No Creative Commons licence, no Open Government Licence, no attribution statement and no reuse grant appears anywhere in the NSW LRS estate. Compare HM Land Registry, which serves Price Paid Data anonymously under Open Government Licence v3.0.

## Auth Model

No developer authentication model is published. Three real schemes were observed:

- **`api.nswlrs.com.au`** is AWS API Gateway and answers every anonymous request with HTTP 403 `ForbiddenException` (`x-amzn-errortype`, `x-amz-apigw-id` headers present) on `/`, `/v1`, `/health`, `/docs`, `/openapi.json`, `/swagger.json`, `/api-docs`, `/$metadata` and `/.well-known/openid-configuration`. A private API estate exists; nothing is published about it.
- **LRS Connect** (`connect.nswlrs.com.au`) is an OutSystems React application with an ordinary subscriber login. Its unauthenticated manifest at `/moduleservices/moduleinfo` returned HTTP 200 with 258,969 bytes of module metadata, but `/rest`, `/Connect/rest/`, `/api`, `/screenservices` and `/ConnectAPI/rest/` all returned 404 — no REST module is exposed.
- **HLRV** carries an `x-portal-token` JWT verified client-side against an RSA public key embedded in the bundle, used to unlock restricted collection IDs — but it is not enforced server-side on `/hlrv/documents/_msearch`.

No OpenID Connect discovery document is served on any host (404/403/400 across five probes). No SAML metadata. No `security.txt`.

## Webhooks, Events, SDKs, Postman

None published — notable because NSW LRS *sells* an event product. Property Alerts promises alerts "in near real-time" and "early warning up to 28 days of refinance and property sale activity prior to the PEXA workspace — the earliest warning available in the market"; Lease Notifications promises continuous monitoring "at your preferred frequency". Neither publishes a delivery mechanism, payload schema, endpoint, subscription API or AsyncAPI document. The entire technical contract is an email address.

No SDK, client library or CLI. No GitHub organization (repository search for `nswlrs` returned `total_count` 0). No Postman workspace. A real [status page](https://status.nswlrs.com.au/) does exist, with email and SMS incident subscriptions covering the Online Portal, Information Broker Services, the websites, LRS Connect and ELNO.

## Harvested Artifacts

| File | What it is | Source | Status |
|---|---|---|---|
| [`openapi/nsw-land-registry-hlrv-iiif-image-information.json`](openapi/nsw-land-registry-hlrv-iiif-image-information.json) | IIIF Image API 2.0 image information document (939 bytes, valid JSON, Level 2 profile) | `api.lrsnative.com.au/hlrv/iiif/2/{id}/info.json` | 200, 2026-07-26 |
| [`openapi/nsw-land-registry-eplan-cif-enumerated-types-4-0.xsd`](openapi/nsw-land-registry-eplan-cif-enumerated-types-4-0.xsd) | ICSM ePlan CIF enumerated types, W3C XML Schema v4.0, 44 `xs:simpleType` definitions pinning NSW LandXML 1.2 jurisdictional values | `nswlrs.com.au/assets/f/1129775276948026/x/7d398c2b5a/...` | 200, 2026-07-26 |

No OpenAPI, Swagger, AsyncAPI, GraphQL SDL, WSDL, OData `$metadata`, RESO Data Dictionary or JSON Schema document exists anywhere in the NSW LRS estate. Nothing was authored to fill the gap.

## Corporate Structure

A privatised operator of a public register. The operating entity is "Australian Registry Investments Pty Ltd (ACN 617 926 020) as trustee for the Australian Registry Investments Trust (trading as NSW Land Registry Services)". Per the regulator page: "As of 1 July 2017, NSW LRS maintain the Torrens Register on behalf of the Registrar General under a concession granted to them by the NSW government."

NSW LRS is a founding member of [Australian Land Registry Operators (ALRO)](https://auslro.com.au/), "a collective of the five privately operated land registries and service providers across Australia" alongside Secure Electronic Registries Victoria (SERV), Titles Queensland, Land Services SA and Land Services WA — together "95% of the nation's land registry data" supporting "more than $10 trillion in residential property by value". Four of Australia's five largest state land registries are now privately operated and collectively marketing national property data products.

## Review

See [`review.yml`](review.yml) for the full probe log: every URL tested, its HTTP status, the DNS resolution results, the verbatim RESO and licence evidence, and the provenance of each harvested artifact.

## Maintainers

- Kin Lane — kin@apievangelist.com
