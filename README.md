# Open Rosary

**One prayer at a time.**

![Open Rosary: a Rosary bead loop with a cross.](docs/readme-banner.svg)

A free Rosary guide for your phone or computer.
Follow the beads on screen, or use the prayer list with your own Rosary.

[**Start praying →**](https://rosary.nickdrezza.com)

## Pray your way

| Mode | How it works |
| --- | --- |
| Digital | Follow your progress bead by bead on screen. |
| Physical | Read the prayer list while you use your own Rosary. |

Choose from 45+ locales, including English, Spanish, Portuguese, French, Latin, and Arabic.
See [language coverage](language_coverage.md) for the full list.
The app calculates liturgical seasons and selected feast dates to choose its theme.
See [themes and dates](themes-and-dates.md) for the calendar rules.

The layout supports phone and desktop screens. Prayer text and translations are kept in
[`prayers-and-verses/`](prayers-and-verses/), where contributors can review each locale.
Mystery images were generated with AI and reviewed for accuracy.

## Run locally

```sh
git clone https://github.com/nickdrezza/open-rosary.git
cd open-rosary
npm ci
npm run dev
```

To check and build the app:

```sh
npm run check
npm test
npm run build
```

## Add a language

1. Create a locale folder in `prayers-and-verses/`, such as `fr-fr/`.
2. Copy the structure of `prayers-and-verses/en-us/constants.ts` into its `constants.ts`.
3. Implement `LocalizationData` with the prayers, mysteries, and interface strings.
4. Register the locale in [`src/lib/i18n/index.ts`](src/lib/i18n/index.ts).
5. Run the app and check the locale route, such as `/fr-fr`.

Use Catholic translation references for the language and region.
Check prayer text and scripture against those sources before submitting a change.

<details>
<summary>Project structure</summary>

Astro builds the static routes. Svelte 5 provides interactive prayer state and language
selection. The project uses TypeScript and Tailwind CSS.

| Path | Purpose |
| --- | --- |
| `src/pages/` | Astro pages and static routes. |
| `src/lib/pages/` | Interactive Svelte pages. |
| `src/lib/components/` | Shared interface components. |
| `src/lib/stores.ts` | Prayer state. |
| `src/lib/liturgical.ts` | Season and feast-date calculations. |
| `src/lib/i18n/` | Locale registration. |
| `prayers-and-verses/` | Prayer text and translations. |

</details>

Made by [nickdrezza](https://nickdrezza.com).

## License

This project is licensed under [GNU AGPLv3 only](LICENSE) (`AGPL-3.0-only`).
See [NOTICE](NOTICE) for copyright information.

You can use, change, and sell copies under the license terms.
If you distribute covered code, provide its source under the same license.
If you change the project and let users access it over a network,
offer those users the source of your version.

Earlier releases keep the license terms that applied to them.
