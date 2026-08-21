# SEO / GEO report, 2026-08-14 (9 files edited, 1 created)

**Scope:** Scheduled full-site SEO/GEO pass, the first since 08-13. Since that pass, the owner
committed the whole tree (`0bb4416`, today 18:49), today's QA sweep ran clean at 18:55 (zero
defects, zero files changed), and the daily publish run landed Dispatch Nº 108, "The customer
list the bots built" (`how-to-stop-fake-customer-accounts-and-spam-signups-on-shopify.html`),
concurrently with this pass; see the concurrency section, which this time is not a footnote.
Post-settle, the site carries **125 HTML files**: 64 rendered (61 wired posts + index.html +
2 noindexed rejected drafts) and 61 redirect stubs. Dispatches run Nº 48 through Nº 108,
contiguous, no duplicates.

## Baseline audit: clean, sixth defect-free baseline in a row

The pass opened by re-deriving the full audit matrix from scratch against the committed tree
as of 18:51. Result: zero defects on every surface across 60 wired posts. Two audit-tooling
notes for future passes, both first-try pitfalls this pass hit and resolved rather than
defects. First, the sibling-mesh order invariant is a two-part rule: each grid opens with a
contiguous newest-first block of every post newer than the host, followed by a curated tail of
older posts whose order is free. A naive global newest-first check false-flags all curated
tails. Second, the standing chrome exemptions (dispatch-header glyphs, index ticker-track
spans, the pinned-card author chip) sit further from the dash character than a short regex
context window reaches; scanners need to look a few hundred bytes back for the owning class
before flagging. Both are recorded so the next pass derives a clean matrix on the first try.

## Improvement: FAQ tranche 6, eight more posts from 3 to 5 questions

The 08-13 pass named tranche 6 and this pass executed it exactly as specified: HS codes
(Nº 107), restocking returns (Nº 103), releasing held orders, splitting orders across
multiple suppliers, combining multiple orders from the same customer, merging duplicate
customer profiles, blocking a customer, and pausing ads for out-of-stock products. Each
gained two questions, three to five.

The sixteen new Q&As were authored fresh in house style, grounded strictly in each post's own
researched body content, so no unsourced claim enters the citable pool. Answers run 147 to
151 words, direct answer first, quantified where the posts are quantified: the 0.85, 1.5,
and temporary 0.5 percent duty-calculation fees charged even when the estimate ran on blanks,
the five to ten percent of a day's ad budget leaking to sold-out products, the nine-of-twelve
release-ranking arithmetic, and the New Jersey 3PL restock that a Charleston studio will
never find. Two more Flow-scoped questions (can Flow tell when a returned package is
delivered, how do I hold a short order automatically with Flow's Hold fulfillment order
action) extend the question class the 08-03 rationale singled out as GEO-effective, and the
how-do-I phrasings (how do I find products missing HS codes, how do I find duplicate customer
profiles, how do I avoid blocking the wrong person) target queries answer engines actually
receive. Zero em or en dashes, zero double quotes, straight apostrophes throughout.

The dedup discipline earned its keep again: three planned angles were dropped before drafting
because their substance already lived in an existing answer. The all-or-nothing hold release
and the status:ON_HOLD polling pattern are already the spine of the existing release-hold Flow
answer; the feed-mismatch disapproval risk already closes the existing why-do-ads-keep-running
answer; and plus-addressed email evasion already appears in the existing Flow-blocking answer.
Replacement angles were authored from untouched body material instead: the release-ranking
answer, the wasted-spend arithmetic answer, and the false-positive protection answer.

Mechanics, asserted before write on every file: visible `.faq-item` blocks appended at the
end of each `faq-list` in exact house markup; matching Question nodes appended to each
FAQPage `mainEntity`; JSON text byte-identical to visible text; JSON-LD re-parsed; tag
balance re-verified; visible and JSON counts both equal 5. The formatting split held again:
seven of the eight posts carry fully pretty-printed Question nodes and took pretty-printed
insertions, and one (restocking returns) carries compact single-line Question nodes and took
compact insertions. The citable pool now stands at **279 questions across 61 posts**
(48 posts at five, 13 at three, including the newly landed Nº 108).

**Dating convention:** substantive content change, so the eight posts' `dateModified` and
`article:modified_time` advanced to 2026-08-14 and their sitemap `lastmod` bumped to match.
`datePublished`, feed pubDates, and llms.txt bylines untouched. index.html, feed.xml, and
llms.txt belong to today's publish run and were not touched by this pass.

## Concurrency: the closest call yet, same files, same minute

The stagger warning carried through seven reports stopped being hypothetical today. The daily
publish run landed Nº 108 while this pass was mid-flight: index.html at 19:01:10, feed and
llms.txt at 19:01:24, and its mesh-card insertions across all 60 sibling posts, including all
eight posts this pass was about to edit, immediately before this pass's writes at 19:01:42.
The write sets were not disjoint; the same eight files were edited by both writers inside one
minute. The merge survived on ordering luck: this pass reads each file immediately before
writing it, so its 19:01:42 read picked up the publish run's card insertions and layered the
FAQ blocks on top. Had the two writers interleaved the other way, the publish run's cards
would have been silently overwritten in eight posts and the mesh would have needed repair.
Post-settle verification confirms the clean merge in both directions: Nº 108's card is first
in all eight edited grids, all eight posts hold five byte-matched FAQs, and the full matrix
passes with zero issues. The stagger recommendation is no longer carried; it is escalated.

## Full audit matrix (post-settle, all passing)

| Check | Result |
|---|---|
| JSON-LD parse, all 64 rendered pages (incl. index @graph) | 0 errors |
| FAQ JSON-LD matches visible text, all 61 posts incl. 8 newly deepened | PASS |
| FAQ counts: visible == JSON on every post | 61 / 61 |
| canonical = filename = og:url; og/twitter sets complete | 62 / 62 |
| exactly one h1; lang; viewport; img alt | 62 / 62 |
| duplicate titles / meta descriptions; descriptions <= 160 chars | 0 / 0 / PASS |
| broken internal links / absolute self-domain hrefs in body | 0 |
| author @id resolves to `#priya-singh`; speakable/about/mainEntityOfPage/image | 61 / 61 |
| dateModified vs article:modified_time agreement; future dates | 0 mismatches / 0 |
| dispatch numbering Nº 48..108 (glyph and entity forms) | contiguous, 0 dupes |
| sitemap.xml: 62 locs = 61 wired + index, 0 dupes, 0 ghosts, valid XML | PASS |
| feed.xml: 62 items, unique guids, weekday-correct dates | PASS |
| llms.txt: 61 article entries, all wired | PASS |
| stubs: 61, bijective onto wired posts, noindex + live targets | PASS |
| sibling mesh: Nº 108 first in all 60 grids; newer-than-self blocks contiguous | PASS |
| mesh curated tails: all older than host; 0 dupes, 0 self-links, 0 ghosts | PASS |
| index hub graph: 62 blogPost entries; hero ISSUE Nº 108 | PASS |
| index ticker: 12 NEW DISPATCHES THIS MONTH = 12 actual Aug posts | PASS |
| raw em/en dashes in authored body and FAQ copy | 0 (standing chrome exempt) |
| tag balance, all 125 files | balanced |
| rejects (2): noindexed, unwired, absent from all surfaces | PASS |

## Checked and deliberately left alone

- **The two rejected drafts**: untouched, delete-on-a-supervised-run recommendation stands.
- **robots.txt**: the 33-agent AI-crawler allowance list still reflects the landscape;
  unchanged since 07-28.
- **Template chrome**: title-suffix em dashes, dispatch-header spans (glyph and entity
  forms), ticker-track spans, CSS-comment glyphs, and the pinned-card author chip, all
  standing rulings.
- **index.html, feed.xml, llms.txt**: owned by today's publish run; correct on
  re-verification, not touched by this pass.

## Recommendations for the owner

1. **Stagger the three schedules, urgently.** Today the publish run and this pass edited the
   same eight files inside one minute and survived on read-before-write ordering luck. An
   hour of separation between the publish run, the QA sweep, and this pass removes the risk
   entirely. This is the eighth report to raise it and the first where the collision actually
   happened.
2. **Continue the FAQ tranches.** 13 posts remain at three questions; two more passes
   finish the program. Suggested tranche 7, freshest first by the same head-term logic:
   fake accounts and spam signups (Nº 108), unpaid draft order follow-ups (Nº 101),
   pickup-to-shipping conversions (Nº 96), warehouse routing (Nº 93), supplier feed sync
   (Nº 92), discount codes applying to sale items (Nº 86), gift messages and gift wrap
   (Nº 85), and bundle inventory sync (Nº 83). That leaves five (Nº 81, 77, 76, 65, 57)
   for a final tranche 8.
3. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
4. **Commit and deploy.** The owner's `0bb4416` commit captured everything through the
   08-13 passes; the uncommitted tree now holds today's QA report, the Nº 108 publish, and
   this pass's 9 edits. Nothing on blog.dugong.live reflects any of it until pushed. No
   commit or push was made, per scheduled-run convention.

## Conclusion

Sixth consecutive defect-free baseline, a sixth FAQ tranche executed to spec, and the
concurrency risk finally cashed out, harmlessly, but only by ordering luck. The sixteen
pages most likely to earn answer-engine citations for their head terms now all field five
grounded, quantified questions, 279 Q&As sit in the citable pool across 61 posts, and the
dedup discipline again kept three would-be near-duplicates out of it. The mesh-invariant
and chrome-exemption tooling notes should make the next pass's first matrix derivation
clean. One more publish like today's, an hour of schedule separation, and this folder
stops depending on luck at all.

**9 files edited: the 8 deepened posts and sitemap.xml. 1 file created: this report.**
