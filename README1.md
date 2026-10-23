# Puff Tracker

Personal THC and nicotine puff tracker. One static page (`index.html`), synced across devices through Supabase.

- Tap the green side (THC: waxpen or joint) or the blue side (nicotine: vape or cigarette) to log a puff.
- Every tap is stored with its time. The Timeline button lists them by day.
- Daily limits, device equivalents and a day-by-day history.
- Works offline. Taps made without a connection are queued and sync later.

## How it is wired

- Hosting: GitHub Pages, custom domain in `CNAME`.
- Data: Supabase project `PuffTracker`, tables `puff_events` and `puff_settings`.
- Privacy: row-level security means a signed-in user can only read and write their own rows. The Supabase URL and anon key in `index.html` are public by design and give a signed-out visitor no access.
- Sign-in: email and password. Create the user in the Supabase dashboard (Authentication > Users > Add user, with Auto Confirm User on) and turn off new sign-ups.
