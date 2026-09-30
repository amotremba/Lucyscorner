# Session log — 2026-09-30

Work on Lucy's Corner (`github.com/amotremba/Lucyscorner`) and the Substack
publication. Five PRs opened and merged, one post published, Substack settings
configured.

---

## Merged

| PR | Commit | Change |
|---|---|---|
| [#1](https://github.com/amotremba/Lucyscorner/pull/1) | `8509480` | `substack:` front matter key + "The Squirrel She Never Caught" |
| [#2](https://github.com/amotremba/Lucyscorner/pull/2) | `07370a9` | Post linked to its published Substack Post |
| [#3](https://github.com/amotremba/Lucyscorner/pull/3) | `24c9eac` | Reconstructed `social-media-growth-plan.md` |
| [#4](https://github.com/amotremba/Lucyscorner/pull/4) | `22e05f2` | Cloudflare Web Analytics |
| [#5](https://github.com/amotremba/Lucyscorner/pull/5) | `b925b37` | Substack drafts + tracker exclusion |

### 1. Substack crosslink feature + squirrel post

Posts can declare their Substack counterpart:

```yaml
substack: https://anneotremba.substack.com/p/your-slug
```

`_layouts/post.html` renders an "Also on Substack" CTA; `blog/index.html` shows
a badge. Posts without the key render unchanged, so the feature shipped inert
and the first real use came later.

Wrote **"The Squirrel She Never Caught"** (2026-09-30, tag SQUIRREL WATCH) —
22 minutes of pursuit, zero catches. Reused `Lucychipmunkhunting.jpg`, which
already matched the post's ending beat.

**Why front matter and not URL matching:** Substack slugs are unpredictable
(`/p/lucys-corner` vs `/blog/:year/:month/:day/:title/`), so the mapping is
authored rather than derived.

**Verified:** all 12 pre-existing posts rendered unchanged, RSS valid, post count
intact, new post led both the blog index and the feed.

### 2. Linked the post to Substack

Went through three targets:

1. Note `/note/c-349748015` — worked, but Notes are short-form, ephemeral, and
   **don't reach email subscribers**
2. Note `/note/c-349759473` — same limitation
3. **Final: `/p/squirrel-watch`** — the actual newsletter post, confirmed via
   `rel="canonical"` and `og:title`

Stripped share-tracking params (`?r=...&utm_campaign=...`) before baking the URL
into front matter.

### 3. Reconstructed the growth plan

`social-media-growth-plan.md` was cited 7 times across two trackers and had never
been committed — every reference was a dead link.

Rebuilt from the cited context, marked as reconstructed in a header, separating:

- **Inferred** — cadences and thresholds, reconstructed from schedule tables
- **Verified** — platform rules and image-handling bugs, documented in the
  trackers with production evidence

Includes a Substack cross-posting section reflecting what shipped today, and
six open questions rather than invented answers. The biggest: **no numeric
success target exists anywhere in the repo.**

Caught a transcription error during review — Canva brand kit is `kAGRCFnMe8s`.

### 4. Cloudflare Web Analytics

The site had **no analytics at all**, so cadence decisions had no data behind
them.

Three insertion points needed — `_layouts/base.html` covers posts and the blog
index, but `index.html` and `album.html` have no layout front matter.

Chosen over Plausible ($9/mo, 30-day trial) because Cloudflare's free tier needs
neither. **Token still ships as a placeholder** — the beacon loads but records
nothing until set.

### 5. Substack drafts + tracker exclusion

Drafts for the welcome email and About page, plus `substack-drafts.md` indexing
them.

Added `_config.yml` `exclude:` — Jekyll copies root-level `.md` files into the
build, so the drafts *and* the three trackers were being served as public pages.
`social-media-project.md` was returning 200 with ~50 Blotato schedule IDs,
account IDs, and the Facebook page ID in the body. Pre-existing, not introduced
here, and the repo is public anyway — but working documents shouldn't ship as
pages. `README.md` remains published.

---

## Substack settings configured

| Item | Status |
|---|---|
| Name → Lucy's Corner | Done |
| Publication description | Done |
| About page body | Done |
| Closing links | Done (verified in browser) |
| Welcome email content | Unverified — private by design |
| Site link in `/p/lucys-corner` | Outstanding |

**Two composer traps hit:**

1. The **profile** Create button at `substack.com/@<handle>` produces **Notes**.
   The Post composer is under the *publication*:
   `anneotremba.substack.com/publish/posts`. Three Notes were published before
   this was found.
2. The About page has **two fields** — *description* (a one-liner, set
   correctly) and the *body* editor further down, initially empty. The About
   page rendered only Substack's default blocks until the body was filled.

---

## Two corrections made during the session

**A false 404 diagnosis.** Reported that the blog links were broken because
`baseurl: "/Lucyscorner"` appeared doubled. Wrong — the templates use Jekyll's
`relative_url` filter, which prepends the baseurl correctly. Checked the live
site instead of trusting the fetched markdown, and all six URLs returned 200.

**A false `TEST` string on the About page.** Reported stray test text that the
user couldn't find. The match was case-insensitive against Substack's
`data-testid` attributes and internal feature flags (`test_age_gate_user`).

**A methodology limitation worth remembering.** Checking whether a URL is
clickable by reading server HTML doesn't work when JavaScript linkifies on the
client side. The user confirmed both About links open in their browser; my
source-level check could not see it. Rendered-page observation beat markup
inspection.

---

## Outstanding

- **Cloudflare token** — replace `REPLACE_WITH_YOUR_CF_TOKEN` in three files.
  Verify the dashboard within 24h: Cloudflare only reports for sites behind its
  proxy, and GitHub Pages may not qualify. Umami's free tier is the fallback.
- **Welcome email** — confirm Settings → Emails shows the text saved. Can't be
  verified externally.
- **`/p/lucys-corner`** — add the missing website link inline. That post says
  *"you will probably see some her in some of the pictures on the website"* with
  no URL. Editable in place; no resend.
- **Redundant Notes** — `c-349748015` and `c-349755843` still returned 200 at
  last check. Worth confirming visually that both were deleted.
- **Growth plan open questions** — six listed in the file, including the missing
  numeric target. Round 2 ends 2026-10-20; analytics should be live by then to
  judge cadence against data.

---

## Reference

- **Site:** https://amotremba.github.io/Lucyscorner
- **Substack:** https://anneotremba.substack.com (`/p/squirrel-watch`)
- **Trackers:** `social-media-project.md`, `pinterest-project.md`,
  `social-media-growth-plan.md`
- **Drafts:** `substack-drafts.md` → welcome email + About page

### Useful paths

- Publish a Post: `anneotremba.substack.com/publish/posts` (not the profile's
  Create button)
- Publication settings: `anneotremba.substack.com/publish/settings`
- About page body: Settings → About → the blank editor under "About page"
- Local build: `/usr/local/lib/ruby/gems/4.0.0/bin/jekyll build` — `jekyll` isn't
  on PATH, and this clone has a narrow refspec so `gh pr create` needs `--head`