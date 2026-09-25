# Kingfisher reference packs (second mirror)

Static, versioned reference packs read by [Kingfisher](https://kingfisherchess.app/).
The first mirror, [`mardakurt/kingfisher-data`](https://github.com/mardakurt/kingfisher-data),
holds the smaller packs and the monthly update channel; the packs here are the
ones that would take that site past GitHub Pages' one-gigabyte limit.

Every directory is one pack version and is never changed or removed once
published: a Kingfisher that installed a version keeps working. Each
`manifest.json` names its licence, the exact upstream files and their SHA-256,
and the SHA-256 of every chunk, which Kingfisher checks before using a byte.

| Directory                 | Pack                                             | Source                                                    | Licence      |
| ------------------------- | ------------------------------------------------ | --------------------------------------------------------- | ------------ |
| `reference-elite-v3/`     | Elite OTB Reference, with per-position history   | Lichess broadcast archive, every month 2020-01 … 2026-08  | CC BY-SA 4.0 |
| `reference-rapid-v1/`     | High-Rated Rapid & Classical Online Reference    | Lichess standard rated database, seven months             | CC0 1.0      |

The broadcast archive is © its contributors and Lichess, licensed
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/); these packs are
derived from it (parsed, filtered, replayed through Kingfisher's rules code and
aggregated; no move altered) and are shared under the same licence. The Lichess
standard database is dedicated to the public domain under
[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/).

How they are built: `scripts/build-reference-pack.mjs` in
[`mardakurt/kingfisher`](https://github.com/mardakurt/kingfisher); published
with `scripts/publish-data.mjs`, which only ever adds a new version directory.
