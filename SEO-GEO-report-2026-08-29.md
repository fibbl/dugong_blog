# SEO / GEO report — 2026-08-29

Scheduled autonomous run. Last pass: 2026-08-25 (Nº 115 wired and repaired). No new
dispatch has landed since then — the newest file in the tree is dated Aug 25, and the
working tree is clean against commit 54d26fd (the Aug 26 commit picked up the 08-25
wiring, so recommendation 4 from that report is now done). With nothing new to wire,
this run was a full re-audit plus a robots.txt re-verification.

## Result: zero defects

Every check recomputed from the files today. Nothing carried forward from 08-25.

## Full audit matrix (all recomputed 2026-08-29, all passing)

Inventory: **139 HTML files** = 71 rendered (68 wired posts + index.html + 2 noindexed
rejected drafts) and 68 redirect stubs, plus sitemap.xml, feed.xml, llms.txt,
llms-full.txt, robots.txt, CNAME. Dispatches Nº 48 through Nº 115, contiguous, no
duplicates.

| Check | Result |
|---|---|
| JSON-LD parses, all 71 rendered pages (incl. index @graph) | 0 errors |
| FAQ parity: visible == FAQPage JSON, questions AND answers, entity-decoded | 68 / 68 |
| FAQ counts: 5 on every post; 340 total | 68 / 68 |
| canonical == og:url == filename; og/twitter sets complete incl. og:image w/h/alt | 68 / 68 |
| exactly one h1; lang; viewport; img alt coverage | 71 / 71 |
| duplicate titles / meta descriptions; descriptions ≤ 160 chars | 0 / 0 / PASS |
| broken internal links across all rendered pages | 0 |
| author @id resolves to `#priya-singh` on all 68 posts | PASS |
| dateModified == article:modified_time == sitemap lastmod; future dates | 0 mismatches / 0 |
| dispatch numbering Nº 48..115 | contiguous, 0 dupes |
| sitemap.xml: valid XML, 69 locs (68 posts + root), 0 dupes, 0 ghosts | PASS |
| feed.xml: valid XML, 69 items (68 posts + lead essay), unique guids, atom self-link, weekday-correct pubDates, no future dates | PASS |
| llms.txt: all 68 wired posts + lead essay + llms-full pointer, 0 ghosts, 0 dupes | PASS |
| llms-full.txt: 68 URL-unique entries, 142 fence markers balanced | PASS |
| llms-full.txt: 0 HTML leftovers outside fences, 0 raw em/en dashes, 0 replacement chars | PASS |
| stubs: 68, bijective onto wired posts, noindexed, targets live | PASS |
| index: 69 BlogPosting nodes, WebSite + Organization entities, all 68 posts carded, hero ISSUE Nº 115 consistent | PASS |
| raw em/en dashes in authored copy (standing chrome exclusions applied) | 0 |
| tag balance, all 139 HTML files | 0 problems |
| rejects (2): noindexed, absent from sitemap / feed / llms / llms-full / index | PASS |
| robots.txt vs current AI-crawler population; CNAME = blog.dugong.live | current / PASS |

Notes on flags this run's tooling raised and cleared as non-defects:

- The 34 older posts (literal `Nº` chrome variant) carry literal em dashes in the
  dispatch ticker, `<title>`, and RSS-link chrome; the newer posts use `&mdash;`. These
  are the standing chrome exclusions — zero raw dashes in authored copy. Same for the
  9 in index.html (title/og tags, ticker, one card byline). Both variants render
  identically; ruled non-defects, consistent with the Nº 110 `&middot;` precedent.
- The feed's 69th item is the lead essay ("The death of the drag-and-drop builder",
  guid `/#dispatch-47`), by design.

## robots.txt re-verified against the live crawler population

Checked against current 2026 crawler references rather than carrying the 08-25 verdict
forward. Every agent the references name — GPTBot, OAI-SearchBot, ChatGPT-User,
ClaudeBot, Claude-User, Claude-SearchBot, anthropic-ai, PerplexityBot, Perplexity-User,
Google-Extended, Applebot-Extended, Meta-ExternalAgent, Amazonbot, Bytespider, CCBot,
and the rest — is already explicitly allowed, and the blanket `User-agent: * Allow: /`
covers anything newly launched. The strategic split some sites now make (allow
search-time bots, block training bots) is intentionally not used here: the site's GEO
stance is maximal citation eligibility. No edit.

## Recommendations for the owner

1. **The publish workflow has not fired since Aug 25** (last new dispatch Nº 115; prior
   cadence was roughly every 1–2 days). If that pause is intentional, fine; if not, the
   blog-run schedule may have stalled after the two mid-run deaths documented on 08-24
   and 08-25. Worth checking the scheduled-task list.
2. **Nothing to commit from this run except this report.** The tree was clean; this run
   changed no site files. Suggested message: "SEO/GEO audit 2026-08-29".
3. **Delete the two rejected drafts** on a supervised run (standing since 08-02):
   `how-to-automatically-follow-up-on-unpaid-draft-order-invoices-on-shopify.html` and
   `how-to-send-payment-reminders-for-unpaid-draft-orders-on-shopify.html`. They remain
   noindexed and excluded from every surface, so they cost nothing meanwhile.
4. **The llms-full converter fix at the blog-run workflow level is still outstanding**
   (standing since 08-23). All 68 current entries are clean, but the next publish run
   will use the unpatched converter.
5. **The ≤ 160-character description check should be added to the blog-run skill**
   (standing since 08-25), so the next publish can't ship another over-length
   description.

## Verification method note

All counts recomputed from the files by script; FAQ parity checked question-and-answer,
entity-decoded and whitespace-normalized; feed pubDate weekdays validated against the
calendar; tag balance parsed on all 139 files. Autonomous choices this run: treating the
literal-dash chrome variant and the lead-essay feed item as non-defects (both consistent
with prior rulings), and making no freshness edits — no content changed, so no
dateModified, lastmod, or lastBuildDate values were bumped. No commit was made, per
scheduled-run convention. `.fuse_hidden*` files are mount artifacts, ignored per
convention.

**0 site files edited. 1 file created: this report.**
