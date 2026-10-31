# Pizza Glee ordering site

Standalone takeout ordering site to replace the TakeEats storefront at pizza-glee.take-eats.jp.

**Status:** Phase 1, data and planning. No app code yet. Stack and payment decisions are pending.

## Folder map
- `data/raw/`: untouched source files (crawl 28 Oct 2026, audit 29 Oct 2026)
- `data/menu.json`: cleaned menu (50 items) with M/L variants and per-store availability
- `data/half_and_half.json`: flavour list and half charges
- `data/issues.md`: every problem found, with product IDs
- `config/site.json`: business settings. Placeholders are in {{double braces}}.
- `content/slides.json`: hero images (alt text still to write)
- `docs/checklist.md`: scope, split into build now, later, and owner decisions

## Rules
- Never commit `.env*` files or real keys. Use Stripe test keys only until launch.
- Do not hard-code hours, phone numbers or legal details in code. Read them from config/site.json.
- Product photos are hosted by TakeEats. Replace them with owner-approved originals before launch.

## Next steps
1. Confirm the stack (proposed: Next.js with TypeScript, Supabase for Postgres, Stripe test mode).
2. Write docs/spec.md: customer flow, pickup rules, order states, kitchen screen.
3. Build in milestones: menu, product page, cart and slots, orders, payment, kitchen screen, legal pages.
