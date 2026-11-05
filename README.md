# Puff Tracker

Personal THC, alcohol and nicotine tracker. One static page (`index.html`), synced across devices through Supabase.

- Tap the green side (THC: waxpen or joint) or the blue side (nicotine: vape or cigarette) to log a puff.
- Tap the gold middle (alcohol) to log a drink. Type the ABV at the top (blank = 5%, a typical beer) and pick how much of the container you drank (1, ¾, ½, ¼). The container (tallboy 473 ml, regular can 355 ml, fifth 750 ml, or a custom size) is set in its own section.
- Alcohol is counted in cans: 1 can = a 473 ml tallboy at 5%, about 1.39 Canadian standard drinks (17.05 ml of pure alcohol). Each drink counts as portion × (container ml ÷ 473) × (ABV ÷ 5).
- Every entry is stored with its time. The Timeline button lists them by day.
- Daily limits, device equivalents and a day-by-day history. Alcohol appears in history from 2026-11-05, the day it was added.
- Works offline. Entries made without a connection are queued and sync later.

## How it is wired

- Hosting: GitHub Pages, custom domain in `CNAME`.
- Data: Supabase project `PuffTracker`, tables `puff_events` and `puff_settings`.
- Privacy: row-level security means a signed-in user can only read and write their own rows. The Supabase URL and anon key in `index.html` are public by design and give a signed-out visitor no access.
- Sign-in: email and password. Create the user in the Supabase dashboard (Authentication > Users > Add user, with Auto Confirm User on) and turn off new sign-ups.
