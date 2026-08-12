# SEO / GEO report, 2026-08-12 (9 files edited, 1 created)

**Scope:** Scheduled full-site SEO/GEO pass, the first since 08-10. In between, the 08-10
publish run landed Dispatch Nº 104, "The gift card that never arrives"
(`how-to-automate-gift-card-delivery-and-reminders-on-shopify.html`), with full wiring.
Mid-way through this pass, the daily publish run landed Dispatch Nº 105, "The package that
stops moving" (`how-to-catch-shopify-orders-stuck-in-transit.html`), writing to the same
folder in the same window; see the concurrency section, which this time is not a footnote.
Post-settle, the site carries **119 HTML files**: 61 rendered (58 wired posts + index.html +
2 noindexed rejected drafts) and 58 redirect stubs. Dispatches run Nº 48 through Nº 105,
contiguous, no duplicates.

## Baseline audit: clean, third defect-free publish in a row

The pass opened by re-deriving the full audit matrix from scratch against the working tree.
Result: zero defects on every surface. Nº 104 launched correctly on all of them: four-node
schema with the `#priya-singh` author `@id`, 153-character meta description, sitemap loc,
feed item, llms.txt entry, hub-graph entry in newest-first position, index hero/ticker/card
advance, and its card first in all 56 sibling grids. Every defect class that has ever
recurred at publish time arrived closed for the third consecutive publish. The standing
chrome rulings (title-suffix em dashes, ticker spans, CSS-comment glyphs, the pinned card's
author chip) were honored as exemptions, not rediscovered as defects.

## Improvement: FAQ tranche 3, eight more posts from 3 to 5 questions

The 08-10 pass named tranche 3 and this pass executed it exactly as specified: invoices,
unpaid-order cancellation, order tagging, sold-out variants, bulk price edits, scheduled
sales, AI product descriptions, and tiered volume discounts. Each gained two questions,
three to five.

The sixteen new Q&As were authored fresh in house style, grounded strictly in each post's
own researched body content, so no unsourced claim enters the citable pool. Answers run 138
to 157 words, direct answer first, quantified where the posts are quantified: the 25-slot
hard cap on active automatic discounts, the vip / VIP / Vip case-sensitivity split that
silently breaks segments, the B2B company-profile wall around Shopify's only native
quantity tiers, and the order-tags-is-invalid failure mode. One more Flow-scoped question
(can Shopify Flow cancel an unpaid order) extends the question class the 08-03 rationale
singled out as GEO-effective, and the how-do-I phrasings (apply a new tagging rule to past
orders, end a sale and put prices back automatically, bulk edit prices with a CSV) target
queries answer engines actually receive. Zero em or en dashes, zero double quotes, straight
apostrophes throughout.

One planning note recorded for future tranches: the obvious invoices question (does Shopify
email its VAT invoices) turned out to be answered inside the post's existing first FAQ, so
the two new invoice questions took the genuinely uncovered angles instead, the edit/refund
lifecycle and receipt-versus-tax-invoice classification. Dedup needs to check existing
answer text, not just existing question titles.

Mechanics, asserted before write on every file: visible `.faq-item` blocks appended at the
end of each `faq-list` in exact house markup; matching Question nodes appended to each
FAQPage `mainEntity`; JSON text byte-identical to visible text; JSON-LD re-parsed; tag
balance re-verified; visible and JSON counts both equal 5. All eight posts carry the older
pretty-printed FAQPage JSON style, as the 08-10 formatting note predicted, and insertions
matched each file's own indentation. The citable pool now stands at **222 questions across
58 posts** (24 posts at five, 34 at three).

**Dating convention:** substantive content change, so the eight posts' `dateModified` and
`article:modified_time` advanced to 2026-08-12 and their sitemap `lastmod` bumped to match.
`datePublished`, feed pubDates, and llms.txt bylines untouched. index.html was not edited
by this pass; its 2026-08-12 dates belong to today's publish run.

## Concurrency: two writers, one window, and this time the same files

This pass wrote its nine files at 10:41. The daily publish run then landed Nº 105 between
10:43 and 10:47, and its wiring wrote into **the same files**: the mesh insert put Nº 105's
card at the top of the related grid in all 57 wired posts, including the eight deepened
minutes earlier, and sitemap.xml took both write sets (this pass's eight lastmod bumps, the
publish's new URL and index bump). Unlike 08-07 and 08-10, the write sets were not
disjoint. The merge was clean anyway, because both writers anchor edits to exact strings at
different points in each file: FAQ blocks append at the faq-list end, mesh cards insert at
the grid top. Post-settle verification re-derived the whole matrix from scratch and
confirmed both directions: the eight posts hold five byte-matched FAQs, 2026-08-12 dates,
and Nº 105's card first in their grids; Nº 105 itself passes every launch check. The
stagger recommendation is carried for a fifth report running, now with the observation
upgraded: today's safety came from anchor disjointness inside shared files, not from file
disjointness, and that is a thinner margin than luck has previously spent.

## Full audit matrix (post-settle, all passing)

| Check | Result |
|---|---|
| JSON-LD parse, all 61 rendered pages (incl. index @graph) | 0 errors |
| FAQ JSON-LD byte-matches visible text, all 58 posts incl. 8 newly deepened | PASS |
| FAQ counts: visible == JSON on every post | 58 / 58 |
| canonical = filename = og:url; og/twitter sets complete | 59 / 59 |
| exactly one h1; lang; viewport; img alt | 59 / 59 |
| duplicate titles / meta descriptions; descriptions <= 160 chars | 0 / 0 / PASS |
| broken internal links / absolute self-domain hrefs in body | 0 |
| author @id resolves to `#priya-singh`; speakable/about/mainEntityOfPage/image | 58 / 58 |
| dateModified vs article:modified_time agreement; future dates | 0 mismatches / 0 |
| dispatch numbering Nº 48..105, ticker date vs datePublished | contiguous, 0 dupes, 58 / 58 |
| sitemap.xml: 59 locs = 58 wired + index, 0 dupes, 0 ghosts, valid XML | PASS |
| feed.xml: 59 items, unique guids, lastBuildDate = newest, weekdays 60/60 | PASS |
| llms.txt: 58 article entries, all wired | PASS |
| stubs: 58, bijective onto wired posts, noindex + live targets | PASS |
| sibling mesh: Nº 105 first in all 57 grids; all 1,653 older-to-newer pairs | PASS |
| mesh grid order: newer-than-self block newest-first, contiguous; 0 dupes, 0 self-links | PASS |
| index hub graph: 59 blogPost entries, newest-first; hero Nº 105; one card-tall | PASS |
| index ticker: 9 NEW DISPATCHES THIS MONTH = 9 actual Aug posts | PASS |
| raw em/en dashes in authored body copy | 0 (standing chrome exempt) |
| tag balance, all 119 files | balanced |
| rejects (2): noindexed, unwired, absent from all surfaces | PASS |

## Checked and deliberately left alone

- **The two rejected drafts**: untouched, delete-on-a-supervised-run recommendation stands.
- **robots.txt**: the 33-agent AI-crawler allowance list still reflects the landscape;
  unchanged since 07-28.
- **Template chrome**: title-suffix em dashes, dispatch-header spans, CSS-comment glyphs,
  and the pinned-card author chip, all standing rulings.
- **feed.xml and llms.txt**: owned by today's publish run this window; correct on
  re-verification, not touched by this pass.

## Recommendations for the owner

1. **Continue the FAQ tranches.** 34 posts remain at three questions; four more passes at
   this pace finishes all but two, five finishes the program. Suggested tranche 4 by the
   same head-term logic: alt text in bulk, meta descriptions in bulk, product review
   requests, order editing after placement, delivered-but-not-received claims, payout
   reconciliation, shipping-delay notifications, free gift with purchase.
2. **Stagger the three schedules** by an hour or more, carried a fifth time and upgraded:
   today the SEO pass and the publish run wrote into the same nine files inside one window
   and merged only because their edit anchors happen not to collide. That invariant is
   implicit and nothing enforces it.
3. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
4. **Commit and deploy.** The uncommitted tree now holds the 08-10 runs, the 08-12 publish
   (Nº 105), and this pass's 9 edits. Nothing on blog.dugong.live reflects any of it until
   pushed. No commit or push was made, per scheduled-run convention.

## Conclusion

Third consecutive pass to find a defect-free baseline, and the FAQ program is now three
tranches in: the twenty-four pages most likely to earn answer-engine citations all field
five grounded, quantified questions, with 222 Q&As in the citable pool across every post on
the site. The concurrency pattern recurred in its sharpest form yet, same files rather than
same window, and cost nothing only because the two writers' string anchors are disjoint by
construction. The stagger recommendation should be read accordingly.

**9 files edited: the 8 deepened posts and sitemap.xml. 1 file created: this report.**
