# DietManager Supabase setup

The website has been wired to Supabase email/password authentication and per-user cloud storage. It will deliberately keep the app hidden until valid Supabase configuration is provided.

## Setup

1. Create a project at https://supabase.com/.
2. In Supabase, open **SQL Editor**, create a query, paste all of `supabase-schema.sql`, and run it. This creates the `user_data` table with row-level security so a signed-in user can access only their own row.
3. In **Project Settings → API** (or API Keys), copy the **Project URL** and the **publishable key** (or legacy `anon` key).
4. Edit `supabase-config.js` in this repository and replace:
   - `YOUR_SUPABASE_PROJECT_URL` with the Project URL
   - `YOUR_SUPABASE_PUBLISHABLE_OR_ANON_KEY` with the publishable/anon key
5. In Supabase **Authentication → URL Configuration**, set the Site URL to your GitHub Pages URL, for example `https://abhijitbot277.github.io/DietManager/`. Add that exact URL to the allowed redirect URLs if required.
6. In **Authentication → Providers → Email**, choose whether email confirmation is required. If enabled, users must confirm their email before logging in.
7. Commit the config change and wait for GitHub Pages to deploy. Test creating a new account, signing in, logging food/workouts, logging out, and signing back in.

## Security and launch notes

- The Supabase publishable/anon key is designed to be public in browser apps. Never put a Supabase `service_role` or secret key in frontend code or GitHub.
- Passwords are managed by Supabase Auth, not stored in DietManager's database.
- Row-level security on `user_data` is essential; do not disable it.
- This initial cloud sync stores each user's app state as one JSON document. It is a useful MVP, but not a substitute for a full production review, backups, privacy policy, terms, deletion/export flows, rate limiting, and monitoring.
- Do not advertise this as production-ready or take payments until security, privacy, data retention, and subscription handling have been reviewed and tested.
- Existing browser-local records are not automatically uploaded unless a legacy `dietmanager-v1` record exists in the same browser at the time that account first signs in.
