# pebbles-legal

Public legal documents for the Pebbles pilot. Static HTML, no build step, no
dependencies. Deployed by Cloudflare Pages to **legal.withpebbles.com**.

| File | Live at |
|---|---|
| `index.html` | `https://legal.withpebbles.com/` |
| `privacy.html` | `https://legal.withpebbles.com/privacy` |
| `terms.html` | `https://legal.withpebbles.com/terms` |
| `style.css` | shared styles for all pages |

Cloudflare Pages serves `privacy.html` at `/privacy` automatically, so the app
and App Store Connect can use the clean URLs above.

## Updating a document

```bash
# edit privacy.html or terms.html
git add -A
git commit -m "Privacy policy: <what changed and why>"
git push
```

Live in roughly 30 seconds. **No app release is required** — the app links to the
URL and opens it in a browser, so the content behind the URL can change freely.

Change the `Last updated` date at the top of any document you edit. Both
documents promise readers that this date reflects the last modification.

## Why this is a git repo rather than drag-and-drop uploads

Because `git log` is a dated record of what these documents said and when. If a
participant asks in November what the policy said when they joined in August,
that question has an exact answer. Direct uploads to Cloudflare overwrite and
forget. For a document whose entire job is recording what was promised, the
history is the point — so **write real commit messages**, not "update".

## Before going live

- [ ] Counsel's redline incorporated
- [ ] Remove the `<div class="draft">` block from **all three** pages, and the
      `.draft` rule from `style.css`
- [ ] Only then: link from the app's About screen and add the URL to App Store
      Connect

Until the draft banners are removed, do not point the app or App Store Connect
at these pages.

## Not in this repo

The source `.docx` files and the note to counsel live in
`IDEA Lab/Legal/Initial Web App Pilot/`. This repo is public; that folder is not.
Keep drafting there and publish here.
