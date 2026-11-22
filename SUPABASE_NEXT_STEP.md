# Supabase connection: next required step

The UI refresh is ready, but the current application data layer uses a platform-specific `actions` endpoint. To make the app work as a GitHub Pages site, that layer must be replaced with Supabase REST calls and authenticated sessions.

Recommended data model: one `app_records` table with `id`, `collection`, `value` (JSONB), `idempotency_key`, and timestamps. Enable RLS and restrict all operations to authenticated users in the shop's owner/staff roles.

The source includes sensitive business data categories (customer contact details, debt balances, sales and audit history). For that reason, this package deliberately does not create an anonymous unrestricted policy or pretend the database is connected.
