# CLAUDE.md — Pizza Glee ordering site

Standalone takeout ordering site for Pizza Glee (Oita Prefecture, Japan), replacing the TakeEats storefront at pizza-glee.take-eats.jp. Takeout only. No delivery, eat-in, EC or POS.

## Where things are
- `docs/spec.md` — customer flow, pickup rules, order states, kitchen screen (to be written)
- `docs/checklist.md` — build now / later / owner decisions
- `data/menu.json` — cleaned menu, 50 items, generated from `data/raw/`
- `data/half_and_half.json` — flavours and half charges
- `data/issues.md` — every known problem; check it before changing menu data
- `config/site.json` — all business settings (hours, shops, legal, payments)
- `data/raw/` — original source files. Never edit.

## Stack (proposed, not yet final)
- Next.js + TypeScript (App Router). Server routes for orders, slot checks and the Stripe webhook. No separate backend.
- Supabase (Postgres) with Row Level Security. Supabase Auth for staff. Realtime for the kitchen screen.
- Stripe Checkout in TEST mode. Card only. Mark an order paid only after the verified webhook.
- Vitest for pricing and slot logic. Tailwind CSS for styling.
- Kitchen printing via a browser print view (`@media print`). Do not talk to the printer directly.

## Rules
- **Config, not code.** Hours, phone numbers, shop addresses and legal details come only from `config/site.json`. Never hard-code them.
- **Placeholders stay until confirmed.** Any `{{...}}` value or `OWNER_DECISION` must not reach production. Leave it in place and say so.
- **Money.** Whole yen, tax included. L-size prices come from `variants`. A Half & Half price is the sum of two half charges, one per flavour.
- **Pickup.** 10-minute slots, up to 6 days ahead. Weekday gap 14:00–17:00 has no slots. No slots in the past. Slot capacity is checked inside a database transaction.
- **Secrets.** Never commit `.env*` files or real keys. Test keys only until the owner approves going live.
- **Copyright.** Don't copy TakeEats' photos or copy. Use placeholders until the owner supplies originals.
- **Menu data.** Don't hand-edit `data/menu.json`. If a fix is needed, change the source process and log it in `data/issues.md`.
- **Scope.** Don't add delivery, eat-in, EC, POS or customer mailing lists.
- **Working style.** Small changes. Show the plan first, then make the change, run the tests and commit. Ask before adding a dependency.

## Status
- Phase 1 complete: data cleaned, config created, scope written.
- Blocked on owner: payment methods and merchant account holder, seller entity and legal details, pizza count (24 or 28), which shops are in scope, Hiji and Takasaki phone numbers, printer model, pickup lead time and cutoff, rights to photos.
- Hours: owner schedule applied (Mon–Fri 11:00–14:00 and 17:00–20:00, Sat–Sun 11:00–20:00). Closed days and holidays still to confirm.
