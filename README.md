# weft-loom-theme-dinum

`dinum` brand theme for weft-loom compile tooling. Aligned with the
**Système de Design de l'État (DSFR)** — the official French
government design system maintained by DINUM.

**Signature** : Marianne blue `#000091` + Marianne red `#E1000F` —
the two locked colours of the République française signature.

## Source

Colour tokens sourced from the open-source `@gouvfr/dsfr` npm
package (`dist/core/core.css`, 2026-06 audit) — these are the
authoritative DSFR variables :

| DSFR token                       | Hex       | Role                          |
| -------------------------------- | --------- | ----------------------------- |
| `--blue-france-sun-113-625`      | `#000091` | Marianne blue (signature)     |
| `--red-marianne-main-472`        | `#E1000F` | Marianne red (signature)      |
| `--blue-france-main-525`         | `#6A6AF4` | Action blue (links, buttons)  |
| `--background-default-grey`      | `#F6F6F6` | Paper surface                 |
| `--text-default-grey`            | `#161616` | Body text                     |

## Typography

The DSFR prescribes two fonts :

- **Marianne** — official République française wordmark face, by
  Tipotype. Free for public and private use under the
  Marianne licence. https://www.numerique.gouv.fr/publications/marianne/
- **Spectral** — editorial serif, Google Fonts.

The theme uses Marianne for the body + headings and Spectral for
blockquotes. If Marianne isn't installed, the theme falls back to
system Arial.

## Wordmark + signature

The DSFR mandates the "RÉPUBLIQUE FRANÇAISE" lockup in the top-left
of official documents — this theme renders it in Marianne blue at
the upper-left of every slide. The footer rule shows the
blue / white / red tricolore.

## Usage (Marp slides)

```yaml
---
marp: true
theme: dinum
---

# Slide title
```

For lead / title slides :

```markdown
<!-- _class: lead -->

# Title here
## Subtitle here
```

## Distribution

Published as an OCI artifact at
`ghcr.io/openweft/weft-loom-theme-dinum:<tag>`. Tool images consume
it via multi-stage `COPY --from=` :

```dockerfile
COPY --from=ghcr.io/openweft/weft-loom-theme-dinum:latest /marp/dinum.css /opt/marp/themes/dinum.css
```

## License

BSD-3-Clause (openweft). The DSFR + Marianne signature remain
property of the République française ; this theme references them
only by colour and typography token. Use of the "RÉPUBLIQUE
FRANÇAISE" lockup outside official government communication is
subject to the DSFR conditions of use.

## Cover slide / logo

The theme renders a brand-typography wordmark on `section.lead`
slides ; no institutional logo file is bundled (trademarks remain
the institution's property and aren't redistributable under
BSD-3-Clause).

If you have the right to use the official logotype in your deck,
supply your own image via the `--m-logo` CSS variable :

```markdown
<!-- _class: lead -->
<!-- _style: "--m-logo: url(/path/to/your/logo.svg)" -->

# Title here
## Subtitle here
```

Official logo source : https://www.systeme-de-design.gouv.fr/utilisation-et-organisation/identite-de-letat/ (DSFR Marianne lockup).
