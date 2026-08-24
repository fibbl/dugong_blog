# SEO / GEO report, 2026-08-24 (0 files edited, 1 created)

**Scope:** Scheduled full-site SEO/GEO pass, the first since 08-23. Nothing has landed since:
the last writes to the tree were yesterday's publish run (Nº 113, 11:25), the 08-23 SEO pass
(11:45), and the 08-23 QA repair of llms-full.txt (11:58). Today's daily publish run had not
fired as of this pass, so no Nº 114 exists yet. Inventory re-derived from the files:
**135 HTML files** = 69 rendered (66 wired posts + index.html + 2 noindexed rejected drafts)
and 66 redirect stubs, plus sitemap.xml, feed.xml, llms.txt, llms-full.txt, robots.txt, CNAME.
Dispatches run Nº 48 through Nº 113, contiguous, no duplicates.

## Result: zero defects. The whole matrix passes on the first derivation.

Every row was recomputed from scratch, nothing carried forward from the 08-23 reports. This
is the fourth consecutive defect-free baseline, and it confirms the 08-23 QA repair held: the
three llms-full.txt entries that had shipped with flattened playbook specs (Nº 111 through
Nº 113) now verify with zero flattened playbook lines outside code fences, and body
paragraphs and FAQ answers spot-checked on the three newest posts are verbatim against their
source pages, 15 checks of 15.

## Full audit matrix (all recomputed 2026-08-24, all passing)

| Check | Result |
|---|---|
| JSON-LD parses, all 69 rendered pages (incl. index @graph) | 0 errors |
| FAQ parity: visible == FAQPage JSON, questions AND answers, entity-decoded | 66 / 66 |
| FAQ counts: 5 on every post; 330 total | 66 / 66 |
| FAQ question lines in llms-full.txt | 330 / 330 |
| canonical == og:url == filename; og/twitter sets complete incl. og:image w/h/alt | 66 / 66 |
| exactly one h1; lang; viewport; img alt coverage | 69 / 69 |
| duplicate titles / meta descriptions; descriptions <= 160 chars | 0 / 0 / PASS |
| broken internal links across all rendered pages | 0 |
| author @id resolves to `#priya-singh` on all 66 posts | PASS |
| dateModified == article:modified_time == sitemap lastmod; future dates | 0 / 0 / 0 |
| dispatch numbering Nº 48..113 | contiguous, 0 dupes |
| sitemap.xml: 67 locs (66 posts + root), 0 dupes, 0 ghosts, valid XML | PASS |
| feed.xml: 67 items, unique guids, atom:link rel=self, weekday-correct pubDates, no future dates | PASS |
| llms.txt: all 66 wired posts + lead essay + llms-full pointer, 0 ghosts | PASS |
| llms-full.txt: 66 URL-unique entries, Nº 113 leading newest first, 138 fence markers balanced | PASS |
| llms-full.txt: 0 flattened playbook lines outside fences (08-23 repair holding) | PASS |
| llms-full.txt body + FAQ spot-checks vs source pages (3 newest posts) | 15 / 15 verbatim |
| llms-full.txt: 0 HTML leftovers, 0 raw em/en dashes, 0 replacement chars | PASS |
| stubs: 66, bijective onto wired posts, noindexed, targets live | PASS |
| sibling mesh: Nº 113 card present in all 65 sibling posts | PASS |
| index: 67 BlogPosting nodes, WebSite + Organization entities present | PASS |
| raw em/en dashes in authored copy (standing chrome exclusions applied) | 0 |
| tag balance, all 135 HTML files | 0 problems |
| rejects (2): noindexed, absent from sitemap/feed/llms/llms-full/index | PASS |
| robots.txt vs current AI-crawler population; CNAME = blog.dugong.live | current / PASS |

## robots.txt re-verified against the live crawler population

Rather than carry the 08-23 "current" verdict forward, this pass re-checked the allowance
list against current 2026 crawler references. Every agent those references name (GPTBot,
OAI-SearchBot, ChatGPT-User, ClaudeBot, Claude-User, Claude-SearchBot, PerplexityBot,
Perplexity-User, Google-Extended, Applebot-Extended, Meta-ExternalAgent, Amazonbot,
Bytespider, CCBot, and the rest) is already explicitly listed, and the blanket
`User-agent: * Allow: /` covers anything newly launched. The references note major new AI
user agents appear only 2 to 4 times a year. No edit.

## Checked and deliberately left alone

- **Structured data.** BlogPosting, BreadcrumbList, FAQPage, HowTo (ItemList on the
  listicle), speakable, and about/mentions entities verified on every post; index carries
  WebSite and Organization. Nothing to add without inventing content.
- **The two rejected drafts**
  (`how-to-automatically-follow-up-on-unpaid-draft-order-invoices-on-shopify.html`,
  `how-to-send-payment-reminders-for-unpaid-draft-orders-on-shopify.html`): untouched;
  delete-on-a-supervised-run recommendation stands (since 08-02).
- **Template chrome** (title-suffix em dashes, RSS link titles, ticker and dispatch-header
  spans, index quote-card attribution): all 72 raw-dash sightings classified into these
  standing rulings, zero in authored copy.
- **No page was touched**, so no dateModified, article:modified_time, sitemap lastmod, or
  feed pubDate moved anywhere. `.fuse_hidden*` files are mount artifacts, ignored per
  convention.

## Recommendations for the owner

1. **Fix the llms-full regenerator's `<pre>` handling at the workflow level.** Standing
   since the 08-23 QA: the publish workflow's converter flattens playbook blocks. Today the
   file is clean only because QA repaired it after the fact; the next publish run (Nº 114)
   will likely reintroduce the flattening on its new entry until the blog-run skill's
   converter preserves `<pre>` line structure inside a fence.
2. **Commit and deploy.** The working tree still holds everything since commit f8f50d4:
   Nº 112, Nº 113, the FAQ deepening of Nº 111/112, the llms-full repair, and all surface
   updates. Nothing on blog.dugong.live reflects any of it until pushed. No commit was made,
   per scheduled-run convention.
3. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
4. **Standing schedule notes:** deduplicate the doubled daily trigger and stagger the three
   schedules by at least an hour so publish, QA, and SEO passes stop landing within minutes
   of each other.
5. **Nothing else.** With the FAQ program complete at 330, the schema stack full, and both
   GEO text surfaces current, the remaining ranking inputs (freshness via the daily publish,
   external links, and time) are not things a maintenance pass can manufacture.

## Conclusion

A quiet day: no publish run had landed since the 08-23 QA repair, and the tree audits clean
on the first derivation for the fourth pass running. The one open risk is upstream in the
publish workflow's llms-full converter, not in the site. The correct output of a clean pass
is this report, not synthetic churn.

**0 files edited. 1 file created: this report.**
