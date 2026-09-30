# Substack content drafts

Copy-paste drafts for the Substack publication
(https://anneotremba.substack.com). These are **not** used by the site build —
they're reference material. Jekyll ignores any file outside `_posts`, so nothing
here affects the published site.

Set them by hand in Substack's settings. There's no write API to automate
against, and session-cookie access isn't a dependency this repo should take on.

---

## [Welcome email](substack-welcome-email-draft.md)

**Where:** Settings → Emails → *Welcome email to free subscribers* → Edit

Sends automatically when someone subscribes. It's a private email — never
visible on the publication's website — so it's the only thing a new subscriber
receives before the first post.

## [About page](substack-about-page-draft.md)

**Where:** Settings → About

Two versions (long and short). The long version also carries a note about
fixing a missing website link in the `/p/lucys-corner` post.

---

## Why these aren't automated

Substack's official Developer API is read-only — it resolves a LinkedIn handle
to public profile data and nothing else. Write access to drafts and posts
requires session cookies (`substack.sid`, `connect.sid`) that expire, and
direct publishing via those cookies is slated for restriction in **January
2027**.

Not worth a credential dependency for three static blocks of text.

## Gotchas learned 2026-09-30

- **The profile Create button makes Notes, not Posts.** Notes live at
  `/note/c-...`, are short-form and ephemeral, and **do not reach email
  subscribers**. The Post composer is under the *publication*:
  `anneotremba.substack.com/publish/posts`.
- **Only a `/p/` slug is a real link target.** This is what the blog's
  `substack:` front matter should always point at — see the growth plan's
  Substack cross-posting section.
- **Copy the URL from the address bar after publishing.** Don't derive the slug
  from the post filename; Substack often shortens or rewords it.