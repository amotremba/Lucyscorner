# Lucy's Corner — Social Media Growth Plan

> **⚠️ RECONSTRUCTED 2026-09-30 — REVIEW BEFORE RELYING ON IT.**
>
> This file was rebuilt from the rules cited in `social-media-project.md` and
> `pinterest-project.md`, which reference a growth plan that was never committed
> to the repo. Everything below is inferred from those citations, not recovered
> from the original. Dates, cadences, and thresholds are the parts most likely
> to be wrong. Correct them here and the trackers follow.
>
> What is **not** inferred and should be treated as authoritative: the platform
> rules, guardrails, and workflows — those are quoted or restated in the
> trackers and are verifiable against what actually shipped.

**Site:** https://amotremba.github.io/Lucyscorner/
**Substack:** https://anneotremba.substack.com

Trackers: [`social-media-project.md`](social-media-project.md) (Instagram, Facebook, Bluesky, Threads, X, TikTok) · [`pinterest-project.md`](pinterest-project.md) (Pinterest)

---

## Goal

Grow an audience that drives traffic to Lucy's Corner, where the revenue is:
the affiliate `#shop` grid (13 products) and the Substack subscriber list.

Traffic is the only thing these platforms are for. Engagement metrics are
diagnostic, not the objective.

---

## Cadence

Reconstructed from the schedule tables in `social-media-project.md`. The
underlying principle the trackers actually cite: **don't let the feed read as a
straight run of ads.**

| # | Cadence | Evidence |
|---|---|---|
| 1 | Shop spotlight: one product every 2 days | 10 products, 09-12 → 09-30, every 2 days (line 72) |
| 2 | Pinterest shop pins: 1/day at 9:00 AM CDT, interleaved with IG/FB so the two don't collide | `pinterest-project.md` line 131 |
| 3 | IG/FB posts at 10:00 AM CDT; Threads/X 5 min later (10:05) | Lines 72, 76 |
| 4 | Weekly light cross-post to Threads/X | Line 76, cited as "cadence #4" |
| 5 | "In-between" days get adventure posts, not product posts | Lines 141, 151 |

### Rules the trackers cite as binding

- **Stagger across platforms.** Never publish to two feeds at the same minute.
  Stagger by 5 minutes.
- **Fill gaps with story content.** Open days between shop-spotlight slots get
  adventure posts, so the cadence mixes product and story rather than reading
  as one long ad run.
- **Cross-post over creating.** When a channel has usable material, reuse it
  (same photo, repurposed caption) rather than producing new assets. This is
  what activated Threads/X at zero cost (line 76).

---

## Affiliate guardrail

Cited at `pinterest-project.md` line 131 and `social-media-project.md` line 70.

**Link to `#shop`, never to a raw `amzn.to` URL.**

Every social post points at `https://amotremba.github.io/Lucyscorner/#shop`
(Facebook and Pinterest use it directly; Instagram uses "shop link in bio").
Two reasons the trackers give:

1. **Genuine-use-case framing.** A bare product URL is an ad. A post that
   describes a real situation and links to the shop reads as content.
2. **One destination to maintain.** Change the shop grid and every existing
   post points at the new lineup automatically.

Blog posts are the exception — they link products inline where the story calls
for it, with the affiliate disclosure placed near the first product link (see
the Seasonal Shift campaign, line 47).

### Disclosure

- Blog posts: affiliate disclosure near the first product link.
- TikTok: `isBrandedContent: false` throughout — these are affiliate links, not
  a paid partnership (line 132).
- TikTok AI-scene posts: `isAiGenerated: true` per platform AI-disclosure policy
  (line 131).

---

## Platform rules

Extracted from what actually shipped. These are not inferred — each was hit in
production.

### Instagram (@aotremba2026)

- Photo or native carousel via `mediaUrls`. **No video pipeline needed** —
  Blotato posts multiple images directly as a platform-native carousel (line 93).
- Link only via "link in bio" — no clickable links in captions.
- Caption: short hook + hashtags (`#CockerSpaniel #RescueDog #DogsOfInstagram`).

### Facebook (Lucy's Corner page, `1063596216837129`)

- Direct links in caption.
- Longer, conversational captions vs Instagram (line 287).
- **Honors EXIF orientation** where Instagram ignores it — see Image handling.

### Threads (@aotremba2026) / X (@anneotremba)

- Text-first. Same photo as the source platform, caption repurposed verbatim.
- Schedule 5 min after the parent platform so feeds don't post simultaneously.

### Bluesky

- **2,000,000 byte hard limit** on images. No server-side auto-compression, so
  an oversized file just fails at publish. A failed schedule can't be updated
  — only recreated.
- Check size before scheduling: `curl -sIL <url> | grep -i content-length`.

### TikTok (amotremba, `35254`)

- Photo Mode (`mediaUrls` + music track) — stills, not rendered video.
- `autoAddMusic: true` **or posts publish silent.** This was forgotten once and
  caught pre-launch; audio is core to how photo-mode posts perform.

### Pinterest (Doggie Days board)

- 1/day, 9:00 AM CDT. Warm-up cleared 2026-08-24.
- Product photos already on the site are used directly as pin images — no
  upload step.
- Distinct fresh photo per pin (see Photo policy).

### LinkedIn — **excluded**

Deliberately not used (line 25). The plan doesn't say why; probably audience
fit. Reinstate only with a reason.

---

## Photo policy

- **One distinct fresh photo per post or pin** when unused material exists.
  This rule exists because the original 14-pin Pinterest batch was reworked from
  6 photos reused twice each into 9 distinct photos (line 265).
- **Real photos over AI renders** when a real one exists — `Lucybed.jpg` beat a
  generated scene for the Nap Bed (line 102).
- **Verify AI scenes against the real product.** Blotato's product-scene
  template substituted a Pomeranian for Lucy (line 104); packaging, brand names,
  and product variants need checking before use.
- **Flag before reusing.** If a post has to reuse an image, say so rather than
  quietly shipping it.

### Image handling

Two known bugs, both with working fixes:

**EXIF orientation.** Real phone photos from `~/Desktop/~:Pictures:Lucy:/` are
landscape with no orientation tag. `sips -r 90` rotates pixels correctly but
also stamps a stray `Orientation: 6`, so EXIF-aware consumers (Facebook) rotate
again — "fine on IG, sideways on FB." The old PNG round-trip trick no longer
works on current macOS (`sips` preserves EXIF via the `eXIf` chunk).

Patch the tag to `1` after rotating:

```bash
sips -r 90 rotated.jpg
python3 -c "
data = bytearray(open('rotated.jpg','rb').read())
pat = b'\x01\x12\x00\x03\x00\x00\x00\x01\x00'
i = data.find(pat)
data[i + len(pat)] = 1
open('fixed.jpg','wb').write(data)
"
```

**AVIF isn't reliable.** Convert `.avif` originals with
`sips -s format jpeg` before posting.

---

## Substack cross-posting

Added 2026-09-30. The original plan said nothing about Substack; this section
reflects what shipped.

### One line per post

Posts declare their Substack counterpart in front matter:

```yaml
substack: https://anneotremba.substack.com/p/your-slug
```

`_layouts/post.html` then renders an "Also on Substack" CTA on the post, and
`blog/index.html` shows a badge. Posts without the key render unchanged.

### Rules learned the hard way

- **Post, not Note.** Notes (`/note/c-...`) are short-form, ephemeral, and do
  **not** reach email subscribers. Only a `/p/` slug does. Since the goal is
  subscriber growth, the crosslink target is always a Post.
- **The composer matters.** The profile page at `substack.com/@<handle>` has a
  Create button that produces Notes. The Post composer lives under the
  *publication* at `anneotremba.substack.com/publish/posts`. Hitting publish in
  the wrong place silently produces a Note.
- **Verify the target before linking.** Copy the real `/p/` URL from the address
  bar after publishing; don't derive the slug from the filename. Publishing a
  guessed slug ships a working-looking button that 404s.
- **Link the canonical URL only.** Strip share-tracking params
  (`?r=...&utm_campaign=...`) before baking a URL into front matter.
- **No API.** Substack's official Developer API is read-only. Write access needs
  session cookies that expire, and direct publishing is slated for restriction
  in Jan 2027. Publishing is manual: write the draft, paste it, publish, then
  copy the slug.

### Publishing order for a blog post

1. Write and merge the blog post.
2. Publish it as a Substack Post (paste-ready body above).
3. Copy the `/p/` URL.
4. Add the `substack:` line, push, confirm the CTA renders.

---

## Workflow

### Standard post

1. Pick a distinct, unused photo from `~/Desktop/~:Pictures:Lucy:/`
2. Real phone photo → rotate + patch orientation; `.avif` → convert to JPEG
3. Check size against Bluesky's 2MB cap
4. Upload via Blotato `create_presigned_upload_url` + `curl -X PUT`
5. Draft a caption per platform (IG: short + hashtags; FB: longer + link)
6. `blotato_create_post`, or `update_schedule` to edit — **except** Bluesky,
   where a failed post must be recreated
7. `scheduledTime` in **UTC**
8. Confirm in the Blotato dashboard; hard-refresh (`Cmd+Shift+R`) if a preview
   looks stale

### Blog story cascade

1. Write the post to match the photo
2. Embed the photo inline
3. Cross-post IG + FB + Bluesky, same day, staggered 5 min
4. Add the `substack:` line once the Substack Post is published
5. Update the relevant tracker with the schedule IDs

---

## Tooling

| Tool | Use |
|---|---|
| `gh` CLI | Authenticated as `amotremba`. Site deploys are git pushes to `main`; GitHub Pages rebuilds automatically. |
| Blotato | Scheduling and publishing to all connected accounts |
| Canva | Design generation. Brand kit `kAGRCFnMe8s`. |

**Canva gotcha (line 60):** asking for a single slide via `generate-design`
produced a 4-page deck, one page of which hallucinated a business phone number.
Always inspect every page of an AI-generated multi-page result, and specify
"single slide, no sub-pages" explicitly.

---

## Open questions for review

These are gaps, not inferences. Your call:

1. **Is 2-day shop spotlight still the right cadence?** 10 products every 2 days
   covers each product twice a month. Now that Round 2 exists, is Round 3 warranted?
2. **How often should adventure posts run?** The trackers reference filling
   "in-between" days but never set a floor.
3. **LinkedIn — still excluded?** No reasoning recorded.
4. **Is the 5-minute stagger enough?** Consistent practice, never stated as a rule.
5. **What are the success thresholds?** No numeric target exists anywhere. Worth
   setting traffic-per-post and subscriber-growth targets so cadence changes
   can be judged.
6. **Should shop posts stop entirely if the feed reads as ads?** The guardrail
   is qualitative — "doesn't read as a straight run of ads" — with no
   enforcement rule.