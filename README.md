# LiveSports-EPG

**Purpose:** Public, read-only JSON distribution repository for the separate private [SportsLiveInfo](https://github.com/jimmyfazz/SportsLiveInfo) Home Assistant App and its B1G IPTV clients.

## Current status

**Feed not yet published.** This repository currently contains no `v1/manifest.json`, television EPG programme rows or verified sporting event snapshots. It will be populated by the owner's Home Assistant SportsLiveInfo App only after source redistribution rights are approved and a narrowly scoped GitHub publishing token is configured.

## Expected feed contract (once activated)

- `v1/manifest.json` — the mutable discovery manifest, polled by read-only B1G devices.
- `v1/manifests/<revision>.json` — retained previous manifests for rollback.
- `v1/assets/<kind>/<sha-prefix>.json` — immutable sports, channel identity, taxonomy and approved feed assets.
- Each published asset has a SHA-256 digest in the manifest; clients should verify it before using a new revision.
- The central publisher writes outbound to GitHub; **ten B1G TVs only read** the public HTTPS files.

**Security and rights:** Never commit Home Assistant credentials, API keys, subscription lists, playlist or stream URLs, hidden-category settings or third-party EPG text without redistribution permission. EPG-source collections remain local to Home Assistant unless individually approved. Sporting broadcaster matches are not presented as verified without independent evidence. SportsLiveInfo supplements each B1G subscription's own EPG rather than replacing it.

## Important: not the Home Assistant App installation repository

This repository is the **published data destination**, not a Home Assistant Apps (add-on) store repository. To install the application in Home Assistant, the installer needs access to the separately packaged `SportsLiveInfo` App source repository (and an appropriate distribution arrangement). Do not enter this data repository URL in the Home Assistant Apps custom-repository installer expecting it to install the collector.

## Links

- [SportsLiveInfo App source and documentation](https://github.com/jimmyfazz/SportsLiveInfo)
- [Feed format specification (`sli/1`)](https://github.com/jimmyfazz/SportsLiveInfo/blob/main/docs/FEED_CONTRACT_SLI_V1.md) (private until source distribution is made public)
