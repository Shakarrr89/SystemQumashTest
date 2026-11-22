# Fabric Shop Management System

A responsive, single-page fabric shop management interface.

## Run locally

Open `index.html` in a modern browser, or serve this folder with any static web server. For example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Deploy to GitHub Pages

1. Create a GitHub repository.
2. Upload the contents of this ZIP (the `index.html` must be at the repository root).
3. Open **Settings → Pages**.
4. Select **Deploy from a branch**, choose `main` and `/ (root)`, then save.

## UI improvements in this package

- Improved small-screen spacing and touch interaction.
- Mobile bottom navigation now allocates space for all seven existing destinations.
- Responsive modal scrolling and horizontal table scrolling.
- Light/dark theme switch with the selected theme saved in the browser.
- Respects reduced-motion preferences and mobile safe-area insets.

## Important: database connection

The uploaded HTML currently reads and writes through a host-provided relative `actions` endpoint (`records.list/create/replace/delete`). It does **not** currently call Supabase. A GitHub Pages static site does not provide that endpoint, so data operations will not work on GitHub Pages until the data layer is migrated to Supabase (or another backend).

The Supabase string supplied with the request appears to contain the project URL and publishable key concatenated together. It can likely be separated into:

- Project URL: `https://cfwoicjexgexczryekmc.supabase.co`
- Publishable key: starts with `sb_publishable_`

A publishable key is intended for browser use, but it is **not** a security boundary. Customer names, phone numbers, balances, debts, invoices and audit records should be protected with Supabase Auth and Row Level Security (RLS). Do not create unrestricted public read/write policies for this business data.

Before enabling the Supabase migration, create an authenticated owner account and decide whether staff will have separate accounts/roles. The existing app has local PIN prompts, but those are not a substitute for server-side authentication or database access policies.

No database schema or RLS policies have been applied to your Supabase project by this ZIP.
