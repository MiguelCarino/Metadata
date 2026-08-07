# Third-party code bundled here

Everything this project needs is vendored: it loads no script, style, font, map
or module from anywhere but its own origin — no CDN, no network, no account.
That is the point of the tool, and it makes the licences below *this project's*
responsibility rather than a package manager's.

**Every library here has its licence text in this directory.** Naming a licence
is not the same as shipping it: MIT and BSD both require the permission text
itself to travel with a copy, and most minified bundles drop it. Where a bundle
does carry the full text inline, the row says so and no separate file is needed.

Eight libraries, because "read and write the metadata of any file" means one
parser per format family. All run client-side; nothing here uploads anything.

Two are **dual-licensed**, which matters if you ever relicense this project:
`jszip` (MIT **or** GPL-3.0) and `node-forge` (BSD-3-Clause **or** GPL-2.0). Under
AGPL-3.0-or-later you may take either arm of each; record which one you rely on
if the question is ever asked.

## What is here, and under what licence

| File | Package | Licence | Licence text |
| --- | --- | --- | --- |
| `jszip.min.js` | [JSZip](https://stuk.github.io/jszip/) 3.10.1 | MIT **or** GPL-3.0 (dual) | [`LICENSE-jszip.txt`](LICENSE-jszip.txt) — header names both, carries neither |
| `browser-id3-writer.min.js` | [browser-id3-writer](https://github.com/egoroof/browser-id3-writer) 4.4.0 | MIT | [`LICENSE-browser-id3-writer.txt`](LICENSE-browser-id3-writer.txt) |
| `exifr-full.umd.js` | [exifr](https://github.com/MikeKovarik/exifr) | MIT | [`LICENSE-exifr.txt`](LICENSE-exifr.txt) |
| `forge.min.js` | [node-forge](https://github.com/digitalbazaar/forge) | BSD-3-Clause **or** GPL-2.0 (dual) | [`LICENSE-forge.txt`](LICENSE-forge.txt) |
| `jsmediatags.min.js` | [jsmediatags](https://github.com/aadsm/jsmediatags) | BSD-3-Clause | [`LICENSE-jsmediatags.txt`](LICENSE-jsmediatags.txt) |
| `opentype.min.js` | [opentype.js](https://github.com/opentypejs/opentype.js) | MIT | [`LICENSE-opentype.js.txt`](LICENSE-opentype.js.txt) |
| `pdf-lib.min.js` | [pdf-lib](https://pdf-lib.js.org/) | MIT | **Inline** — full MIT text in the bundle; also embeds the Apache-2.0 tslib runtime, credited inline |
| `piexif.js` | [piexifjs](https://github.com/hMatoba/piexifjs) | MIT | **Inline** — full MIT text in the file header |

Four of those texts carry a bracketed note: the copyright holder was transcribed
from the upstream project because the minified bundle names no one. Confirm them
against the exact release you vendored before a distribution someone else relies
on.

## The rule

Adding a file to this directory means adding a row here **in the same commit**.
A record kept from the first vendored file is trivial; one reconstructed two
years later is not.
