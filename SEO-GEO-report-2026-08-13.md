# SEO / GEO report, 2026-08-13 (9 files edited, 1 created)

**Scope:** Scheduled full-site SEO/GEO pass, the first since the second 08-12 pass. In
between, today's publish run landed Dispatch Nº 107, "The parcel customs sends back"
(`how-to-fix-missing-hs-codes-on-shopify-before-customs-holds-your-orders.html`), at 11:24
to 11:27 with full wiring. This pass ran 11:40 to 11:54 against a settled tree; see the
concurrency section. The site carries **123 HTML files**: 63 rendered (60 wired posts +
index.html + 2 noindexed rejected drafts) and 60 redirect stubs. Dispatches run Nº 48
through Nº 107, contiguous, no duplicates.

## Baseline audit: clean, fifth defect-free publish in a row

The pass opened by re-deriving the full audit matrix from scratch against the working
tree. Result: zero defects on every surface. Nº 107 launched correctly on all of them:
four-node schema with the `#priya-singh` author `@id`, 159-character meta description,
sitemap loc, feed item, llms.txt entry, hub-graph entry in newest-first position behind
the pinned essay, index hero ISSUE Nº 107, ticker at 11 NEW DISPATCHES THIS MONTH matching
11 actual August posts, and its card first in all 59 sibling grids. Every defect class
that has ever recurred at publish time arrived closed for the fifth consecutive publish.
All standing chrome rulings (title-suffix em dashes, dispatch-header spans, CSS-comment
glyphs, the pinned card's author chip) were honored as exemptions.

Two structural notes derived fresh this pass, recorded so future auditors do not
rediscover them as false alarms. First, the ticker's dispatch-header encoding split:
roughly the 28 newest posts write `N&ordm;` and `&mdash;` as entities while older posts
carry the raw glyphs; both render identically, both are chrome, and any dash or numbering
scan has to match both forms. Second, five posts (block-a-customer, duplicate-orders,
merge-duplicate-profiles, shipping-delays, discount-code-abuse) wrap some anchor tags with
a newline immediately after `<a`; the HTML is valid and balanced, and naive `<a `-style
regex counts will miscount there. Neither is a defect; both are now on record.

## Improvement: FAQ tranche 5, eight more posts from 3 to 5 questions

The second 08-12 pass named tranche 5 and this pass executed it exactly as specified:
pricing errors (Nº 106), stuck-in-transit orders (Nº 105), gift card delivery (Nº 104),
tracking numbers, customer self-serve cancellations, dead stock clearance, wholesale
customer approval, and syncing inventory between two stores. Each gained two questions,
three to five.

The sixteen new Q&As were authored fresh in house style, grounded strictly in each post's
own researched body content, so no unsourced claim enters the citable pool. Answers run
139 to 150 words, direct answer first, quantified where the posts are quantified: the
25 to 30 percent annual carrying cost against the $9,300 shorts overbuy, the Descartes
8,000-consumer survey with its 67 and 63 percent delivery-problem shares, the $20 to $30
per lost cancellation race, the eleven fulfillment event statuses including the delayed
status nothing posts, Flow's Get gift card data action querying 100 cards at a time, and
the $249 to $2.49 slipped decimal running through the pricing answers. One more
Flow-scoped question (can Flow send gift card reminders) extends the question class the
08-03 rationale singled out as GEO-effective, and the how-do-I phrasings (how do I audit
my catalog for pricing errors, how do I add tracking numbers in bulk, how do I stop two
stores selling the same last unit) target queries answer engines actually receive. Zero
em or en dashes, zero double quotes, straight apostrophes throughout.

The dedup discipline added on 08-12 earned its keep three times this tranche. Three
planned questions were dropped mid-draft because their substance already lived inside an
existing answer: the carrier claim windows (USPS day 7, UPS 24 hours and 60 days, already
in the stuck-in-transit thresholds answer), the EU Directive 2023/2673 withdrawal
requirement (already closing the cancellations feature answer), and the Bankrate
$27 billion reminder economics (already in the gift card expiry answer). Replacement
angles were authored from untouched body material instead: the delayed-status event-model
answer, the cost-of-a-lost-race answer, and the notification-template diagnostic answer.

Mechanics, asserted before write on every file: visible `.faq-item` blocks appended at
the end of each `faq-list` in exact house markup; matching Question nodes appended to
each FAQPage `mainEntity`; JSON text byte-identical to visible text; JSON-LD re-parsed;
tag balance re-verified; visible and JSON counts both equal 5. The formatting split held
again: four of the eight posts carry the older pretty-printed FAQPage JSON and took
pretty-printed insertions (pricing errors, tracking numbers, dead stock, wholesale
approval), and four carry the compact single-line style and took compact insertions
(stuck-in-transit, gift card, cancellations, two-store sync). The citable pool now stands
at **260 questions across 60 posts** (40 posts at five, 20 at three).

**Dating convention:** substantive content change, so the eight posts' `dateModified` and
`article:modified_time` advanced to 2026-08-13 and their sitemap `lastmod` bumped to
match. `datePublished`, feed pubDates, and llms.txt bylines untouched. index.html was not
edited by this pass; its 2026-08-13 dates belong to today's publish run.

## Concurrency: a second consecutive quiet window

No other writer touched the folder during this pass. The publish run finished at 11:27,
this pass wrote its nine files at 11:53, and the QA sweep had not run today as of 11:54.
A post-settle mtime scan confirms exactly nine files changed after 11:30, all nine of
them this pass's. As on 08-12 afternoon, the serialization was luck of the clock, not
policy: three scheduled tasks still share this folder and nothing enforces write
disjointness. The stagger recommendation is carried for a seventh report running.

## Full audit matrix (post-settle, all passing)

| Check | Result |
|---|---|
| JSON-LD parse, all 63 rendered pages (incl. index @graph) | 0 errors |
| FAQ JSON-LD byte-matches visible text, all 60 posts incl. 8 newly deepened | PASS |
| FAQ counts: visible == JSON on every post | 60 / 60 |
| canonical = filename = og:url; og/twitter sets complete | 61 / 61 |
| exactly one h1; lang; viewport; img alt | 61 / 61 |
| duplicate titles / meta descriptions; descriptions <= 160 chars | 0 / 0 / PASS |
| broken internal links / absolute self-domain hrefs in body | 0 |
| author @id resolves to `#priya-singh`; speakable/about/mainEntityOfPage/image | 60 / 60 |
| dateModified vs article:modified_time agreement; future dates | 0 mismatches / 0 |
| dispatch numbering Nº 48..107 (both glyph and entity forms) | contiguous, 0 dupes |
| sitemap.xml: 61 locs = 60 wired + index, 0 dupes, 0 ghosts, valid XML | PASS |
| feed.xml: 61 items, unique guids, lastBuildDate = newest, weekdays 62/62 | PASS |
| llms.txt: 60 article entries, all wired | PASS |
| stubs: 60, bijective onto wired posts, noindex + live targets | PASS |
| sibling mesh: Nº 107 first in all 59 grids; newer-than-self blocks complete | PASS |
| mesh grid order: newest-first, contiguous; 0 dupes, 0 self-links | PASS |
| index hub graph: 61 blogPost entries, 1 pinned + 60 newest-first; hero Nº 107 | PASS |
| index ticker: 11 NEW DISPATCHES THIS MONTH = 11 actual Aug posts | PASS |
| raw em/en dashes in authored body copy | 0 (standing chrome exempt) |
| tag balance, all 123 files | balanced |
| rejects (2): noindexed, unwired, absent from all surfaces | PASS |

## Checked and deliberately left alone

- **The two rejected drafts**: untouched, delete-on-a-supervised-run recommendation stands.
- **robots.txt**: the 33-agent AI-crawler allowance list still reflects the landscape;
  unchanged since 07-28.
- **Template chrome**: title-suffix em dashes, dispatch-header spans (glyph and entity
  forms), CSS-comment glyphs, and the pinned-card author chip, all standing rulings.
- **feed.xml, llms.txt, index.html**: owned by today's publish run; correct on
  re-verification, not touched by this pass.

## Recommendations for the owner

1. **Continue the FAQ tranches.** 20 posts remain at three questions; two more passes at
   this pace leaves four, three finishes the program. Suggested tranche 6 by the same
   head-term logic, weighted toward the freshest launches so their citable depth
   compounds early: HS codes (Nº 107), restocking returns (Nº 103), releasing held
   orders, splitting orders across multiple suppliers, combining multiple orders from
   the same customer, merging duplicate customer profiles, blocking a customer, and
   pausing ads for out-of-stock products.
2. **Stagger the three schedules** by an hour or more, carried a seventh time. Both
   windows today happened to be quiet; nothing guarantees the next one is.
3. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
4. **Commit and deploy.** The uncommitted tree now holds everything since the owner's
   last commit, including both 08-12 passes, today's Nº 107 publish, and this pass's 9
   edits. Nothing on blog.dugong.live reflects any of it until pushed. No commit or push
   was made, per scheduled-run convention.

## Conclusion

Fifth consecutive pass to find a defect-free baseline, on the same day a new dispatch
shipped. The FAQ program is now five tranches in and two-thirds done: the forty pages
most likely to earn answer-engine citations all field five grounded, quantified
questions, 260 Q&As sit in the citable pool, and the dedup discipline caught three
would-be near-duplicates before they were written. Two audit-tooling pitfalls (the
entity-form dispatch headers and the newline-wrapped anchors) are now documented so the
next pass derives a clean matrix on the first try.

**9 files edited: the 8 deepened posts and sitemap.xml. 1 file created: this report.**
