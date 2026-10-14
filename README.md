# Nexora Wallet — Setup

1. Supabase → SQL Editor → paste & run `supabase/migration.sql`
2. Supabase → Authentication → Sign In / Providers → Email → turn OFF "Confirm email"
3. Supabase → Project Settings → API → copy Project URL + anon public key
4. `cp .env.example .env.local` and paste the URL and anon key (NEVER use the service_role key)
5. `npm install` then `npm run dev` (open http://localhost:3000)
6. Register once, then run in SQL Editor:
   `update public.profiles set role='admin' where email='YOUR_EMAIL';`
7. Login → Admin → Payment methods → enter bKash / Nagad / Binance details → tick Enabled → Save
8. Deploy: push to GitHub → import in Vercel → add the same 2 env vars.
   Then in Supabase → Auth → URL Configuration, add your Vercel URL (needed for password reset).

Status: all features are functional. Payments are manual (no gateway). Do not take real money before legal/provider approval.
