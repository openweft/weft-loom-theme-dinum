# weft-loom-theme-dinum

`dinum` brand theme for weft-loom compile tooling.

**Signature** : DINUM — DSFR Marianne palette (Marianne Blue #000091 / White / Marianne Red #E1000F).

## Usage (Marp slides)

```yaml
---
marp: true
theme: dinum
---

# Slide title
```

The theme is published as an OCI artifact at
`ghcr.io/openweft/weft-loom-theme-dinum:<tag>` and consumed by
the tool images via a multi-stage `COPY --from=` :

```dockerfile
COPY --from=ghcr.io/openweft/weft-loom-theme-dinumatest /marp/ /opt/marp/themes/
```

## Layout

| Path                  | Contents                                  |
| --------------------- | ----------------------------------------- |
| `marp/dinum.css`   | Marp slide stylesheet                     |
| `pandoc/dinum.tex` | pandoc XeLaTeX template (V0.2)            |
| `latex/dinum.sty`  | raw LaTeX style package (V0.2)            |

## Brand integrity

The CSS commits to the institution's published visual identity
guide. Re-brand drift → open a PR with the citation. Logos +
wordmarks remain the property of their owners and are referenced
only by colour + typography, never bundled as image assets.

## License

BSD-3-Clause (openweft).
