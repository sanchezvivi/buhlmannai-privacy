# Dive-site gazetteer — attribution & license

`dive-sites-osm.json` is a build-time snapshot produced by
[`scripts/build-gazetteer.mjs`](../../../scripts/build-gazetteer.mjs). It is
fetched on a dev machine and committed as a tracked asset; the app **never**
fetches it at runtime (project constraint D5 — no egress of dive-site data).

## Source

Structured OSM-derived fields from
[`jbunderwater/dive-vibe-community`](https://github.com/jbunderwater/dive-vibe-community),
`data/osm_clean/*.json` only. The per-site markdown prose in that repo is
**deliberately excluded** — it is AI-summarised derivative text citing
third-party commercial dive-tourism sites and carries a redistribution risk. We
bundle only `{name, lat, lng, type, depth_m?}`.

## License — ODbL 1.0

The data is OpenStreetMap-derived and redistributed under the
[Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/).

Required attribution (surfaced in-app on the map attribution line):

> © OpenStreetMap contributors — https://www.openstreetmap.org/copyright
> via dive-vibe-community

## Share-alike (NEEDS-HUMAN, light sign-off — ADR-012 D-2c)

ODbL share-alike attaches to the derivative database. Whether embedding this file
in a closed app bundle satisfies "make available under ODbL" is unresolved by the
source's own docs. Proposed low-risk resolution: publish this exact JSON file at a
public URL alongside the app. Not blocking; awaiting Vivi's yes/no.

## Refresh

Re-run `node scripts/build-gazetteer.mjs` to regenerate. Output is deterministic
(sorted, fixed key order) so diffs are reviewable. Staleness only matters at the
next app release.

## File separation (ADR-012 D-2c)

Each source ships as its own file so its license statement stays unambiguous. A
future Overpass `sport=scuba_diving` supplement (also ODbL) would be a separate
`dive-sites-overpass.json`, never merged into this one.
