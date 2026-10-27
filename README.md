# Neon Highway

A responsive arcade car-driving game built with HTML Canvas. Drive through neon traffic, fire fictional onboard missiles at rogue enemy vehicles, avoid collisions, and submit scores to a Supabase leaderboard.

## Play locally
Open `index.html` in a modern browser. The game runs in local practice mode until Supabase is configured.

## Controls
- **A / D** or **← / →**: steer
- **Space**: fire missile at the nearest target
- **P**: pause/resume
- Touch devices: on-screen left, fire, and right buttons

## Supabase leaderboard setup
1. Create a Supabase project.
2. Open the SQL Editor and run `supabase/schema.sql`.
3. Copy the project URL and the publishable (or legacy anon) key from the Supabase API settings.
4. Paste them into `config.js` as `supabaseUrl` and `supabaseAnonKey`.
5. Keep service-role/secret keys out of browser code.

The public leaderboard is intentionally readable and allows anonymous score submissions. RLS is enabled and basic input constraints are enforced, but client-submitted scores are not cheat-proof. Add server-side validation/rate limiting before using it for prizes or competitive rankings.

## Deploy to Vercel
Import this GitHub repository into Vercel and deploy with the default static settings. The included `vercel.json` supplies security headers. Set the Supabase values in `config.js` before deployment, or use a generated build step to inject public environment variables.

## Stack
- HTML, CSS, Canvas 2D, vanilla JavaScript
- Supabase Postgres for global leaderboard
- Vercel static hosting
