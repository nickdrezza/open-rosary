# [Open Rosary](https://rosary.nickdrezza.com)

A beautiful, modern, and open-source web application for praying the Rosary. Designed with a focus on aesthetics, simplicity, and accessibility.

hosted here: https://rosary.nickdrezza.com

My personal website: https://nickdrezza.com

## ✨ Features

-   **Modes**:
    -   **Digital**: Track your progress bead-by-bead on screen.
    -   **Physical**: A simple list view for those who have their own physical Rosary.
-   **Liturgical Intelligence**: Automatically calculates the correct Liturgical Season and major Feast Days (e.g., Ash Wednesday, Easter, All Saints) according to Catholic doctrine.
-   **Multi-Language**: Support for 45+ locales including English, Spanish (ES/MX), Portuguese (PT/BR), French, Italian, German, Polish, Chinese (Simplified/Traditional), Korean, Vietnamese, Filipino, Latin, Hindi, Arabic, Russian, Swahili, and many more.
    -   *Measurements of accuracy are paramount. We strictly use approved Catholic translations for each specific language and region.*
-   **Glassmorphism UI**: A modern, premium aesthetic with blurred glass panels and smooth animations.
-   **PWA**: Installable on mobile devices and works offline.
-   **Responsive**: Optimized for both mobile and desktop experiences.
-   **AI Imagery**: The images were generated with AI (Google Nano Bana Pro (Gemini 3 Pro)). They were carefully reviewed and edited for accuracy.

## Portfolio Notes

-   **Problem:** most digital Rosary tools are either visually dated, single-language, or not built around both physical and digital prayer habits.
-   **Approach:** Astro generates fast static routes while Svelte islands handle the interactive prayer state, language switching, PWA behavior, and liturgical theme logic.
-   **What it shows:** multilingual product work, religious-domain accuracy, offline-first UX, and date-sensitive testing for liturgical seasons and feast days.

## 🛠️ Tech Stack

-   **Framework**: [Astro](https://astro.build/) with hydrated Svelte 5 islands
-   **Styling**: [Tailwind CSS](https://tailwindcss.com/)
-   **Language**: TypeScript
-   **Build Tool**: Astro/Vite

## 📂 Project Structure

-   `src/pages`: Astro pages and static route generation.
-   `src/lib/pages`: Hydrated Svelte page islands used by the Astro routes.
-   `src/lib`: Shared components (`components/`), stores (`stores.ts`), and utilities (`liturgical.ts`, `i18n/`).
-   `prayers-and-verses`: Centralized repository for all prayer text and scripture translations.
    -   Each language has its own folder (e.g., `en-us/`, `es-mx/`) containing a `constants.ts` file which feeds the UI.

## 🚀 Getting Started

1.  **Clone the repository**:

    ```bash
    git clone https://github.com/nickdrezza/open-rosary.git
    cd open-rosary
    ```

2.  **Install dependencies**:

    ```bash
    npm install
    ```

3.  **Run the development server**:

    ```bash
    npm run dev
    ```

4.  **Build for production**:

    ```bash
    npm run build
    ```

5.  **Run Tests**:

    ```bash
    npm test
    ```

    See [themes-and-dates.md](./themes-and-dates.md) for detailed liturgical logic documentation.

## 🤝 Contributing

We welcome contributions! Whether it's a new language, a bug fix, or a feature enhancement.

### Adding a New Language

1.  **Create a Folder**: Inside `prayers-and-verses/`, create a new folder for your locale (e.g., `fr-fr`).
2.  **Create Constants**: Create a `constants.ts` file inside that folder. You can copy the structure from `prayers-and-verses/en-us/constants.ts`.
    -   Ensure you implement the `LocalizationData` interface.
    -   Translate all prayers, mysteries, and UI strings.
3.  **Register Locale**: Open `src/lib/i18n/index.ts`:
    -   Import your new constants file.
    -   Add it to the `locales` object exported at the top.
4.  **Test**: Run the app and manually switch the URL to your new locale (e.g., `/fr-fr`) to verify.

## License

This project is licensed under [GNU AGPLv3 only](LICENSE) (`AGPL-3.0-only`).
See [NOTICE](NOTICE) for copyright information.

You can use, change, and sell copies under the license terms.
If you distribute covered code, provide its source under the same license.
If you change the project and let users access it over a network,
offer those users the source of your version.

Earlier releases keep the license terms that applied to them.
