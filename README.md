# NSW Land Registry Services

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

NSW Land Registry Services (NSW LRS) operates the Torrens Title Register for New South Wales, Australia's largest property market, under a concession granted by the NSW Government on 1 July 2017 and held by Australian Registry Investments Pty Ltd (ACN 617 926 020) as trustee for the Australian Registry Investments Trust. It is a privatised operator of a public record: the Registrar General retains the statutory authority and the Office of the Registrar General regulates the concession, while NSW LRS runs the register, examines and registers dealings and plans, and sells access to the resulting data. It sits at the legal foundation of the Australian value chain, beneath the REA Group and Domain portal duopoly, beneath PropTrack and CoreLogic valuation, and beneath PEXA and Sympli, the Electronic Lodgment Network Operators through which every Real Property Act dealing must now be lodged. Its API posture is the sharpest example in this study of a registry that is technically modern and commercially closed. There is no developer portal, no developer or docs subdomain, no published API programme, no OpenAPI or Swagger document, no SDK, no Postman workspace and no GitHub organization. One documented, anonymously callable API does exist, and it is not about land: the NSW LRS status page is an Atlassian Statuspage with the public v2 API enabled and referenced at status.nswlrs.com.au/api, publishing 27 components — among them an "API Service" component under Information Broker Services that confirms from the registry's own mouth that a production API estate sits behind the broker licence — plus RSS and Atom incident feeds and webhook notifications on incident and component changes. Access to the register itself is gated behind a licence: the site states plainly that "Only an information broker we've authorised can access our records", and those brokers — InfoTrack, Dye & Durham, Equifax, CITEC Confirm, TriSearch, Landchecker, Fynd, PSI Global and others — "deliver and on-sell land titling and related property information through an official licence agreement with NSW LRS". Wholesale data products (Property Alerts, Lease Notifications, Mortgage Insights, Mortgage Verifications) are sold by emailing datasolutions@nswlrs.com.au, with no self-serve path and no published technical contract. What does exist, and what this profile records, are three genuinely reachable machine-readable surfaces that NSW LRS never advertises to developers: a Cantaloupe IIIF Image API 2.0 Level 2 endpoint serving the scanned historical land records behind the Historical Land Records Viewer, an anonymously callable Elasticsearch search proxy over 7,160,622 indexed historical documents, and a publicly downloadable W3C XML Schema for the ICSM ePlan Cadastral Information File enumerated types that pins the NSW LandXML jurisdictional vocabulary now mandatory for digital plan lodgment. The contracts are open; the licence is not — the HLRV terms of use prohibit on-supply, data aggregation, republishing and "any device, software or routine to abuse the service of HLRV or emulate human interaction and operation". RESO is entirely absent: NSW LRS appears nowhere in RESO's certified-organizations list, there is no RESO Web API or Data Dictionary certification, no OData $metadata document and no Universal Property Identifier, which is the expected answer for Australia, where RESO is a North American NAR construct with no adoption. No open, unlicensed dataset is published — NSW LRS is not a publishing organization on data.nsw.gov.au — and a privatised registry selling the public record back through a licensed broker channel is itself the finding. The registry does publish its language: a 257-term glossary of NSW land titling definitions, harvested here as the controlled vocabulary that stands in for the data dictionary it never wrote.

**Areas:** Real Estate · Australia · Land Registry · Title · Conveyancing · Property Records · Torrens Title · eConveyancing · Government · Geospatial · PropTech

## NSW Land Registry Services on APIs.io

Everything profiled for NSW Land Registry Services is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/nsw-land-registry/](https://apis.io/providers/nsw-land-registry/)** — or go straight to one of the APIs or properties below.

### APIs (3)

- [NSW LRS Historical Land Records Viewer IIIF Image API](https://apis.io/apis/nsw-land-registry/nsw-lrs-hlrv-iiif-image-api/) — A live Cantaloupe Image Server exposing the International Image Interoperability Framework (IIIF) Image API 2.x over the scanned NSW land record images…
- [NSW LRS Historical Land Records Viewer Document Search API](https://apis.io/apis/nsw-land-registry/nsw-lrs-hlrv-document-search-api/) — An Elasticsearch search proxy that backs the Historical Land Records Viewer and answers anonymously. Verified on 2026-07-26: POST…
- [NSW LRS Status API](https://apis.io/apis/nsw-land-registry/nsw-lrs-status-api/) — The one documented, publicly callable API NSW Land Registry Services operates. The NSW LRS status page at status.nswlrs.com.au is an Atlassian Statuspage…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Nsw Land Registry Status Webhooks](https://apis.io/asyncapis/nsw-land-registry/nsw-land-registry-status-webhooks/)

#### Examples (5)

Example requests and responses.

- [Nsw Land Registry Hlrv Msearch Response](https://apis.io/examples/nsw-land-registry/nsw-land-registry-hlrv-msearch-response/)
- [Nsw Land Registry Status Components](https://apis.io/examples/nsw-land-registry/nsw-land-registry-status-components/)
- [Nsw Land Registry Status Incidents Unresolved](https://apis.io/examples/nsw-land-registry/nsw-land-registry-status-incidents-unresolved/)
- [Nsw Land Registry Status Scheduled Maintenances Upcoming](https://apis.io/examples/nsw-land-registry/nsw-land-registry-status-scheduled-maintenances-upcoming/)
- [Nsw Land Registry Status Status](https://apis.io/examples/nsw-land-registry/nsw-land-registry-status-status/)

#### Collections (1)

Postman and Open Collection request collections.

- [API Collection](https://apis.io/collections/nsw-land-registry/open-nsw-land-registry-hlrv-iiif-image-information/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Nsw Land Registry Authentication](https://apis.io/security/nsw-land-registry/nsw-land-registry-authentication/)
- [Nsw Land Registry Domain Security](https://apis.io/security/nsw-land-registry/nsw-land-registry-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://nswlrs.com.au/)
- [Documentation](https://nswlrs.com.au/glossary-of-terms)
- [Pricing](https://nswlrs.com.au/services/fees-payments/fees)
- [Support](https://nswlrs.com.au/about-us/contact-us)
- [Changelog](https://nswlrs.com.au/about-us/education-hub/lrs-connect-release-schedule)
- [Blog](https://nswlrs.com.au/about-us/announcements)
- [Terms of service](https://nswlrs.com.au/about-us/policies/terms-conditions)
- [Privacy policy](https://nswlrs.com.au/about-us/policies/privacy-policy)
- [Status](https://status.nswlrs.com.au/)

## API Evangelist rating

**Kin Score 46.9** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 45.3 |
| Contract governance | 33.3 |
| Operational transparency | 39.5 |
| Developer ergonomics | 45.2 |
| Access clarity | 44.7 |

**Agent readiness 23.9** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | — |
| Event Surface Described | yes |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 22.1** — Government & Public Sector

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/nsw-land-registry/](https://apis.io/providers/nsw-land-registry/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for NSW Land Registry Services: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/nsw-land-registry/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
