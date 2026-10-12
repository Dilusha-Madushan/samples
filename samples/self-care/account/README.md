# ThunderID Account

ThunderID Account is where users manage their own ThunderID account. Signed-in users can view and edit their profile and
change their password. It is a React (Vite + TypeScript) app built with the self-care components of the
[ThunderID React SDK](https://www.npmjs.com/package/@thunderid/react).

| Account page tab | SDK component      |
| ---------------- | ------------------ |
| Home             | `User`             |
| Personal info    | `UserProfile`      |
| Security         | `ChangeCredential` |

The top nav uses `SignInButton`, `UserDropdown` and `SignedIn`/`SignedOut`.

## Prerequisites

- Node.js 20+ and [pnpm](https://pnpm.io/)
- A running ThunderID server (defaults to `https://localhost:8090`)

New to ThunderID with React? Follow the
[React quickstart guide](https://thunderid.dev/docs/next/getting-started/connect-your-application/react/) to set up a
ThunderID server and connect a React app to it.

## Setup

1. In the ThunderID Console,
   [create a React application](https://thunderid.dev/docs/getting-started/connect-your-application/react/#:~:text=2-,Create%20an%20Application,-Sign%20in%20to)
   using the React quickstart guide. Use `http://localhost:5173` as the app's redirect URL, and copy the client ID it
   gives you.

2. Configure the app:

   ```bash
   cp .env.example .env
   ```

   | Variable                   | Description                                 |
   | -------------------------- | ------------------------------------------- |
   | `VITE_THUNDERID_BASE_URL`  | Base URL of your ThunderID server.          |
   | `VITE_THUNDERID_CLIENT_ID` | Client ID of the application (from step 1). |

3. Install and start:

   ```bash
   pnpm install
   pnpm dev
   ```

4. Open `http://localhost:5173` and sign in. You land on the account page.

## Adding new self-care components

When the SDK ships a new self-care component, bump `@thunderid/react` in `package.json` and add the component to
`src/pages/AccountPage.tsx`:

- A new area (for example, Security): add a tab to `TABS` and `TILES`, and render the component for that tab.

## Docs

- Full SDK reference: [thunderid.dev/docs](https://thunderid.dev/docs)

## License

Apache License 2.0.
