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
| Bluesky / LinkedIn / Threads / TikTok / Twitter | connected, unused so far | potential future channels |

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
