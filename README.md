# Metadata

A client-side, offline-first metadata tool for **almost any file** — extract, edit and create metadata without anything ever leaving your device. Part of the [Carino Systems](https://carino.systems) toolset; a general-purpose sibling to the [DICOM Tag Editor](https://dicom.carino.systems).

**Live:** https://metadata.carino.systems

## What it does

- **Detects the file type by magic bytes** (not just the extension) and shows a type-aware advisory — e.g. a `.dcm` file points you to the DICOM editor, a `.lnk` is explained as a Windows shortcut, executables and private keys carry a caution.
- **Universal extraction** for every file: name, size, MIME guess, last-modified, **SHA-256** hash, and the byte signature.
- **Export** all extracted metadata as **JSON** or **CSV**.

### Read + edit + write-back
| Format | Read | Edit / Create | Download rewritten file |
|--------|------|---------------|--------------------------|
| **PDF** (info dict) | ✅ | ✅ | ✅ |
| **JPEG** (EXIF/IPTC/XMP, GPS) | ✅ | ✅ (+ Strip GPS) | ✅ |
| **MP3** (ID3 tags) | ✅ | ✅ | ✅ |

### Read / extract only
Images (PNG, TIFF, WebP, HEIC, GIF, BMP) · Video/containers (MP4, MOV, MKV/WebM, AVI) · Archives & Office (ZIP, DOCX, XLSX, PPTX, EPUB, JAR, APK — incl. core properties) · Fonts (TTF, OTF, WOFF/WOFF2) · Certificates (X.509 PEM/DER) · Keys/keystores (PEM, PKCS#12 — described, secrets never extracted) · Executables (PE/EXE, ELF, Mach-O, WASM, Java class) · SQLite · text/source.

## Privacy

Everything runs in your browser. Files are **never uploaded**. Cryptographic secrets (private keys) are deliberately **not** parsed or displayed — only non-secret properties.

## Tech

Single self-contained `index.html`. Parsing libraries loaded from CDN and every call is guarded, so core detection + generic extraction still work offline. Uses [exifr](https://github.com/MikeKovarik/exifr) + [piexifjs](https://github.com/hMatoba/piexifjs) (images), [pdf-lib](https://pdf-lib.js.org/) (PDF), [jsmediatags](https://github.com/aadsm/jsmediatags) + [browser-id3-writer](https://github.com/egoroof/browser-id3-writer) (MP3), [JSZip](https://stuk.github.io/jszip/) (archives/Office), [opentype.js](https://opentype.js.org/) (fonts) and [node-forge](https://github.com/digitalbazaar/forge) (certificates). Shares the Carino navbar/clock convention and the [Carino Branding](https://branding.carino.systems) design system.

## License

Licensed under the **GNU Affero General Public License v3.0 or later** (AGPL-3.0-or-later) — see [LICENSE](LICENSE). Copyright © 2026 Miguel Carino.
