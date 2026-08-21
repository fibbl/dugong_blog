# SEO / GEO report, 2026-08-15 (9 files edited, 1 created)

**Scope:** Scheduled full-site SEO/GEO pass, the first since 08-14. Since that pass, today's daily
publish run landed Dispatch Nº 109, "The cancelled order that never leaves your queue"
(`how-to-stop-cancelled-orders-showing-as-unfulfilled-on-shopify.html`), and settled at 11:21,
roughly half an hour before this pass began writing, so the concurrency hazard that cashed out
on 08-14 did not recur; the two writers' windows were cleanly disjoint this time. Post-settle,
the site carries **127 HTML files**: 65 rendered (62 wired posts + index.html + 2 noindexed
rejected drafts) and 62 redirect stubs. Dispatches run Nº 48 through Nº 109, contiguous, no
duplicates.

## Baseline audit: clean, seventh defect-free baseline in a row

The pass opened by re-deriving the full audit matrix from scratch against the tree as of 11:40,
including all of yesterday's Nº 109 wiring. Result: zero defects on every surface across 62
wired posts. One audit-tooling note for future passes, a first-try pitfall this pass hit and
resolved rather than a defect: the FAQ byte-match check must HTML-entity-decode the visible
copy before comparing against the JSON-LD text. Two posts (high-risk orders, WISMO tickets)
carry entity-escaped apostrophes and quotes (&#x27;, &quot;) in their visible FAQ markup, and
a naive byte comparison false-flags four questions that decode to exactly the JSON text. The
byte-identical rule holds at the decoded level; recorded so the next pass derives a clean
matrix on the first try.

## Improvement: FAQ tranche 7, eight more posts from 3 to 5 questions

The 08-14 pass named tranche 7 and this pass executed it exactly as specified: fake accounts
and spam signups (Nº 108), unpaid draft order follow-ups (Nº 101), pickup-to-shipping
conversions (Nº 96), warehouse routing (Nº 93), supplier feed sync (Nº 92), discount codes
applying to sale items (Nº 86), gift messages and gift wrap (Nº 85), and bundle inventory
sync (Nº 83). Each gained two questions, three to five.

The sixteen new Q&As were authored fresh in house style, grounded strictly in each post's own
researched body content, so no unsourced claim enters the citable pool. Answers run 148 to 157
words, direct answer first, quantified where the posts are quantified: the two to six dollars
an order that bad routing costs and the two-hundred-order audit that sizes it, the nineteen
hours of exposure a once-daily feed leaves after the supplier's warehouse runs out, the
Klaviyo race in which the email sync picks up a bot profile before the cleanup deletes it,
and the UK- prefix that reads as one mapping shift rather than 2,800 discontinuations. The
tranche also lands the timeliest fact in the pool: the June 30, 2026 Shopify Scripts sunset
as the answer to why codes suddenly started applying to sale items, phrased as the question
merchants are actually asking this summer. How-do-I phrasings (how do I see which drafts are
still unpaid, how do I keep fake signups out of my email list, how do I stop a broken feed
zeroing my catalog) target queries answer engines receive, and two more platform-capability
questions (can routing choose the cheapest rate, does the Bundles app track per location)
extend the question class the 08-03 rationale singled out as GEO-effective. Zero em or en
dashes, zero double quotes, straight apostrophes throughout.

The dedup discipline earned its keep again: one planned angle was dropped before drafting
because its substance already lived in an existing answer. A how-do-I-charge-for-gift-wrap
angle for Nº 85 would have restated the existing first answer's coverage of Checkout
Extensibility and the bare Plus toggle; a message-validation angle (empty submissions, pasted
tracking URLs, abusive notes held before printing) was authored from untouched body material
instead.

Mechanics, asserted before write on every file: visible `.faq-item` blocks appended at the
end of each `faq-list` in exact house markup, located by div-depth matching rather than
pattern guessing; matching Question nodes appended to each FAQPage `mainEntity`, all eight
posts pretty-printed so all insertions were pretty-printed; JSON text identical to visible
text; JSON-LD re-parsed; tag balance re-verified; visible and JSON counts both equal 5. The
citable pool now stands at **298 questions across 62 posts** (56 posts at five, 6 at three,
including the newly landed Nº 109).

**Dating convention:** substantive content change, so the eight posts' `dateModified` and
`article:modified_time` advanced to 2026-08-15 and their sitemap `lastmod` bumped to match.
`datePublished`, feed pubDates, and llms.txt bylines untouched. index.html, feed.xml, and
llms.txt belong to today's publish run and were not touched by this pass.

## Full audit matrix (post-settle, all passing)

| Check | Result |
|---|---|
| JSON-LD parse, all 65 rendered pages (incl. index @graph) | 0 errors |
| FAQ JSON-LD matches visible text (entity-decoded), all 62 posts incl. 8 newly deepened | PASS |
| FAQ counts: visible == JSON on every post | 62 / 62 |
| canonical = og:url; og/twitter sets complete | 63 / 63 |
| exactly one h1; lang; viewport; img alt | 63 / 63 |
| duplicate titles / meta descriptions; descriptions <= 160 chars | 0 / 0 / PASS |
| broken internal links in rendered pages | 0 |
| author @id resolves to `#priya-singh` on all 62 posts | PASS |
| dateModified vs article:modified_time agreement; future dates | 0 mismatches / 0 |
| dispatch numbering Nº 48..109 | contiguous, 0 dupes |
| sitemap.xml: 63 locs = 62 wired + index, 0 dupes, 0 ghosts, valid XML | PASS |
| sitemap lastmod = 2026-08-15 on exactly index + Nº 109 + the 8 deepened posts | 10 / 10 |
| feed.xml: 63 items, unique guids | PASS |
| llms.txt: 62 article entries, all wired | PASS |
| stubs: 62, bijective onto wired posts, noindex + live targets | PASS |
| sibling mesh: Nº 109 card present in all 61 sibling posts | PASS |
| raw em/en dashes in authored body and FAQ copy | 0 (standing chrome exempt) |
| tag balance, all 127 files | balanced |
| rejects (2): noindexed, unwired, absent from all surfaces | PASS |

## Checked and deliberately left alone

- **The two rejected drafts**: untouched; delete-on-a-supervised-run recommendation stands.
- **robots.txt**: the AI-crawler allowance list unchanged since 07-28, still current.
- **Template chrome**: title-suffix em dashes, dispatch-header spans, ticker-track spans,
  CSS-comment glyphs, and the pinned-card author chip, all standing rulings.
- **index.html, feed.xml, llms.txt**: owned by today's publish run; correct on
  re-verification (63 items/entries each surface, Nº 109 wired once everywhere), not touched.

## Recommendations for the owner

1. **Finish the FAQ program with tranche 8.** Six posts remain at three questions, one more
   pass closes it out: cancelled orders in the queue (Nº 109), limit purchase quantity
   (Nº 81), push sold-out products to the bottom (Nº 77), schedule product publishing
   (Nº 76), segment repeat customers (Nº 65), and minimum order amount (Nº 57). After that,
   every wired post fields five grounded questions and the program retires.
2. **Stagger the three schedules.** No collision today, but only because the publish run
   finished half an hour before this pass started writing. The 08-14 report escalated this
   after same-minute writes to the same eight files; an hour of separation remains the fix.
3. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
4. **Commit and deploy.** The uncommitted tree holds the 08-14 passes, today's Nº 109
   publish, and this pass's 9 edits. Nothing on blog.dugong.live reflects any of it until
   pushed. No commit or push was made, per scheduled-run convention.

## Conclusion

Seventh consecutive defect-free baseline, a seventh FAQ tranche executed to spec with no
concurrency drama this time, and the pool within one pass of complete coverage. The sixteen
new Q&As put the freshest head terms, bot signups, quote follow-ups, and the Scripts-sunset
double-discounting question, on five-answer footing, 298 Q&As sit in the citable pool across
62 posts, and the dedup discipline kept one would-be near-duplicate out of it. One more
tranche and every dispatch on the site fields a full slate.

**9 files edited: the 8 deepened posts and sitemap.xml. 1 file created: this report.**
