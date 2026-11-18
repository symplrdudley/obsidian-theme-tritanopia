# Tritanopia

An [Obsidian](https://obsidian.md/) theme designed for tritanopia — a blue-cone color deficiency where blue and yellow/amber are the primary confusion pair.

Supports both **dark mode** and **light mode**.

---

## Color palette

Tritanopia means blue and green can appear similar, and yellow and red can appear similar. Blue, purple, and yellow are avoided as primary distinguishing colors. The maximally safe pair for tritanopes is **red vs teal** — they differ in the R and G channels, which tritanopes retain — so this pair carries all the most important signal (errors vs actions, danger vs info).

| Color | Hex | Role | How it appears to tritanopes |
|-------|-----|------|------------------------------|
| Teal | `#2EC4B6` | Accent, links, info | Saturated green |
| Red | `#EF233C` | Danger, errors | Unchanged |
| Orange | `#FF9F1C` | Warnings, keywords | Pinkish-warm, light |
| Lime | `#A8D82D` | Success, strings, tips | Olive-yellow-green |

Blue, purple, and yellow are never used as primary discriminating colors. Blue/green pairs and yellow/red pairs are never used as discriminators.

## Callout color mapping

| Type | Color | Callouts |
|------|-------|----------|
| Teal | Info/neutral | `note`, `info`, `todo` |
| Lime | Positive | `tip`, `hint`, `success`, `check`, `done`, `abstract`, `summary`, `tldr` |
| Orange | Caution | `warning`, `caution`, `attention`, `question`, `help`, `faq`, `important` |
| Red | Danger | `danger`, `error`, `bug`, `failure`, `fail`, `missing` |

## Syntax highlighting

| Token | Color |
|-------|-------|
| Functions | Teal |
| Strings | Lime |
| Keywords | Orange |
| Tags, important | Red |
| Properties | Lighter teal |
| Comments | Muted gray |

## Header hierarchy

Headers cycle through the tritanopia-safe palette to give visual depth without relying on blue or purple:

`H1 (teal)` → `H2 (lime)` → `H3 (orange)` → `H4 (lighter teal)` → `H5 (lighter lime)` → `H6 (lighter orange)`

---

## Installing for development

1. Clone this repository somewhere on your machine.
2. Copy or symlink the theme folder into your vault's themes directory:

   ```
   <vault>/.obsidian/themes/Tritanopia/
   ```

   The folder must contain both `manifest.json` and `theme.css`.

3. In Obsidian, open **Settings → Appearance → Themes** and select **Tritanopia**.

---

## Contributing / linting

This repository uses [`stylelint-config-obsidianmd`](https://github.com/obsidianmd/stylelint-config) to enforce the same CSS rules used during Obsidian community theme review. There are no unit tests for a CSS theme beyond linting.

Install dependencies and run the linter:

```bash
npm install
npm run lint
```

The lint workflow also runs automatically on every pull request via `.github/workflows/lint.yml`.

> **Note:** Obsidian themes do not use test frameworks (Jest, pytest, etc.) — CSS linting is the only automated check that applies. See the [Theme guidelines](https://docs.obsidian.md/Themes/App+themes/Theme+guidelines) for the rules enforced: use CSS variables, avoid `!important`, and keep all assets local.

---

## Releasing a version

1. Update `manifest.json` with the new version.
2. Add an entry to `versions.json` mapping the new version to the minimum Obsidian version it requires.
3. Commit and push, then push a tag matching the version string (e.g. `0.2.0`). The GitHub Actions release workflow creates a draft release automatically.

---

## References

All design decisions in this theme follow these official and community resources:

- **[Build a theme](https://docs.obsidian.md/Themes/App+themes/Build+a+theme)** — official step-by-step walkthrough for creating an Obsidian theme from scratch
- **[Theme guidelines](https://docs.obsidian.md/Themes/App+themes/Theme+guidelines)** — best practices enforced during community theme review: CSS variables, no `!important`, local assets
- **[About styling](https://docs.obsidian.md/Reference/CSS+variables/About+styling)** — how Obsidian's CSS variable system is structured and how themes layer on top of it
- **[CSS variables reference](https://docs.obsidian.md/Reference/CSS+variables/CSS+variables)** — full index of every CSS custom property Obsidian exposes for theming
- **[Embed fonts and images](https://docs.obsidian.md/Themes/App+themes/Embed+fonts+and+images+in+your+theme)** — how to bundle web fonts and images into a theme using base64 data URIs (this theme uses system fonts only, keeping the bundle small)
- **[obsidian-sample-theme](https://github.com/obsidianmd/obsidian-sample-theme)** — the official starter template this theme was forked from
- **[Getting started with Obsidian themes](https://obsidian.rocks/getting-started-with-obsidian-themes/)** — community guide covering theme installation, the Style Settings plugin ecosystem, and maintainability considerations
