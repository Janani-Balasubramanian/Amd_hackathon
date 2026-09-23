<p align="center"><img src=".github/repository-banner.svg" alt="Retail, Reimagined — Customer experiences and merchant insights" width="100%" /></p>

<p align="center"><a href="https://github.com/Janani-Balasubramanian">GitHub profile</a> · <a href="https://github.com/Janani-Balasubramanian/portfolio">Portfolio</a> · <a href="https://github.com/Janani-Balasubramanian/Amd_hackathon/issues">Issues</a></p>

# Retail, Reimagined

A retail application prototype built for the 1 Day AMD × Google Hackathon. The main application combines a customer storefront with merchant-facing inventory and insights screens.

## Two connected experiences

| Customer | Merchant |
| --- | --- |
| Storefront at `/` | Dashboard at `/seller` |
| Shopping bag at `/cart` | Inventory ledger at `/seller/inventory` |
| Checkout screen at `/checkout` | AI insights at `/seller/insights` |

## Technology

React, Vite, React Router, Tailwind CSS, Firebase, Lucide icons, and the Google Generative AI SDK are declared in the root package manifest.

## Run the main application

From the repository root:

```sh
npm ci
npm run dev
```

Build with `npm run build` and preview with `npm run preview`.

### Configuration

The Firebase integration reads these Vite environment variables from a local `.env` file:

```text
VITE_FIREBASE_API_KEY=
VITE_FIREBASE_AUTH_DOMAIN=
VITE_FIREBASE_PROJECT_ID=
VITE_FIREBASE_STORAGE_BUCKET=
VITE_FIREBASE_MESSAGING_SENDER_ID=
VITE_FIREBASE_APP_ID=
VITE_FIREBASE_MEASUREMENT_ID=
```

The insights module returns a mock response when `VITE_GEMINI_API_KEY` is absent. Its optional direct Gemini call is implemented in [`src/api/gemini.js`](src/api/gemini.js). Vite variables are visible in the browser bundle; use a server-side integration for a production Gemini key. Firebase initializes on import, so configure the Firebase project before expecting the application to start reliably.

## Repository map

- [`src/pages/`](src/pages/) — customer and merchant screens.
- [`src/layouts/`](src/layouts/) — shared layouts.
- [`src/api/`](src/api/) — Firebase and Gemini integrations.
- [`Amd Hackathon/`](Amd%20Hackathon/) — a separate React + TypeScript starter; the commands above target the root application.

## Project scope

This is a hackathon prototype. Checkout UI does not by itself establish production payment processing, and mock insights are demonstration content.

## License

See [LICENSE](LICENSE).
