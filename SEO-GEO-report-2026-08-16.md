# SEO / GEO report, 2026-08-16 (65 files edited, 1 created)

**Scope:** Scheduled full-site SEO/GEO pass, the first since 08-15. Since that pass, today's daily
publish run landed Dispatch Nº 110, "The custom order that arrives blank"
(`how-to-catch-shopify-orders-with-missing-personalization-before-they-ship-blank.html`), settling
at 11:18, well before this pass began writing, so the writers' windows were again cleanly disjoint.
Post-settle the site carries **129 HTML files**: 66 rendered (63 wired posts + index.html + 2
noindexed rejected drafts) and 63 redirect stubs. Dispatches run Nº 48 through Nº 110, contiguous,
no duplicates.

## Baseline audit: three real defects, all from today's publish run

The pass re-derived the full audit matrix from scratch (with the entity-decoded FAQ comparison the
08-15 report flagged, which produced a clean matrix on the first try as intended). Unlike the seven
prior passes, the baseline was not defect-free: today's publish run wired Nº 110 into index.html,
feed.xml, and sitemap.xml but left three surfaces incomplete, the first publish-run wiring gaps
this pass series has caught.

1. **llms.txt missing Nº 110 entirely.** 62 entries against 63 wired posts. Fixed: a full entry in
   house format was authored from the post's own og:description narrative and inserted newest-first,
   directly below the lead-essay entry. llms.txt now carries 63 article entries, all wired.
2. **Sibling mesh absent for Nº 110 in all 62 sibling posts.** The publish run never prepended the
   new card. Fixed: the Nº 110 card (dispatch title "The custom order that arrives blank", research
   tag, 10 min, AUG 16, P. Singh, dek grounded in the post's opening scene) was prepended at the
   top of every sibling's `related-grid` in exact house markup, located by div-anchor rather than
   pattern guessing. Rejects excluded, matching standing convention. Mesh now passes 62/62.
3. **Nº 110 meta description over limit at 177 chars.** The twitter:description carried the same
   string. Both trimmed to an equivalent 159-char version ("...and the AI playbook that catches
   it."). og:description (long-form narrative) and JSON-LD description untouched, both within
   their own conventions.

Everything else came up clean on the first derivation: JSON-LD parse, FAQ parity, canonicals,
og/twitter sets, h1/lang/viewport/alt, no duplicate titles or descriptions, no broken internal
links, author @id resolution, date agreement, stub bijection, tag balance.

## Improvement: FAQ tranche 8 executed, program complete

The 08-15 pass named tranche 8 as the final tranche and this pass executed it: cancelled orders in
the queue (Nº 109), limit purchase quantity (Nº 81), push sold-out products to the bottom (Nº 57),
schedule product publishing (Nº 77), segment repeat customers (Nº 65), and minimum order amount
(Nº 76). Each gained two questions, three to five. Nº 110 landed at five out of the box, so no
seventh post joined the tranche.

The twelve new Q&As were authored fresh in house style, grounded strictly in each post's own body
content, so no unsourced claim enters the citable pool. Answers run roughly 140 to 155 words,
direct answer first, quantified where the posts are quantified: the forty units taken across
twenty tidy orders when a cap fails, the October 2024 fulfill-then-refund folklore and the locked
cancel button behind it, the December 2023 merchant told to teach her staff to ignore the app's
own notification. How-do-I phrasings (how do I keep customer tags from going stale) and
platform-capability questions (do purchase limits apply to Shop Pay and Apple Pay, can a free
shipping threshold replace a minimum) extend the two question classes prior rationales singled
out as GEO-effective, and two why-questions capture query shapes answer engines see (why do small
orders lose money, why do win-back discounts reach discount hunters). Zero em or en dashes, zero
double quotes, straight apostrophes throughout.

The dedup discipline was applied before drafting: a planned silent-draft angle for Nº 77 was
dropped because the existing first answer already covers the Active-at-the-minute requirement,
and a planned 3PL angle for Nº 109 was dropped because the existing AI-playbook answer already
covers the warehouse-feed leak; both were replaced with angles authored from untouched body
material (the take-down-deadline cost and the fulfill-first ritual respectively).

Mechanics, asserted before write on every file: visible `.faq-item` blocks appended at the end of
each `faq-list` located by div-depth matching; matching Question nodes appended to each FAQPage
`mainEntity`; JSON-LD re-parsed after write; visible and JSON counts both equal 5; FAQ JSON text
byte-identical to visible text at the entity-decoded level. The citable pool now stands at
**315 questions across 63 posts, every post at five**. The FAQ deepening program that began with
tranche 1 is complete and retires.

**Dating convention:** substantive content change, so the six deepened posts' `dateModified` and
`article:modified_time` advanced to 2026-08-16 and their sitemap `lastmod` bumped to match. The
mesh-card insertions are chrome-level per the standing convention and moved no dates.
`datePublished`, feed pubDates, and llms.txt bylines untouched.

## Full audit matrix (post-fix, all passing)

| Check | Result |
|---|---|
| JSON-LD parse, all 66 rendered pages (incl. index @graph) | 0 errors |
| FAQ JSON-LD matches visible text (entity-decoded), all 63 posts incl. 6 newly deepened | PASS |
| FAQ counts: visible == JSON == 5 on every post | 63 / 63 |
| canonical = og:url; og/twitter sets complete | 64 / 64 |
| exactly one h1; lang; viewport; img alt | 64 / 64 |
| duplicate titles / meta descriptions; descriptions <= 160 chars | 0 / 0 / PASS |
| broken internal links in rendered pages | 0 |
| author @id resolves to `#priya-singh` on all 63 posts | PASS |
| dateModified vs article:modified_time agreement; future dates | 0 mismatches / 0 |
| dispatch numbering Nº 48..110 | contiguous, 0 dupes |
| sitemap.xml: 64 locs = 63 wired + index, 0 dupes, 0 ghosts, valid XML | PASS |
| sitemap lastmod = 2026-08-16 on exactly index + Nº 110 + the 6 deepened posts | 8 / 8 |
| feed.xml: 64 items, unique guids | PASS |
| llms.txt: 63 article entries, all wired (Nº 110 added this pass) | PASS |
| stubs: 63, bijective onto wired posts, noindex + live targets | PASS |
| sibling mesh: Nº 110 card present in all 62 sibling posts (added this pass) | PASS |
| raw em/en dashes in authored body and FAQ copy | 0 (standing chrome exempt) |
| tag balance, all 129 files | balanced |
| rejects (2): noindexed, unwired, absent from all surfaces | PASS |

## Checked and deliberately left alone

- **The two rejected drafts**: untouched; delete-on-a-supervised-run recommendation stands.
- **robots.txt**: the AI-crawler allowance list unchanged since 07-28, still current.
- **Template chrome**: title-suffix em dashes, dispatch-header spans, ticker-track spans,
  CSS-comment glyphs, and the pinned-card author chip, all standing rulings.
- **index.html, feed.xml**: owned by today's publish run and correct on verification (64 items
  each, Nº 110 wired once), not touched.
- **Nº 110 og:description and JSON-LD description**: long-form by house convention, left as
  published.

## Recommendations for the owner

1. **Fix the publish workflow's wiring checklist.** Today's run wired three surfaces and missed
   three (llms.txt, sibling mesh, description length). This pass caught and repaired all of them,
   but the publish skill should treat llms.txt entry, mesh prepend, and a 160-char description
   check as part of landing a dispatch, not as cleanup for the next SEO pass.
2. **Stagger the schedules.** No collision today, but the separation was luck of the clock again.
   An hour of enforced separation between the publish run and this pass remains the fix.
3. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
4. **Commit and deploy.** The uncommitted tree now holds several passes of work, today's Nº 110
   publish, and this pass's 65 edits. Nothing on blog.dugong.live reflects any of it until pushed.
   No commit or push was made, per scheduled-run convention.

## Conclusion

The first non-clean baseline in eight passes, all three defects traced to one incomplete publish
run and all three repaired the same morning: Nº 110 is now wired once on every surface, its
description is within limit, and its card sits at the top of every sibling's read-next grid. The
final FAQ tranche landed to spec, which closes the program: 315 grounded Q&As across 63 posts,
every dispatch on the site fielding a full five-question slate. The re-derived matrix passes on
all 19 rows.

**65 files edited: 62 sibling posts (mesh, of which 6 also deepened), Nº 110 (description),
sitemap.xml, and llms.txt. 1 file created: this report.**
