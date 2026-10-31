# Scope checklist

## Build now (MVP)
- [ ] Menu: 4 categories, 50 items, availability per store (data/menu.json)
- [ ] Store selection before ordering. Do not show items as sold out before a store is chosen.
- [ ] Product page: M/L size choice, count options (nuggets 5/10), quantity
- [ ] Half & Half: pick exactly 2 flavours, price = sum of the two half charges
- [ ] Pickup: date (6 days ahead), 10-minute slots, per-store hours from config
- [ ] Cart with special-request note (max 250 characters)
- [ ] Card payment via Stripe, test mode
- [ ] Order confirmation with order number
- [ ] Kitchen screen: new-order alert, statuses (new, preparing, ready, picked up, cancelled), print view
- [ ] Sold-out toggle per product per store
- [ ] Legal pages (特定商取引法 and privacy policy), placeholders until the owner confirms
- [ ] Copy fixes from data/issues.md

## Later
- [ ] PayPay, Apple Pay, konbini (check provider support first)
- [ ] English menu
- [ ] Allergen information, size dimensions, serving counts (owner to supply)
- [ ] Google Business Profile order link
- [ ] Coupons; customer list only with a consent basis
- [ ] Analytics (after the privacy policy covers it)
- [ ] Kitchen printer integration (only if the printer model supports it)

## Not planned
- Delivery by the shop (Uber Eats runs on its own tablet)
- Eat-in, EC cart, POS (owner to confirm these are unused in TakeEats)

## Owner decisions (block launch)
- [ ] Real opening hours per store
- [ ] Pizza count (24 on site copy vs 28 items)
- [ ] Seller entity, address and contact details
- [ ] Payment methods and merchant account holder
- [ ] Which shops are in scope (Hiji, Takasaki)
- [ ] Verified phone numbers for Hiji and Takasaki
- [ ] Are two halves of the same flavour allowed?
- [ ] Pickup lead time and order cutoff
- [ ] Printer model
- [ ] Rights to the product photos
- [ ] Export of past TakeEats orders (check TakeEats terms first)
