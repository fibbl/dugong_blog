# SEO / GEO report, 2026-08-25 (71 files edited, 2 created)

**Scope:** Scheduled full-site SEO/GEO pass, the first since 08-24. Timeline since the 08-24
QA (12:02): the tree was committed (0f8cfb7), and then today at 11:20-11:21 a publish run
landed partially, for the second day running: the Nº 115 post file
(`how-to-put-your-shopify-store-on-vacation-mode-without-losing-sales.html`) and part of
index.html were written, and the run stopped there. No run log (`blog-run-2026-08-25.md`)
was written, and no other surface was touched. This is the same failure shape the 08-24 QA
documented for Nº 114, at almost the same minute of the day.

## Result: one major defect (interrupted publish) and one minor defect (long meta description), both fixed. The site now audits clean on every check.

## Defect 1: the Nº 115 publish run was interrupted mid-wiring

What the interrupted run had done: the post file itself (complete and internally clean
except for Defect 2), the index card-tall (old card-tall correctly demoted), the index
BlogPosting JSON-LD node (69th), and three topic-cloud links.

What it had NOT done, leaving the post linked from the index grid but invisible to feeds,
crawlers, and every sibling page: the index hero still read ISSUE Nº 114 / AUG 24 · 2026,
the dispatches stat still read 114, the ticker still read 18 NEW DISPATCHES THIS MONTH (×2),
and there was no redirect stub, no sitemap entry, no feed item, no llms.txt entry, no
llms-full.txt entry, no sibling-mesh card anywhere, and no run log.

**Fixed by this run, following the conventions the 08-24 QA established for the identical
Nº 114 case:**

- index: hero → ISSUE Nº 115 / AUG 25 · 2026, stat → 115, ticker → 19 ×2 (matches the 19
  August pubDates now in the feed)
- stub created: `the-vacation-your-store-wont-let-you-take.html` (noindex, meta-refresh +
  JS redirect + canonical, byte-pattern identical to the existing 67). Narrative title
  chosen by this run: "The vacation your store won't let you take", consistent with the
  family
- sitemap.xml: post added (0.9 / monthly / lastmod 2026-08-25), root lastmod bumped to
  2026-08-25; 69 locs
- feed.xml: item added at top (pubDate Tue, 25 Aug 2026 12:00:00 +0000, description = the
  index card-tall dek verbatim, per convention), lastBuildDate bumped; 69 items
- llms.txt: entry inserted after the lead essay, summary = card dek, "By Priya Singh,
  2026-08-25."
- llms-full.txt: full-text entry inserted as the first article. The converter was validated
  before use by regenerating the existing Nº 114 entry from its source page: 3,540 of 3,540
  words identical and the playbook fence byte-identical. On Nº 115 the `<pre id="playbook">`
  block survived verbatim inside its fence, the following paragraph was NOT swallowed
  (the failure class QA documented on 08-23 and 08-24 was checked for explicitly), and the
  whitespace-normalized word round-trip against the source page shows zero missing content
  (the only excluded tokens are the "Back to Field Notes" nav chrome, excluded by
  convention)
- sibling mesh: Nº 115 card (narrative title, 10 min, AUG 25, short dek) inserted at the
  top of the related grid in all 67 wired posts; the two noindexed rejects excluded, and
  sibling dateModified values deliberately not bumped, matching prior mesh inserts

## Defect 2: Nº 115 shipped with a 175-character meta description

The site convention (enforced since the audit matrix existed) is descriptions ≤ 160
characters, and all 67 prior posts comply. The interrupted run shipped Nº 115 with a
175-character description in the meta description, twitter:description, and the index
BlogPosting node (og:description and the page's JSON-LD description are the long-dek
surfaces by convention and were left alone). Rewritten to 160 characters exactly, in all
three short-description locations: "Shopify has no vacation mode: the official options
close your store or tie your pause to a billing cycle. The AI playbook that keeps selling
while you are away." No date fields moved: the post was already dated 2026-08-25.

## Full audit matrix (all recomputed 2026-08-25, post-edit, all passing)

Inventory: **139 HTML files** = 71 rendered (68 wired posts + index.html + 2 noindexed
rejected drafts) and 68 redirect stubs, plus sitemap.xml, feed.xml, llms.txt, llms-full.txt,
robots.txt, CNAME. Dispatches run Nº 48 through Nº 115, contiguous, no duplicates.

| Check | Result |
|---|---|
| JSON-LD parses, all 71 rendered pages (incl. index @graph) | 0 errors |
| FAQ parity: visible == FAQPage JSON, questions AND answers, entity-decoded | 68 / 68 |
| FAQ counts: 5 on every post; 340 total | 68 / 68 |
| canonical == og:url == filename; og/twitter sets complete incl. og:image w/h/alt | 68 / 68 |
| exactly one h1; lang; viewport; img alt coverage | 71 / 71 |
| duplicate titles / meta descriptions; descriptions ≤ 160 chars | 0 / 0 / PASS (after Defect 2 fix) |
| broken internal links across all rendered pages | 0 |
| author @id resolves to `#priya-singh` on all 68 posts | PASS |
| dateModified == article:modified_time == sitemap lastmod; future dates | 0 / 0 / 0 |
| dispatch numbering Nº 48..115 | contiguous, 0 dupes |
| sitemap.xml: valid XML, 69 locs (68 posts + root), 0 dupes, 0 ghosts | PASS |
| feed.xml: valid XML, 69 items, unique guids, atom self-link, weekday-correct pubDates, no future dates | PASS |
| llms.txt: all 68 wired posts + lead essay + llms-full pointer, 0 ghosts, 0 dupes | PASS |
| llms-full.txt: 68 URL-unique entries, Nº 115 leading newest-first, 142 fence markers balanced, 69 h1 outside fences | PASS |
| llms-full.txt: 0 flattened playbook lines outside fences; Nº 115 fence == source `<pre>` verbatim | PASS |
| llms-full.txt round-trip: Nº 115 entry vs source page, word-level | 0 missing content |
| llms-full.txt: 0 HTML leftovers, 0 raw em/en dashes, 0 replacement chars | PASS |
| stubs: 68, bijective onto wired posts, noindexed, targets live | PASS |
| sibling mesh: Nº 115 card present in all 67 sibling posts | PASS |
| index: 69 BlogPosting nodes, WebSite + Organization entities, exactly one card-tall, all 68 posts carded, hero/stat/ticker consistent | PASS |
| raw em/en dashes in authored copy (standing chrome exclusions applied) | 0 |
| tag balance, all 139 HTML files | 0 problems |
| rejects (2): noindexed, absent from sitemap/feed/llms/llms-full/index | PASS |
| robots.txt vs current AI-crawler population; CNAME = blog.dugong.live | current / PASS |

Note on Nº 110: its dispatch header uses `&middot;` where every other post uses `&mdash;`.
Pre-existing chrome variant, does not affect numbering contiguity, ruled a non-defect and
left alone.

## robots.txt re-verified against the live crawler population

Checked against current 2026 crawler references rather than carrying the 08-24 verdict
forward. Every agent the references name (GPTBot, OAI-SearchBot, ChatGPT-User, ClaudeBot,
Claude-User, Claude-SearchBot, PerplexityBot, Perplexity-User, Google-Extended,
Applebot-Extended, Meta-ExternalAgent, Amazonbot, Bytespider, CCBot, and the rest) is
already explicitly allowed, and the blanket `User-agent: * Allow: /` covers anything newly
launched. No edit.

## Recommendations for the owner

1. **The publish workflow has now died mid-run two days in a row**, both times right after
   writing the post file and part of index.html, both times around 11:20, minutes after
   another scheduled pass. This is no longer a one-off: the run order (post → index cards →
   everything else) combined with the schedule collision looks like the trigger. The
   standing fixes both stand: stagger the three schedules by at least an hour, and make the
   publish workflow write a run log first so an interruption is visible.
2. **The publish workflow also shipped its first over-length meta description** (Defect 2).
   Worth adding a ≤ 160 check to the blog-run skill itself.
3. **The llms-full converter fix is still needed at the workflow level** (standing since
   08-23). This run's converter preserved the fence and the following paragraph, but the
   blog-run workflow's own converter remains unpatched — it never got far enough today to
   misbehave.
4. **Commit and deploy.** The working tree holds today's Nº 115 post plus this run's full
   wiring and fixes, 73 files against commit 0f8cfb7. Nothing on blog.dugong.live reflects
   any of it until pushed. No commit was made, per scheduled-run convention. Suggested
   message: "dispatch 115 wiring + SEO pass".
5. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
6. **If the publish workflow re-fires today, it must verify rather than double-post**, per
   the Aug 22 precedent. Nº 115 is now fully wired; a second run should find nothing to do.

## Verification method note

All counts recomputed from the files; nothing carried forward from the 08-24 reports.
Pre-edit backups of index.html, sitemap.xml, feed.xml, llms.txt, llms-full.txt, and the
post were retained during the run. The llms-full converter was calibrated by round-tripping
the existing Nº 114 entry (word-identical, fence byte-identical) before being trusted with
Nº 115. Autonomous choices made by this run (user not present): the narrative stub title,
the mesh-card dek, the 160-character rewritten description, and the decision to complete
the interrupted publish rather than roll it back (the post file was complete; only wiring
and the description were defective). `.fuse_hidden*` files are mount artifacts, ignored per
convention.

**71 files edited (index, sitemap, feed, llms.txt, llms-full.txt, the Nº 115 post, and 67
sibling posts, minus overlaps: 73 paths changed in total against git). 2 files created: the
redirect stub and this report.**
