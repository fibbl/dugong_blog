# SEO / GEO report, 2026-08-10 (9 files edited, 1 created)

**Scope:** Scheduled full-site SEO/GEO pass, the first since 08-07. In between, the owner
committed the 08-07 runs (`9f62ffc`), and the 08-09 publish run landed Dispatch Nº 103,
"The return that never goes back on the shelf"
(`how-to-automatically-restock-returns-on-shopify.html`), plus its stub and full wiring.
Two scheduled tasks wrote to this folder inside one window again today: the QA sweep
(12:03, feed.xml weekday fix) and this pass (12:02 to 12:05, FAQ tranche 2). The site
carries **115 HTML files**: 59 rendered (56 wired posts + index.html + 2 noindexed rejected
drafts) and 56 redirect stubs.

## Baseline audit: clean, second defect-free publish in a row

The pass opened by re-deriving the full audit matrix from scratch against the working tree.
Result: zero defects on every surface. Nº 103 launched correctly on all of them: four-node
schema with the `#priya-singh` author `@id`, 152-character meta description, sitemap loc,
feed item, llms.txt entry, hub-graph entry in newest-first position, index hero/ticker/card
advance, and its card first in all 55 sibling grids. Every defect class that has ever
recurred at publish time arrived closed for the second consecutive publish. The audit's one
flag is the pinned essay card's `card-author` chip on index (an em dash before A. Rao's
name), which is template chrome carried since May and exempt under the standing
body-copy-only ruling; it is recorded here so future passes do not rediscover it.

## Improvement: FAQ tranche 2, eight more posts from 3 to 5 questions

The 08-07 pass opened the FAQ deepening program on the eight head-term pages and named the
next tranche; this pass executed it exactly as specified: WISMO, returns and exchanges,
address validation, back-in-stock, pre-orders, duplicate orders, discount code abuse, and
reorder points. Each gained two questions, three to five.

The sixteen new Q&As were authored fresh in house style, grounded strictly in each post's
own researched body content, so no unsourced claim enters the citable pool. Answers run 142
to 151 words, quantified where the posts are quantified: the 70 to 90% preventable-WISMO
share and the $880-a-month economics, the 5 to 10% return-to-sender rate, the 200-waiting
on 40-units blast arithmetic, days-of-cover-minus-lead-time reorder math, and the
Tuesday-coupon-site-to-Thursday-extension leak clock. Three more Flow-scoped questions
(can Flow reduce WISMO, send back-in-stock alerts, manage reordering) extend the question
class the 08-03 rationale singled out as GEO-effective, and the how-to phrasings (how do I
offer store credit, which copy of a duplicate order gets canceled, how do I calculate a
reorder point) target queries answer engines actually receive. Zero em or en dashes, zero
double quotes, straight apostrophes throughout.

Mechanics, asserted before write on every file: visible `.faq-item` blocks appended at the
end of each `faq-list` in exact house markup; matching Question nodes appended to each
FAQPage `mainEntity`; JSON text byte-identical to visible text; JSON-LD re-parsed; tag
balance re-verified; visible and JSON counts both equal 5. One formatting note for future
tranches: these eight posts carry the older pretty-printed FAQPage JSON rather than the
compact single-line style of the 08-07 head posts, so insertions matched each file's own
indentation style. The citable pool now stands at **200 questions across 56 posts** (16
posts at five, 40 at three).

**Dating convention:** substantive content change, so the eight posts' `dateModified` and
`article:modified_time` advanced to 2026-08-10 and their sitemap `lastmod` bumped to match.
`datePublished`, feed pubDates, and llms.txt bylines untouched. index.html was not edited
this pass and keeps its 08-09 dates.

## Concurrency note: two writers, one window, disjoint files

Mid-pass, the QA sweep finished at 12:03 having edited exactly one file: feed.xml, fixing
the RFC 822 weekday names on the two May 28 pubDates (`Wed,` to `Thu,`; May 28, 2026 was a
Thursday). This pass wrote eight posts plus sitemap.xml and never touches feed.xml, so the
two write sets were disjoint and no merge was even required. Post-settle verification
confirms both directions anyway: the eight deepened posts hold five byte-matched FAQs each,
and the feed passes the QA sweep's new weekday-agreement check at 58/58. The daily publish
had not run as of 12:05; its convention of inserting mesh cards and hub entries by exact
string means a later Nº 104 will land cleanly on top of these edits. The standing
recommendation to stagger the three schedules is carried for a fourth report running.

## Full audit matrix (post-settle, all passing)

| Check | Result |
|---|---|
| JSON-LD parse, all 59 rendered pages (incl. index @graph) | 0 errors |
| FAQ JSON-LD byte-matches visible text, all 56 posts incl. 8 newly deepened | PASS |
| FAQ counts: visible == JSON on every post | 56 / 56 |
| canonical = filename = og:url; og/twitter sets complete | 57 / 57 |
| exactly one h1; lang; viewport; img alt | 57 / 57 |
| duplicate titles / meta descriptions; descriptions <= 160 chars | 0 / 0 / PASS |
| broken internal links / absolute self-domain hrefs in body | 0 |
| author @id resolves to `#priya-singh`; speakable/about/mainEntityOfPage/image | 56 / 56 |
| dateModified vs article:modified_time agreement; future dates | 0 mismatches / 0 |
| sitemap.xml: 57 locs = 56 wired + index, 0 dupes, 0 ghosts, valid XML | PASS |
| feed.xml: 57 items, unique guids, lastBuildDate = newest, weekdays 58/58 | PASS |
| llms.txt: 56 article entries, all wired | PASS |
| stubs: 56, bijective onto wired posts, noindex + live targets | PASS |
| sibling mesh: Nº 103 card first in all 55 sibling grids, 0 dupes, 0 self-links | PASS |
| index hub graph: 57 BlogPosting entries; hero ISSUE Nº 103; one card-tall | PASS |
| raw em/en dashes in authored body copy | 0 (card-author chip = standing chrome) |
| tag balance, all 115 files | balanced |
| rejects (2): noindexed, unwired, absent from all surfaces | PASS |

## Checked and deliberately left alone

- **The two rejected drafts**: untouched, delete-on-a-supervised-run recommendation stands.
- **robots.txt**: the 33-agent AI-crawler allowance list still reflects the landscape;
  unchanged since 07-28.
- **Template chrome**: title-suffix em dashes, dispatch-header spans, CSS-comment glyphs,
  and the pinned-card author chip, all standing rulings.
- **index.html**: correct on every surface after the 08-09 publish; no edit, no lastmod bump.

## Recommendations for the owner

1. **Continue the FAQ tranches.** 40 posts remain at three questions; five more passes at
   this pace finishes the program. Suggested tranche 3 by the same head-term logic:
   invoices, unpaid-order cancellation, order tagging, sold-out variants, bulk price
   edits, scheduled sales, AI product descriptions, tiered volume discounts.
2. **Stagger the three schedules** by an hour or more, carried a fourth time. Today's
   overlap was harmless only because the write sets happened to be disjoint.
3. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
4. **Commit and deploy.** The uncommitted tree now holds the 08-09 publish run, today's QA
   feed fix, and this pass's 9 edits. Nothing on blog.dugong.live reflects any of it until
   pushed. No commit or push was made, per scheduled-run convention.

## Conclusion

Second consecutive pass to find a defect-free baseline, and the FAQ program is now two
tranches in: the sixteen pages most likely to earn answer-engine citations all field five
grounded, quantified questions, with 200 Q&As in the citable pool. The concurrency pattern
recurred and again cost nothing, this time because the writers touched disjoint files, but
the luck-spending observation from 08-07 stands.

**9 files edited: the 8 deepened posts and sitemap.xml. 1 file created: this report.**
