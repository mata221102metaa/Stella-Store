STELLA STORE 🌾

Files:
- index.html: storefront connected to your Supabase project and Telegram @maliitaa
- SUPABASE_CHECK.sql: optional SQL permission/check query

How to test:
1. Open index.html in a modern browser while online.
2. Public product listing reads from public.products.
3. Click Admin Login and sign in using the email/password already created in Supabase Auth and registered in public.store_admins.
4. Admin can add/edit/delete products.

IMPORTANT:
- Publishable key is designed for browser use; never put a Supabase secret/service_role key here.
- RLS must remain enabled. Admin writes are protected by your is_store_admin() function and policies.
- This is a single-file prototype for easy testing. Before public launch, host over HTTPS and test RLS carefully.
- The current products table created earlier does not include an `icon` or `badge` column. This site uses icon only for display and writes `icon`; run the SQL below once to add it:
  ALTER TABLE public.products ADD COLUMN IF NOT EXISTS icon TEXT DEFAULT '🌾';
  ALTER TABLE public.products ADD COLUMN IF NOT EXISTS badge TEXT;
- Product prices are stored as numbers; currency display formatting can be adjusted to your shop currency.
