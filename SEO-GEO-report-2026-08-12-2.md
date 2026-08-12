# SEO / GEO report, 2026-08-12, second pass (9 files edited, 1 created)

**Scope:** Second scheduled full-site SEO/GEO pass of the day. The first pass ran at 10:50
(FAQ tranche 3, nine files). Since then, the second publish run of the day landed Dispatch
Nº 106, "The misprice that sells all night"
(`how-to-catch-pricing-errors-on-shopify-before-orders-flood-in.html`) at 11:23 to 11:26,
with full wiring. This pass ran 12:01 to 12:07 against a settled tree, the first fully
quiet window in five reports; see the concurrency section. The site carries **121 HTML
files**: 62 rendered (59 wired posts + index.html + 2 noindexed rejected drafts) and 59
redirect stubs. Dispatches run Nº 48 through Nº 106, contiguous, no duplicates.

## Baseline audit: clean, fourth defect-free publish in a row

The pass opened by re-deriving the full audit matrix from scratch against the working
tree. Result: zero defects on every surface. Nº 106 launched correctly on all of them:
four-node schema (BlogPosting, BreadcrumbList, FAQPage, HowTo) with the `#priya-singh`
author `@id`, 157-character meta description, sitemap loc, feed item, llms.txt entry,
hub-graph entry in newest-first position behind the pinned essay, index hero ISSUE Nº 106,
ticker advanced to 10 NEW DISPATCHES THIS MONTH matching 10 actual August posts, and its
card first in all 58 sibling grids (59 rendered appearances counting index). Every defect
class that has ever recurred at publish time arrived closed for the fourth consecutive
publish. All standing chrome rulings (title-suffix em dashes, dispatch-header spans,
CSS-comment glyphs, the pinned card's author chip) were honored as exemptions. One
structural note derived fresh this pass and worth recording for future auditors: the
sibling-mesh invariant is directional. Each post's grid carries every post newer than
itself (all 1,711 older-to-newer pairs verified present, newest-first and contiguous at
the top) plus its original birth set of older related cards; grids are not, and never
were, complete cliques.

## Improvement: FAQ tranche 4, eight more posts from 3 to 5 questions

The first 08-12 pass named tranche 4 and this pass executed it exactly as specified: alt
text in bulk, meta descriptions in bulk, product review requests, order editing after
placement, delivered-but-not-received claims, payout reconciliation, shipping-delay
notifications, and free gift with purchase. Each gained two questions, three to five.

The sixteen new Q&As were authored fresh in house style, grounded strictly in each post's
own researched body content, so no unsourced claim enters the citable pool. Answers run
138 to 148 words, direct answer first, quantified where the posts are quantified: FedEx
Picture Proof of Delivery and the USPS GPS readback that comes from the counter rather
than the 800 number, the 7-business-day Missing Mail threshold, the four hidden costs of
the cancel-and-recreate dance, the fifth-of-queue WISMO share that passes half during a
sale, and the demand-letter statistic behind blank alt text. Three more Flow-scoped
questions (can Flow send review requests, why can't Flow handle order changes, can Flow
detect a delivered-but-not-received claim) extend the question class the 08-03 rationale
singled out as GEO-effective, and the how-do-I phrasings (how should I record a payout in
my books, where can I see the fees inside a payout, which pages need meta descriptions)
target queries answer engines actually receive. Zero em or en dashes, zero double quotes,
straight apostrophes throughout.

The 08-12 dedup note (check existing answer text, not just question titles) earned its
keep four times this tranche. Four planned questions were dropped mid-draft because their
substance already lived inside an existing answer: the review response-rate lift (in the
timing answer), the 24-to-48-hour wait guidance (in the refund-or-deny answer), the
Shopify Email marketing-consent limit (in the bulk-email answer), and the
larger-discount-swallows-the-gift mechanics (in the Buy X Get Y answer). Replacement
angles were authored from untouched body material instead.

Mechanics, asserted before write on every file: visible `.faq-item` blocks appended at the
end of each `faq-list` in exact house markup; matching Question nodes appended to each
FAQPage `mainEntity`; JSON text byte-identical to visible text; JSON-LD re-parsed; tag
balance re-verified; visible and JSON counts both equal 5. Formatting split confirmed the
08-10 note: seven of the eight posts carry the older pretty-printed FAQPage JSON and took
pretty-printed insertions; the eighth (Nº 102, delivered-but-not-received, published
08-07) carries the compact single-line style and took a compact insertion. The citable
pool now stands at **241 questions across 59 posts** (32 posts at five, 27 at three).

**Dating convention:** substantive content change, so the eight posts' `dateModified` and
`article:modified_time` advanced to 2026-08-12 and their sitemap `lastmod` bumped to
match. `datePublished`, feed pubDates, and llms.txt bylines untouched. index.html was not
edited by this pass; its 2026-08-12 dates belong to today's publish runs.

## Concurrency: a quiet window, for once

For the first time in five reports, no other writer touched the folder during this pass.
The second publish run finished at 11:26; this pass wrote its nine files between 12:01 and
12:07; the QA sweep did not run in the window. A post-settle mtime scan confirms exactly
nine files changed today after 11:30, all nine of them this pass's. The serialization was
luck of the clock, not policy: three scheduled tasks still share this folder, the 08-12
morning window saw two of them write into the same nine files, and nothing yet enforces
the anchor disjointness that made that merge clean. The stagger recommendation is carried
for a sixth report running.

## Full audit matrix (post-settle, all passing)

| Check | Result |
|---|---|
| JSON-LD parse, all 62 rendered pages (incl. index @graph) | 0 errors |
| FAQ JSON-LD byte-matches visible text, all 59 posts incl. 8 newly deepened | PASS |
| FAQ counts: visible == JSON on every post | 59 / 59 |
| canonical = filename = og:url; og/twitter sets complete | 60 / 60 |
| exactly one h1; lang; viewport; img alt | 60 / 60 |
| duplicate titles / meta descriptions; descriptions <= 160 chars | 0 / 0 / PASS |
| broken internal links / absolute self-domain hrefs in body | 0 |
| author @id resolves to `#priya-singh`; speakable/about/mainEntityOfPage/image | 59 / 59 |
| dateModified vs article:modified_time agreement; future dates | 0 mismatches / 0 |
| dispatch numbering Nº 48..106, header date vs datePublished | contiguous, 0 dupes, 59 / 59 |
| sitemap.xml: 60 locs = 59 wired + index, 0 dupes, 0 ghosts, valid XML | PASS |
| feed.xml: 60 items, unique guids, lastBuildDate = newest, weekdays 61/61 | PASS |
| llms.txt: 59 article entries, all wired | PASS |
| stubs: 59, bijective onto wired posts, noindex + live targets | PASS |
| sibling mesh: Nº 106 first in all 58 grids; all 1,711 older-to-newer pairs | PASS |
| mesh grid order: newer-than-self block newest-first, contiguous; 0 dupes, 0 self-links | PASS |
| index hub graph: 60 blogPost entries, 1 pinned + 59 newest-first; hero Nº 106 | PASS |
| index ticker: 10 NEW DISPATCHES THIS MONTH = 10 actual Aug posts | PASS |
| raw em/en dashes in authored body copy | 0 (standing chrome exempt) |
| tag balance, all 121 files | balanced |
| rejects (2): noindexed, unwired, absent from all surfaces | PASS |

## Checked and deliberately left alone

- **The two rejected drafts**: untouched, delete-on-a-supervised-run recommendation stands.
- **robots.txt**: the 33-agent AI-crawler allowance list still reflects the landscape;
  unchanged since 07-28.
- **Template chrome**: title-suffix em dashes, dispatch-header spans, CSS-comment glyphs,
  and the pinned-card author chip, all standing rulings.
- **feed.xml, llms.txt, index.html**: owned by today's publish runs; correct on
  re-verification, not touched by this pass.

## Recommendations for the owner

1. **Continue the FAQ tranches.** 27 posts remain at three questions; three more passes
   at this pace leaves three, four finishes the program. Suggested tranche 5 by the same
   head-term logic, weighted toward the freshest launches so their citable depth compounds
   early: pricing errors (Nº 106), stuck-in-transit orders (Nº 105), gift card delivery
   (Nº 104), tracking numbers, customer self-serve cancellations, dead stock clearance,
   wholesale customer approval, and syncing inventory between two stores.
2. **Stagger the three schedules** by an hour or more, carried a sixth time. Today's
   afternoon window was quiet only because the publish run happened to finish 35 minutes
   before this pass began; the morning window proved again that same-file overlap is live.
3. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
4. **Commit and deploy.** The uncommitted tree now holds the 08-10 runs, both 08-12
   publishes (Nº 105, Nº 106), the 08-12 QA sweep, the first 08-12 SEO pass (tranche 3),
   and this pass's 9 edits. Nothing on blog.dugong.live reflects any of it until pushed.
   No commit or push was made, per scheduled-run convention.

## Conclusion

Fourth consecutive pass to find a defect-free baseline, on a day that shipped two
dispatches. The FAQ program is now four tranches in: the thirty-two pages most likely to
earn answer-engine citations all field five grounded, quantified questions, 241 Q&As sit
in the citable pool, and the dedup discipline added on 08-12 caught four would-be
near-duplicates before they were written. The mesh invariant is now documented in its
directional form, so future passes can assert it exactly instead of rediscovering it.

**9 files edited: the 8 deepened posts and sitemap.xml. 1 file created: this report.**
