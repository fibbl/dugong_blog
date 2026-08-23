# SEO / GEO report, 2026-08-23 (0 files edited, 1 created)

**Scope:** Scheduled full-site SEO/GEO pass, the first since 08-20. Two dispatches have landed
since: **Nº 112** ("The stock count that changes overnight", 08-22) and **Nº 113** ("The order
confirmation that never arrives", 08-23, this morning's publish run). Inventory re-derived:
**135 HTML files** = 69 rendered (66 wired posts + index.html + 2 noindexed rejected drafts)
and 66 redirect stubs, plus sitemap.xml, feed.xml, llms.txt, llms-full.txt, robots.txt.
Dispatches run Nº 48 through Nº 113, contiguous, no duplicates.

## Result: zero defects. The whole matrix passes on the first derivation.

Every row was recomputed from the files, nothing carried forward. This is the third
defect-free baseline in the pass series, and the first recorded **after** an intervening
publish run, which is the meaningful part: the two structural leaks the last two reports
flagged have both closed.

1. **The publish workflow now regenerates llms-full.txt.** The 08-20 report predicted every
   future publish run would strand the full-text surface one dispatch behind, and 08-22
   proved it (Nº 111 missing, fixed by QA). Today's run report lists llms-full.txt among
   files touched, and the file verifies current: 66 entries, Nº 113 leading, newest first,
   URL-unique, fences balanced. The workflow-level fix recommended on 08-20 has evidently
   been adopted.

2. **The 3-question FAQ debt on Nº 111 and Nº 112 is already paid.** The 08-22 QA flagged
   both for "the next SEO/GEO pass." By the time this pass ran, both posts carry five
   questions with exact visible/JSON-LD parity, dateModified and article:modified_time
   bumped to 2026-08-22, sitemap lastmod in agreement, and their llms-full.txt entries in
   sync. The FAQ program now stands at **330 questions (66 posts × 5)** across every
   surface: pages, FAQPage structured data, and llms-full.txt, verified question-by-question
   and answer-by-answer at the entity-decoded level.

## Full audit matrix (all recomputed 2026-08-23, all passing)

| Check | Result |
|---|---|
| JSON-LD parses, all 69 rendered pages (incl. index @graph) | 0 errors |
| FAQ parity: visible == FAQPage JSON, questions AND answers, entity-decoded | 66 / 66 |
| FAQ counts: 5 on every post; 330 total | 66 / 66 |
| FAQ text in llms-full.txt matches pages (questions and answers) | 330 / 330 |
| canonical == og:url == filename; og/twitter sets complete incl. og:image w/h/alt | 67 / 67 |
| exactly one h1; lang; viewport; img alt coverage | 67 / 67 |
| duplicate titles / meta descriptions; descriptions <= 160 chars | 0 / 0 / PASS |
| broken internal links across all rendered pages | 0 |
| author @id resolves to `#priya-singh` on all 66 posts | PASS |
| dateModified == article:modified_time; == sitemap lastmod; future dates | 0 / 0 / 0 |
| dispatch numbering Nº 48..113 | contiguous, 0 dupes |
| sitemap.xml: 67 locs (66 posts + root), 0 dupes, 0 ghosts, valid XML | PASS |
| sitemap lastmod: root + Nº 113 at 08-23; Nº 111, Nº 112 at 08-22 (FAQ deepening) | PASS |
| feed.xml: 67 items, unique guids, atom:link rel=self, 17 Aug pubDates == ticker 17 ×2 | PASS |
| llms.txt: all 66 wired posts + lead essay + llms-full pointer, 0 ghosts | PASS |
| llms-full.txt: 66 entries incl. Nº 112 and Nº 113, URL-unique, fence-balanced | PASS |
| llms-full.txt body spot-checks against source pages (3 newest posts) | verbatim |
| stubs: 66, bijective onto wired posts, noindexed, targets live | PASS |
| sibling mesh: Nº 113 card present in all 65 sibling posts | PASS |
| index: hero Nº 113 / AUG 23 / 67 BlogPosting nodes / WebSite + Organization entities | PASS |
| schema stack: BlogPosting, BreadcrumbList, FAQPage, HowTo (ItemList on listicle), speakable, about | 66 / 66 |
| raw em/en dashes in authored copy incl. llms-full.txt | 0 |
| tag balance, all 135 HTML files | balanced |
| rejects (2): noindexed, unwired, absent from sitemap/feed/llms/llms-full/index | PASS |
| robots.txt: AI-crawler allowance list vs current crawler population | current |

## Checked and deliberately left alone

- **robots.txt.** Reviewed against current 2026 crawler references. Every agent the
  references name is already listed (GPTBot, OAI-SearchBot, ChatGPT-User, ClaudeBot,
  Claude-User, Claude-SearchBot, PerplexityBot, Perplexity-User, Google-Extended,
  Applebot/-Extended, Meta-ExternalAgent, Amazonbot, MistralAI-User, DuckAssistBot, CCBot,
  and the rest), and the blanket `User-agent: * Allow: /` makes further explicit entries
  cosmetic. No edit.
- **Structured data.** The stack is complete on every post, and index carries WebSite and
  Organization (with logo and sameAs) for entity grounding. Nothing to add without
  inventing content.
- **index.html lacking article:published_time** is correct; it is a Blog page, not an
  article.
- **The two rejected drafts**: untouched; the delete-on-a-supervised-run recommendation
  stands (since 08-02).
- **Template chrome** (title-suffix em dashes, CSS-comment glyphs, ticker spans): standing
  rulings, unchanged.

## Recommendations for the owner

1. **Commit and deploy.** The working tree holds Nº 112, Nº 113, the FAQ deepening of
   Nº 111/112, and all surface updates, uncommitted (last commit "Changes"). Nothing on
   blog.dugong.live reflects any of it until pushed. No commit was made, per scheduled-run
   convention. Suggested message: "dispatches 112-113 + FAQ deepening + wiring".
2. **Deduplicate the doubled daily trigger.** The 08-22 second trigger verified rather than
   double-posted, which is the right behavior, but the schedule itself still fires twice.
3. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
4. **Nothing else.** With llms-full regeneration now inside the publish workflow and the FAQ
   program complete at 330, the remaining ranking inputs (freshness via the daily publish,
   external links, and time) are not things a maintenance pass can manufacture. The correct
   output of a clean pass is this report, not synthetic churn.

## Conclusion

A busy four days (two dispatches, one QA repair, one FAQ deepening) and the tree still
audits clean on the first derivation, with both previously flagged structural leaks closed
at the workflow level. No page was touched, so no dateModified, lastmod, or pubDate moved
anywhere.

**0 files edited. 1 file created: this report.**
