# Lucy's Corner — Social Media Growth Project

Tracks the Instagram + Facebook posting workflow for driving traffic to Lucy's Corner (goal: grow an audience for the affiliate Shop links + Substack). Pinterest has its own tracker in [`pinterest-project.md`](pinterest-project.md) — warm-up cleared 2026-08-24, now posting via Blotato. The overall recurring content plan (all platforms, affiliate strategy) is in [`social-media-growth-plan.md`](social-media-growth-plan.md).

**Site:** https://amotremba.github.io/Lucyscorner/

---

## Tools connected

- **GitHub CLI (`gh`)** — installed via Homebrew, authenticated as `amotremba`
- **Blotato** — scheduling/publishing to connected social accounts (starter plan)
- **Canva** — design generation (1 brand kit connected, not yet used for a finalized post)

## Connected Blotato accounts

| Platform | Account | Notes |
|---|---|---|
| Instagram | @aotremba2026 | used for Lucy's Corner posts |
| Facebook | Anne Otremba → **Lucy's Corner** page (pageId `1063596216837129`) | already branded |
| Pinterest | anne8133 → **Doggie Days** board | ✅ warm-up cleared 2026-08-24 — now posting via Blotato. See `pinterest-project.md`. |
| Pinterest | anneotremba | no dog-specific board yet |
| Threads | @aotremba2026 | now active — see "Shop Spotlight Cross-post Round" below |
| Twitter/X | @anneotremba | now active — see "Shop Spotlight Cross-post Round" below |
| Bluesky / LinkedIn / TikTok | connected, unused beyond Bluesky's shop batch | LinkedIn excluded per growth plan; TikTok needs a video pipeline |

---

## "Seasonal Shift" Campaign — Summer-to-Fall Allergy/Skin Care (in progress, not yet drafted)

New campaign per Anne's brief (2026-09-18): educates on transitioning dog skin/allergy care from summer to fall, with a "Transition Kit" of 3 affiliate products. Instagram carousel (6 slides) + GitHub blog post, CTA to the kit.

**Photos ready** (both real, both needed the standard rotation-fix/compression treatment — see "Known issues" below):
- Summer half of the split-screen: `Lucysummer.jpg` — rotated, compressed 3.75MB → 1.2MB. Hosted: `https://database.blotato.io/storage/v1/object/public/public_media/d5e38952-0dea-42ba-9c4c-201c796234b9/96d0ea7c-121e-4ed2-9b73-094588de52cb.jpg`
- Fall half / "Fall Shift" slide: `lucyinleaves.png` — compressed 2.5MB → 0.9MB (PNG→JPEG). Hosted: `https://database.blotato.io/storage/v1/object/public/public_media/d5e38952-0dea-42ba-9c4c-201c796234b9/bd4a7c9d-1923-48c1-9115-e30493098e28.jpg`

**Transition Kit products — all 3 fully confirmed (photo + link matching):**
1. Summer Protector: **K9 Advantix II, Large Dog (21-55 lbs)** — link https://amzn.to/4rjnp0L, photo `k9advantixii.jpg`. (First link/photo pair Anne sent were both the Extra Large 55+ lbs variant — wrong size for a Cocker Spaniel; caught via WebFetch redirect check before drafting, Anne corrected both.)
2. Fall Hydrator: **Burt's Bees for Dogs Oatmeal Shampoo** — link https://amzn.to/4iVIcFB, photo `burtsbeesshampoo.jpg`.
3. Internal Shield: **Zesty Paws Wild Alaskan Omega-3 (Pollock + Salmon Oil)** — link https://amzn.to/3TCnOyQ, photo `zestypawsomega3.jpg`.

All 3 photos: converted from Anne's `.avif` originals via `sips -s format jpeg` (AVIF isn't reliably supported across social platforms), live in repo root, and hosted on Blotato:
- Advantix: `https://database.blotato.io/storage/v1/object/public/public_media/d5e38952-0dea-42ba-9c4c-201c796234b9/226bc745-7dd1-4ad7-933a-7caeb4f41fc4.jpg`
- Burt's Bees: `https://database.blotato.io/storage/v1/object/public/public_media/d5e38952-0dea-42ba-9c4c-201c796234b9/7c1e3be4-2783-4879-9693-d386cd249aa0.jpg`
- Zesty Paws: `https://database.blotato.io/storage/v1/object/public/public_media/d5e38952-0dea-42ba-9c4c-201c796234b9/46d792bc-bfc4-4006-b42c-3dd0e9b8a9b5.jpg`

**Blog post drafted:** `_drafts/the-summer-to-fall-itch.md` (Jekyll draft — not live, not committed to `_posts/`). Follows the blueprint voice/template, includes the required affiliate disclosure near the first product link, all 3 products linked.

**Status:** everything drafted and ready for Anne's review. Nothing published, committed, or scheduled yet — carousel copy delivered in-chat for review alongside the blog draft.

## Shop Spotlight Batch — Sept 2026 (scheduled)

10 products from the shop, one IG + FB + Bluesky post each, every 2 days 2026-09-12 → 2026-09-30 (interleaved with the Pinterest daily shop-pin queue in `pinterest-project.md`) so the feed doesn't read as a straight run of ads, per the growth plan's guardrail. Each product photo already lives on the site (`dogbed.jpg`, `leash.jpg`, `moongemlick.jpg`, `doggroomingkit.jpg`, `caninecarryouts.jpg`, `buddysofties.jpg`, `bullysticks.jpg`, `biokleen.jpg`, `furryfreshness.jpg`, `dogcrate.jpg`), used directly — no re-upload needed. All link to `#shop` (FB: direct link; IG: "shop link in bio"; Bluesky: direct link).

Schedule: 2026-09-12 (Nap Bed), 09-14 (Leash), 09-16 (Lick Pad), 09-18 (Grooming Kit), 09-20 (Canine Carry Outs), 09-22 (Buddy Softies), 09-24 (Bully Sticks), 09-26 (Bac-Out Cleaner), 09-28 (Furry Freshness), 09-30 (Travel Crate) — all 10:00 AM CDT.

## Shop Spotlight — Threads/X Cross-post Round (scheduled)

Per the growth plan's cadence #4 (weekly light cross-post), repurposed each shop-spotlight product's Bluesky caption verbatim into a Threads + X (Twitter) post, same photo, no new material needed. Threads/X had been "connected, unused" — this activates them. Same product order/images as the Bluesky batch above; scheduled 5 min after each product's Bluesky slot (10:05 AM CDT) so feeds don't post at the exact same minute across platforms.

| Product | Date | Threads submission ID | X submission ID |
|---|---|---|---|
| The Nap Bed | 2026-09-13 (posted now — original date already passed) | published — https://www.threads.com/@aotremba2026/post/DdQB1K2oJIe | published — https://x.com/anneotremba/status/2099319560805535812 |
| Retractable Leash | 2026-09-14 | `b37dfccc-a8bf-4d0e-8476-f902d046d1ff` | `1f4ad2bf-5e29-40d2-957d-a0b0a5325370` |
| Dog Lick Pad | 2026-09-16 | `7bd649ec-1144-4f20-b68e-20d6e8e7d61f` | `ef56d0a9-9434-4e08-9d0f-d480b201a08f` |
| Grooming Kit | 2026-09-18 | `b736514d-f9e3-4b2c-a315-21dc5be666f2` | `23b5ebaa-90fa-4d56-9486-aca4234f41fa` |
| Canine Carry Outs | 2026-09-20 | `d77df5d9-9843-4c6c-8cb9-dd467c0060b7` | `809f11b9-d74b-4c7f-a5b5-d906bf980edc` |
| Buddy Softies | 2026-09-22 | `5e59e560-d645-43c5-82b1-e3f8d49bb317` | `d4f6051d-cb36-4fc1-82c7-bac700f1283f` |
| Bully Sticks | 2026-09-24 | `ec09a87c-c839-45de-9ccb-f380479d825e` | `b8419848-66dc-45c3-aa3e-a346a2f8cfa0` |
| Bac-Out Cleaner | 2026-09-26 | `e47dc1a8-4fab-451b-86fe-8c99a8033cc5` | `e21a583b-ef84-4d14-9d21-d2c3f7386591` |
| Furry Freshness | 2026-09-28 | `5531d506-5f01-41df-9150-96161fcf5007` | `eb554101-7f3a-4bde-8189-fa4b443ba2d9` |
| Folding Travel Crate | 2026-09-30 | `188af727-7843-4407-b6ef-80124369853e` | `c5816f87-f832-4dc3-bcfc-09f5dc269501` |

## Shop Round-up Carousel — "Lucy's Favorite Things" (scheduled)

Native IG/FB carousel featuring all 10 shop products in one swipeable post (not a rendered video — Blotato posts multiple `mediaUrls` directly as a platform-native carousel), using the same photos already hosted from the shop-spotlight batch. Fills one of the still-open "in-between" days between shop-spotlight posts.

- **Scheduled:** 2026-09-19, 10:00 AM CDT — Instagram `f9942de5-a048-4026-b029-068acf1187a7`, Facebook `e3ccbc60-05e7-4e98-8395-de892b0700f2`
- **Links to:** `#shop` (IG: link in bio; FB: direct link in caption)

## Shop Spotlight Round 2 (scheduled, 6 platforms × 4 products)

Second round on 4 of the 10 shop products, spaced every 2 days starting after Round 1 ends, across IG+FB+Bluesky+Threads+X+Pinterest (Threads/X 5 min after IG/FB, Pinterest at 9:00 AM CDT matching Round 1's pattern).

**Nap Bed uses a real photo, not AI** — Anne added `Lucybed.jpg` (Lucy actually on the bed) to the phone-photo folder mid-session. Applied the standard rotation fix (`sips -r 90` + patch EXIF Orientation byte to 1, per the "Known issue" section below) and used it directly — better and more authentic than any AI render.

**Leash, Grooming Kit, and Travel Crate use Blotato's "Product Scene Placement" AI visual template** (product photo + generated lifestyle scene). First attempt also generated a Nap Bed scene, but it substituted a Pomeranian for Lucy — dropped in favor of the real photo above. Leash brand (Flexi) confirmed correct by Anne; Grooming Kit ("onesall") and Travel Crate ("amazon basics" text visible) checked against the real product photos and match, just a different color/angle than the box shot.

| Product | Image source | Scheduled | IG | FB | Bluesky | Threads | X | Pinterest |
|---|---|---|---|---|---|---|---|---|
| The Nap Bed | Real photo (`Lucybed.jpg`, rotation-fixed) | 2026-10-02 | `12fb626d-a119-4001-808d-def548acc54a` | `ccd0d44e-899e-4dfd-a7cc-5f6724241667` | `7eaa4d90-2497-43d2-b09f-f431d1ee5f5f` | `cec228fe-5917-4730-b4f1-37357bbae74b` | `0e3d739d-761b-486c-a853-89bcacb473cc` | `3335894e-f1d4-46d1-9944-ad5baf609122` |
| Retractable Leash | AI scene (entryway, hiking boots) | 2026-10-04 | `cbeee1d8-cd26-47f9-998c-7e15b356047a` | `c888e66e-a701-4117-8ea5-40de3a6df6ae` | `d41b00df-1d7d-4c16-8438-54bc9c13119b` | `c2cf50aa-9fb4-4e27-a22d-8fa3abe65bb1` | `3591f2ee-1e8a-4425-9a8a-02c20b24bff0` | `61b49189-b71f-4eae-b8c5-2e1829839426` |
| Grooming Kit | AI scene (wood table, wildflowers) | 2026-10-06 | `cf28b4a3-bbcf-48eb-91bd-a38593cf0d94` | `cadc46e4-07f2-4749-bd8f-b378ad51b9af` | `8352b447-ef27-4d56-b0ed-30ea0cc60125` | `892dd350-d742-4aab-bf17-4244c98ce478` | `f67f443d-057f-4f43-8783-e500883ac6f5` | `e1f3cd44-dd04-43a4-b046-e490e7beb548` |
| Folding Travel Crate | AI scene (car trunk, road trip) | 2026-10-08 | `ae30208b-4e53-4ba8-99b6-57086be0b41e` | `5f0dbc1d-74d2-4f48-8795-361aaaba3c82` | `d75bec6b-e51e-4b31-8cc2-e834365bf28e` | `d0e0d19f-716e-44c0-a497-2def6e3ee90b` | `064130e5-ac33-4726-8669-0f0de4d94d49` | `71ea5b44-0371-40aa-82ff-bdc01ddc27b9` |

Remaining 6 products now also in Round 2 (see table below) — all 10 shop products have a Round 2 batch.

| Product | Image source | Scheduled | IG | FB | Bluesky | Threads | X | Pinterest |
|---|---|---|---|---|---|---|---|---|
| Dog Lick Pad | AI scene (sunroom, dog bed cushion) — checked against real photo, matches (red/blue mats, spatula) | 2026-10-10 | `f1e0aecf-d0d2-447d-a7c6-5aed38535045` | `a88c3b41-6489-4135-8464-fa839696ddeb` | `01c09fc9-652f-4ab0-a5ef-8ba9eae0e0ff` | `5c7dc61e-0e81-46e2-a812-5d57d1d3c3b2` | `d0298e23-e2be-4c43-8c94-f9333a5547ca` | `da5033c0-9cc5-4da1-93a1-ff88bb40611d` |
| Canine Carry Outs (Beef) | AI scene (entryway bench, leash, trail shoes) — packaging matches real product | 2026-10-12 | `5c81251a-fff3-40b2-a178-e4eb8046cf47` | `4e1e53c1-2752-448c-951e-bd310469ec00` | `aa42a23c-11bb-4a3b-9051-b856e300c5e4` | `48a5b84e-459a-4736-aa45-0e2142df4f22` | `f256be9d-6bda-4f7a-8ea4-72924856b49e` | `f590a097-d966-4a1f-96da-f89454819d7f` |
| Buddy Softies (Bacon & Cheese) | AI scene (kitchen counter, treat jar) — packaging matches real product | 2026-10-14 | `5f4c18a4-7bec-485c-a3fa-bcd077e84a7c` | `c2190490-04f0-4cf3-afb8-27065dce6f7b` | `b03bf353-5256-4411-94a5-e2f96a1d770b` | `c6ff7da2-5a15-4f65-b374-878cd2844c61` | `645965f6-35d7-4d05-be91-769e1bfebbc4` | `5a12e9a6-855f-4ea8-8d4f-cf8890b8b1d3` |
| Bully Sticks (Party Pack) | AI scene (coffee table, dog bed) — Redbarn packaging matches real product | 2026-10-16 | `40e34eaa-2a87-45d2-9de6-faffebaaf3ae` | `5273ce6e-0d17-4f39-9d18-6937c8f986be` | `ddfe1907-1ff7-4f9a-920f-a0bf5b5acf0e` | `f6018726-ee70-4db2-83cd-5c62355a1e76` | `b11cf083-ef67-40f9-bca5-80dd9a9fe258` | `3289ee99-6095-4659-82fe-6a2a2c9ef1f9` |
| Bac-Out Enzyme Cleaner | AI scene (laundry room shelf, towels) — Biokleen packaging matches real product | 2026-10-18 | `a188d65a-3ce6-4708-8eeb-20d6b373c29c` | `45688170-3c94-4f67-866c-e1e455da2e54` | `e6dd16f3-ec09-4530-a9fa-48ecf8a3e778` | `ef234c33-5a23-46db-9151-a851b3c87b6e` | `6796f380-0b34-4bb3-901c-85bbf2b09a80` | `fc9a34e4-b978-4d56-a387-882bc090c54d` |
| Furry Freshness Spray | AI scene (bathroom counter, towel) — packaging matches real product | 2026-10-20 | `01d5a7ab-5fde-4271-a5fe-7ed09a6cd987` | `f51e7990-70ff-441f-b600-40508cc96fe0` | `42176f74-ed3c-4ba7-ab53-2c28388bff83` | `50129682-f3d1-46c9-b777-d3b947742a92` | `a74b2d4b-58bf-4786-b881-7a53821f328e` | `269701eb-33b6-4722-a430-ef83ce834e65` |

All 10 shop products now have a complete Round 2 (IG+FB+Bluesky+Threads+X+Pinterest), running 2026-10-02 → 2026-10-20, every 2 days.

## TikTok (scheduled, photo mode)

Added TikTok (amotremba, accountId `35254`) as a 7th shop-post channel — new platform, first posts. TikTok's Content Posting API supports "Photo Mode" (swipeable still images with a music track, not a rendered video), so the same product photos/AI scenes work directly via `mediaUrls`, no video pipeline needed after all — updates the growth plan's earlier note that TikTok was blocked on that.

11 posts scheduled 2026-09-19 → 2026-10-20 (round-up + all 10 Round 2 products, 5 min after the X/Twitter slot each day). Two settings matter for TikTok specifically:
- `isAiGenerated: true` on the 9 AI-scene-placement posts (per TikTok's AI-content disclosure policy) — `false` on the round-up (real photos) and the real Nap Bed photo.
- `isBrandedContent: false` throughout — affiliate links, not a paid partnership.
- `autoAddMusic: true` — initially forgotten (all 11 posted without it), caught before anything went live and fixed via `blotato_update_schedule` on all 11. Without it, TikTok photo posts publish silent, which undercuts them since the audio track is core to how they perform. Worth remembering for any future TikTok photo-mode posts.

Schedule IDs: round-up `4425649` (09-19) · Nap Bed `4425625` (10-02) · Leash `4425653` (10-04) · Grooming Kit `4425654` (10-06) · Crate `4425661` (10-08) · Lick Pad `4425667` (10-10) · Carry Outs `4425670` (10-12) · Buddy Softies `4425674` (10-14) · Bully Sticks `4425678` (10-16) · Bac-Out `4425683` (10-18) · Furry Freshness `4425687` (10-20).

## Adventure Post — "Meeting the Collie Mix at the Cabin" (scheduled)

- **Photo:** `lucymeetscolliemix.jpg` — Lucy nose-to-nose with a 6-month-old collie mix puppy, already noticeably bigger than her, met at the cabin. Fresh photo, added 2026-09-11.
- **Blog post:** [`_posts/2026-09-11-meeting-the-collie-mix-at-the-cabin.md`](https://amotremba.github.io/Lucyscorner/blog/2026/09/11/meeting-the-collie-mix-at-the-cabin/) — written to match the photo, photo embedded inline
- **Scheduled:** IG + FB + Bluesky, 2026-09-13, 10:00 AM CDT (fills an "in-between" day in the shop spotlight cadence, per the user's request)
- **Blotato schedule IDs:** Instagram `4364958` · Facebook `4364960` (links to the story) · Bluesky `4364961` (links to the story)

## Adventure Post — "The Creek at the Cabin" (scheduled, 2 photos)

- **Photos:** `lucybythecreek.jpg` (front-facing, damp, second-guessing the water) and `lucycreek2.jpg` (side profile, studying the creek warily) — same outing, both fresh, added 2026-09-11.
- **Blog post:** [`_posts/2026-09-11-the-creek-at-the-cabin.md`](https://amotremba.github.io/Lucyscorner/blog/2026/09/11/the-creek-at-the-cabin/) — both photos embedded inline, ties into her established "trails over swimming" personality
- **Scheduled:** IG + FB + Bluesky ×2 (one post per photo), 2026-09-15 and 2026-09-17, 10:00 AM CDT
- **Blotato schedule IDs:** 09-15 — Instagram `4365248` · Facebook `4365254` (links to the story) · Bluesky `4365256` (links to the story). 09-17 — Instagram `4365259` · Facebook `4365262` (links to the story) · Bluesky `4365265` (links to the story)

Two adventure photos filled 3 of the 9 "in-between" days. Still open: 09-19, 09-21, 09-23, 09-25, 09-27, 09-29 — add more real Lucy moments/photos here as they come up to fill them.

---

## Post #3 — "The New Pup Across the Street" (DRAFT — not yet scheduled)

- **Photo:** TBD — Anne is adding new photos for this one. Unused-photo pool was otherwise empty (only off-theme `20260618_190037.jpg` left), so this cascade is holding for fresh material rather than reusing.
- **Links to:** https://amotremba.github.io/Lucyscorner/blog/2026/09/01/the-new-pup-across-the-street/

**Instagram caption:**
> Lucy just found out the house across the street has a new resident: one (1) extremely young puppy with zero self-preservation instincts. 🐶👀 Verdict pending. More at the link in bio.
>
> #CockerSpaniel #RescueDog #DogsOfInstagram

**Facebook caption:**
> Lucy spotted the new neighbor through the window before we even knew there was one to see — a wobbly puppy about a third her size, already losing a fight with a leaf. First official meeting happened on today's walk, and it went... better than expected? Read the full introduction on Lucy's Corner 🐾
>
> (link: https://amotremba.github.io/Lucyscorner/blog/2026/09/01/the-new-pup-across-the-street/)

**Pinterest story pin:**
> Title: "The New Pup Across the Street"
> Text: A new puppy moved in across the street, and Lucy has Opinions. Read the full first-meeting report on Lucy's Corner.

**Pinterest quote pin:**
> Title: "Threat level: reconsidered"
> Text: "Threat level after seeing it fall over a leaf: significantly reduced." — Lucy's Corner, on meeting the new puppy next door.

**Bluesky cross-post (new platform for the cascade, per growth plan's cross-post cadence — text-only, no photo needed):**
> Lucy assessed the new puppy across the street as a high threat... right up until it fell over a leaf. Full report on Lucy's Corner: https://amotremba.github.io/Lucyscorner/blog/2026/09/01/the-new-pup-across-the-street/

---

## Post #2 — "The Staring Contest With a Deer" (scheduled)

- **Photo:** `lucy running from deer.png` (AI illustration, `Photos-1-001/`) for IG/FB and the Pinterest quote pin; `lucy chasing deer.png` for the Pinterest story pin — these were the only two unused deer-themed assets, so the quote pin reuses the IG/FB photo per the user's call (flagged first, per the fresh-photo rule).
- **Scheduled:** IG/FB 2026-09-01 1:00 AM CDT (06:00 UTC); Pinterest story pin 2026-09-02, quote pin 2026-09-04 (see `pinterest-project.md` rows 15–16)
- **Blotato IDs:** Instagram `f772bb0c-cc53-45da-8706-c0c4818e0c50` · Facebook `e25e14c6-f9eb-4d02-9bed-f8cc6e966f5c`
- **Links to:** https://amotremba.github.io/Lucyscorner/blog/2026/08/31/the-staring-contest-with-a-deer/

---

## Post #1 — "Neighborhood Watch" (scheduled)

- **Photo:** `20260814_141112.jpg` from `~/Desktop/~:Pictures:Lucy:/` — Lucy sitting in tall grass, side profile. Needed a 90° rotation fix (see below).
- **Scheduled:** 2026-08-20, 1:00 AM CDT (06:00 UTC)
- **Blotato schedule IDs:** Instagram `3621181` · Facebook `3621198`

**Instagram caption:**
> Undercover investigation: is the mailman a squirrel in disguise? Lucy is on the case. 🕵️‍♀️🐾
>
> From timid rescue to full-time neighborhood watch captain — more of Lucy's story at the link in bio.
>
> #CockerSpaniel #RescueDog #DogsOfInstagram

**Facebook caption:**
> Caught mid-investigation 🕵️‍♀️ Lucy takes her job as neighborhood watch very seriously — squirrels, mail carriers, and suspicious leaves are all under surveillance.
>
> Come read more about her journey from timid rescue to full of opinions on Lucy's Corner 🐾
>
> (link: https://amotremba.github.io/Lucyscorner/)

---

## Known issue: Bluesky 2MB image limit

**Found 2026-09-15:** Bluesky hard-rejects any image over 2,000,000 bytes (`blob too big` error) — unlike other platforms via Blotato, there's no server-side auto-compression for it, so an oversized file just fails at publish time.

- The 09-15 "Creek at the Cabin" Bluesky post failed live (`lucybythecreek.jpg`, 2,029,029 bytes — literally 29KB over). Recreated with a compressed version (`sips -Z 2000 -s formatOptions 82`, down to ~1.2MB) since a failed schedule can't be re-updated, only recreated as a new post.
- The Round 2 Nap Bed photo (`Lucybed.jpg`, rotation-fixed) was 2.6MB — caught before it fired and fixed the same way, swapped across all 7 platforms using it (not just Bluesky, for consistency).
- Audited all other scheduled Bluesky posts same day: every AI-scene render and Round 1 site photo is well under the cap (largest was 210KB); only these two real phone photos were oversized.
- **Takeaway:** any real phone photo (not a AI-render or web-optimized site image) needs a size check before use in a Bluesky post — `curl -sIL <url> | grep -i content-length`, or check the local file size before upload. Target well under 2MB (e.g. `sips -Z 2000 -s formatOptions 82`) to leave margin.

## Known issue: photo rotation/orientation bug

- Real phone photos in `~/Desktop/~:Pictures:Lucy:/` are landscape with **no EXIF orientation tag**, so they need a manual 90° rotation (`sips -r 90`) to display upright.
- **Root cause (found 2026-08-24):** `sips -r 90` physically rotates the pixel data (width/height swap in the output) *but also stamps a stray EXIF `Orientation` tag* (e.g. `6`) on top, telling any EXIF-aware consumer to rotate it *again*. Instagram's Blotato pipeline appears to ignore EXIF orientation (so it looked fine there), but Facebook's honors it — hence "fine on IG, sideways on FB."
- The old "round-trip through PNG to strip metadata" trick **no longer works** on current macOS — `sips` now preserves EXIF through PNG via the `eXIf` chunk, so the orientation tag survives the round-trip instead of being stripped.
- **Fix that actually works:** after rotating, patch the EXIF Orientation value directly to `1` (normal) instead of relying on format round-tripping. The pixels are already correctly rotated by `sips -r 90`, so the tag just needs to stop telling viewers to rotate again:
  ```bash
  python3 -c "
  data = bytearray(open('rotated.jpg','rb').read())
  pat = b'\x01\x12\x00\x03\x00\x00\x00\x01\x00'
  i = data.find(pat)
  data[i + len(pat)] = 1   # set Orientation = 1 (normal)
  open('fixed.jpg','wb').write(data)
  "
  ```
- Verify before uploading: `python3 -c "d=open('fixed.jpg','rb').read(); i=d.find(b'\x01\x12\x00\x03'); print(d[i:i+12])"` — last two bytes of the printed tag should be `\x00\x01` (orientation 1), not `\x00\x06`.
- **Takeaway:** always check/patch the Orientation tag (not just re-encode) before posting real phone photos via Blotato, especially for Facebook.

---

## Photo library

Local folder: `~/Desktop/~:Pictures:Lucy:/` (syncs to `~/Library/Mobile Documents/com~apple~CloudDocs/~:Pictures:Lucy:/`)

- Real phone photos — check orientation before use (see rotation fix above). All of the ones below are landscape with no orientation tag and need the fix.
- Two branded AI illustrations already matching the site's Adventures-section art style: `lucy chasing butterfly.png`, `lucy dipping paw in water.png` — good candidates for Pinterest since they're already vertical and polished. **`lucy dipping paw in water.png` is a better match for the Lake Day pins than the generic grass photo currently used — worth swapping in.**

### Cataloged 2026-08-24

| File | Shows | Best fit |
|---|---|---|
| `20260814_141112.jpg` | Lucy in tall grass, side profile | Already used — "Neighborhood Watch" IG/FB post (scheduled 2026-08-20) |
| `20260706_121853.jpg` | Duplicate of `Stalkermode.jpg` | Already used — cat-next-door IG/FB/Pinterest content |
| `20260618_185934.jpg` | Close portrait by the fireplace, cozy indoor | "Lucy at Home" pillar |
| `20260618_190037.jpg` | Playful upside-down-ish pose on the couch, ball nearby | "Lucy at Home" pillar / funny photo-led post |
| `20260625_110222.jpg` | Close portrait in the car, road-trip light | "Adventures" pillar — car ride / road trip moment |
| `20260629_151750.jpg` | Cozy portrait on a bed with a pink blanket | "Lucy at Home" pillar / naptime |
| `20260730_191627.jpg` | Close portrait on a paved trail next to grass | "Adventures" pillar — trail walk |
| `20260730_191747.jpg` | Action shot from behind/side in grass | "Adventures" pillar — supporting shot |
| `20260730_191921.jpg` | Playful crouch in dry grass field | "Adventures" / wildlife-watch style post |
| `20260814_141153.jpg` | Playful crouch in dry grass, same walk as above | "Adventures" — alternate angle |

**Rule (2026-08-24 onward): use a distinct, fresh photo per post/pin — avoid repeating the same image across multiple posts when unused material exists.** This is why the Pinterest 14-pin batch was reworked to use 9 distinct new photos instead of 6 photos reused twice each — see `pinterest-project.md`.

**Used 2026-08-24:** `20260618_185934.jpg`, `20260625_110222.jpg`, `20260629_151750.jpg`, `20260730_191627.jpg`, `20260730_191747.jpg`, `20260730_191921.jpg`, `20260814_141153.jpg`, `lucy chasing butterfly.png`, `lucy dipping paw in water.png` — all now in the Pinterest queue (see `pinterest-project.md`).

**Still unused and available** for the next story cascade, monthly affiliate spotlight, or a standalone photo-led post per the [growth plan](social-media-growth-plan.md): `20260618_190037.jpg` (playful upside-down pose on the couch — only one left from this batch).

**Used 2026-08-31:** `lucy running from deer.png`, `lucy chasing deer.png` (both AI illustrations from `Photos-1-001/`) — the deer-themed illustration pool is now exhausted; the next deer/wildlife story will need new photos or artwork.

**Used 2026-09-13:** `Lucybed.jpg` (Anne added it mid-session) — real photo of Lucy on the actual Nap Bed product, landscape/no-orientation-tag like the others, rotation-fixed and used for the Shop Spotlight Round 2 Nap Bed post (see above).

## Draft Canva candidates (not finalized/used yet)

- IG quote card ("From timid to full of opinions"): https://www.canva.com/d/Si5Z_yqqtIbSnzQ
- Pinterest pin ("Meet Lucy: A Rescue Dog's Adventures"): https://www.canva.com/d/G04U3hJRDBdDtfO

---

## Workflow for future posts

1. Pick photo(s) from `~/Desktop/~:Pictures:Lucy:/`
2. If it's a real phone photo, verify it's upright; if not, rotate + run the clean re-encode (PNG round-trip) before uploading
3. Upload via Blotato `create_presigned_upload_url` + `curl -X PUT`
4. Draft a caption per platform (Instagram: short + hashtags; Facebook: longer, conversational, include link)
5. `blotato_create_post` (or `update_schedule` if editing an existing one) with `scheduledTime` in UTC
6. Confirm in the Blotato dashboard — hard refresh (`Cmd+Shift+R`) if a preview looks stale after an edit

## Next steps / ideas

- Once the Pinterest account clears warm-up, resume posting to the **Doggie Days** board (use `pinterest-project.md` for the manual posting calendar)
- Consider finishing one of the Canva graphic drafts above as an alternate content type alongside real photos
- Expand to Threads/Bluesky/Twitter once Instagram + Facebook cadence is established
