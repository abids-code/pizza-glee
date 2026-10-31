# Issues log

Generated from data/raw by the build script. Severity: error = must fix before build, warn = needs owner review, info = handled, FYI.

## Automated checks (products)
| Severity | Product ID | Finding |
|---|---|---|
| warn | 104155 | shop availability for Half & Half not confirmed per shop |
| warn | 104156 | shop availability for Half & Half not confirmed per shop |
| warn | 34982 | description calls this pizza ハワイアン (Hawaiian) but it is smoked salmon and cream cheese; owner to correct |
| warn | 34983 | L half charge 1475 is not half of L price 2650 (expected 1325); check live page |
| info | 104155 | M Half & Half description taken from audit text (source reads ビザ, corrected to ピザ); confirm |
| info | 34991 | typo ビザ corrected to ピザ in description |
| info | 35011 | デリシャスフォー excluded from Half & Half (already a 4-flavour pizza, per audit) |
| info | 35035 | placeholder description removed (it only repeated the product name) |
| info | 35037 | placeholder description removed (it only repeated the product name) |
| info | 35038 | placeholder description removed (it only repeated the product name) |
| info | 42131 | placeholder description removed (it only repeated the product name) |
| info | 42134 | placeholder description removed (it only repeated the product name) |

## Conflicts to resolve with the owner
1. **Opening hours: three sources disagree.** Shop pages say 11:30-20:00 every day (all shops). The legal page (/law) says 16:00-20:00. The owner brief says Mon-Fri 11-14 and 17-20, Sat-Sun 11-20. config/site.json uses placeholders until the owner confirms.
2. **Pizza count.** Site copy says 24 pizzas (meta description). The menu has 28 pizza items. Owner to confirm which are live.
3. **Shop scope.** Beppu is confirmed. Hiji and Takasaki phone numbers come from external listings, not the site. Verify before publishing. Whether these two shops are in scope is an owner decision.
4. **Seller entity.** /law names 株式会社Lihaat Foods. TakeEats' privacy policy names 株式会社ランプ. The owner decides the seller entity. Placeholder used.
5. **Personal contact on /law.** The sales-manager contact on /law looks personal. Replace with business contact details before launch.
6. **Privacy policy.** /privacy is TakeEats' (LAMP) policy. It must be replaced by the shop's own policy, covering its payment provider and hosting.

## Copy and content fixes
- 34982: "ハワイアン" in the description does not match the pizza. Owner to correct.
- 34991: ビザ typo, corrected in menu.json.
- Half & Half M description: source reads ビザ, corrected.
- Drinks (35035, 35037, 35038) and 42134: placeholder descriptions removed.
- 42131: no description on the site.
- Half & Half flavour name "ガーリックミートピザ" in the audit list does not match the product name "ガーリックミート". Use the product name.
- No allergen information, ingredient lists or cm sizes anywhere on the site. Owner to supply.

## Source notes
- products.json and products.csv both have 50 items. Automated checks compare them field by field (see table above).
- Audit s.11 overrides earlier sections. The 8 L prices marked [verified live] in products.json come from there.
- Images are hosted on TakeEats' CloudFront CDN. Do not hotlink them in the new site. Get originals from the owner, and confirm the rights.
