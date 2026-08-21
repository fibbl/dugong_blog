# SEO / GEO report, 2026-08-20 (2 files edited, 2 created)

**Scope:** Scheduled full-site SEO/GEO pass, the first since 08-16. No publish run has landed since
Dispatch Nº 110 settled on 08-16, so this pass inherited a quiet tree: **129 HTML files**, 66
rendered (63 wired posts + index.html + 2 noindexed rejected drafts) and 63 redirect stubs.
Dispatches run Nº 48 through Nº 110, contiguous, no duplicates. No writer collision was possible;
nothing else has touched the folder in four days.

## Baseline audit: clean on the first derivation

The full audit matrix was re-derived from scratch, entity-decoded FAQ comparison included. Every
row passed with zero defects: JSON-LD parse on all 66 rendered pages, FAQ parity at the
entity-decoded level with visible and JSON counts both at five on all 63 posts (315 questions
total, matching the closed program), canonicals equal to og:url with complete og and twitter sets,
one h1 with lang, viewport, and alt coverage everywhere, no duplicate titles or descriptions and
every description within 160 characters, zero broken internal links, author @id resolving to
#priya-singh on all 63 posts, dateModified in agreement with article:modified_time with no future
dates, sitemap at 64 locs with no dupes or ghosts and lastmod 2026-08-16 on exactly the eight
expected files, feed at 64 items with unique guids, llms.txt at 63 wired article entries, stubs
bijective onto wired posts, the Nº 110 sibling-mesh card present in all 62 siblings, no raw em or
en dashes in authored copy, tag balance across all 129 files, and both rejects noindexed and absent
from every surface. This is the second defect-free baseline this pass series has recorded, and the
first where no intervening publish run existed to introduce wiring gaps, which supports the 08-16
recommendation that the publish workflow, not the site, is where defects originate.

## Improvement: llms-full.txt, the full-text GEO surface

With the FAQ deepening program retired at 315 questions, this pass audited the remaining GEO
surface area before choosing a successor. The structured-data stack is already complete
(BlogPosting, BreadcrumbList, FAQPage, HowTo, Speakable, and about/mentions entities on all 63
posts; ItemList on the listicle by design), robots.txt's AI-crawler allowance list is current, and
llms.txt carries all 63 entries. The one missing piece of the llms.txt convention was its
companion: **llms-full.txt**, the single file that gives answer engines the complete article text
in one fetch instead of 63 crawls.

The file was generated programmatically from the rendered posts themselves, so nothing in it is
newly authored and no unsourced claim enters the citable pool. It carries all 63 dispatches newest
first at 1.04 MB. Each entry opens with the article title as a level-one heading, then a metadata
block (canonical URL, dispatch number, author, published and updated dates), the dek, the full
body converted to markdown with headings, lists, blockquotes, and callouts preserved in document
order, external links kept as markdown links so citations survive, the plain-language playbook
specs quoted verbatim inside code fences, and the five-question FAQ carrying text identical to
each page's FAQPage structured data. The lead essay (Nº 47, index.html) is referenced with its
llms.txt summary rather than extracted, since its markup is the homepage's, not the article
template's. The two rejects are excluded, matching every other surface.

Two conversion defects were caught and fixed before the file settled: a regex prefix collision
that let paragraph matching swallow pre blocks (the same class of bug was then found in the
verifier itself), and playbook specs initially flattening onto single lines that collided with
markdown h1 syntax. The shipped file verifies clean: 64 h1 lines outside fences (63 titles plus
the file header), 66 balanced fences, 63 unique canonical URL lines, 63 FAQ sections with 315
questions, zero HTML leftovers, zero em or en dashes, and spot-checked body paragraphs and FAQ
answers byte-identical to the source pages.

**Wiring:** llms.txt gained one header line pointing to the full-text file, and robots.txt's
answer-engine comment block gained the matching reference. llms-full.txt was deliberately kept out
of sitemap.xml, which stays reserved for indexable HTML, consistent with llms.txt's own absence.

**Dating convention:** no rendered page changed, so no dateModified, article:modified_time,
sitemap lastmod, or feed pubDate moved anywhere.

## Full audit matrix (post-change, all passing)

| Check | Result |
|---|---|
| JSON-LD parse, all 66 rendered pages (incl. index @graph) | 0 errors |
| FAQ JSON-LD matches visible text (entity-decoded), all 63 posts | PASS |
| FAQ counts: visible == JSON == 5 on every post; 315 total | 63 / 63 |
| canonical = og:url; og/twitter sets complete | 64 / 64 |
| exactly one h1; lang; viewport; img alt | 64 / 64 |
| duplicate titles / meta descriptions; descriptions <= 160 chars | 0 / 0 / PASS |
| broken internal links in rendered pages | 0 |
| author @id resolves to `#priya-singh` on all 63 posts | PASS |
| dateModified vs article:modified_time agreement; future dates | 0 mismatches / 0 |
| dispatch numbering Nº 48..110 | contiguous, 0 dupes |
| sitemap.xml: 64 locs, 0 dupes, 0 ghosts, valid XML, no llms-full | PASS |
| sitemap lastmod = 2026-08-16 on exactly the 8 files from that pass | 8 / 8 |
| feed.xml: 64 items, unique guids | PASS |
| llms.txt: 63 article entries + new full-text pointer | PASS |
| llms-full.txt: 63 entries, URL-unique, fence-balanced, source-verbatim | PASS |
| stubs: 63, bijective onto wired posts, noindex + live targets | PASS |
| sibling mesh: Nº 110 card present in all 62 sibling posts | PASS |
| raw em/en dashes in authored copy incl. llms-full.txt | 0 |
| tag balance, all 129 files | balanced |
| rejects (2): noindexed, unwired, absent from all surfaces incl. llms-full | PASS |

## Checked and deliberately left alone

- **The two rejected drafts**: untouched; delete-on-a-supervised-run recommendation stands.
- **robots.txt AI-crawler list**: reviewed against the current crawler population, still complete;
  only the comment block changed.
- **index.html, feed.xml, sitemap.xml**: verified, not modified; no content changed that would
  justify touching them.
- **Template chrome**: title-suffix em dashes, dispatch-header spans, ticker-track spans,
  CSS-comment glyphs, and the pinned-card author chip, all standing rulings.
- **Schema stack**: complete on every post; no additions warranted.

## Recommendations for the owner

1. **Add llms-full.txt regeneration to the publish workflow.** The file is a snapshot: the next
   dispatch that lands will make it one entry stale. The publish skill should append the new entry
   (or rerun the generator) as part of landing a dispatch, exactly as it wires llms.txt. Until it
   does, each scheduled SEO pass will need to refresh it.
2. **Investigate the publish cadence.** The daily publish run has not landed anything since 08-16.
   If that is intentional, fine; if the schedule silently stopped, four days of freshness signal
   have already been lost, and freshness is the one ranking input this pass cannot manufacture.
3. **Delete the two rejected drafts** on a supervised run, standing since 08-02.
4. **Commit and deploy.** The uncommitted tree now holds the 08-16 pass, Nº 110, and today's new
   GEO surface. Nothing on blog.dugong.live reflects any of it until pushed. No commit or push was
   made, per scheduled-run convention.

## Conclusion

A quiet tree audited clean on the first derivation, which let the pass spend its budget forward:
the site now serves its entire 63-dispatch corpus to answer engines in a single fetch, with every
word traceable to a rendered page, wired from both llms.txt and robots.txt, and verified
structurally sound. The matrix passes on all 20 rows.

**2 files edited: llms.txt (full-text pointer) and robots.txt (comment reference). 2 files
created: llms-full.txt and this report.**
