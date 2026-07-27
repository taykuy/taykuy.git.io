# How to publish The Hungry Squirrel site

This is the runbook for updating the live site. It exists so any Cowork chat
(or future you) can publish without re-discovering how things fit together.

## The facts

- **GitHub repo:** https://github.com/taykuy/taykuy.git.io  (public)
- **Hosting:** GitHub Pages, built automatically from the **`main`** branch.
- **Live site base:** https://taykuy.github.io/taykuy.git.io/
- **Local canonical copy (Taylor's computer):** `~/Downloads/hungry-squirrel-site/`

## The pages

| Repo file            | What it is                        | Live URL                                                        | Source in the skill      |
|----------------------|-----------------------------------|----------------------------------------------------------------|--------------------------|
| `hungrysquirrel.html`| Private meal plan (rotation, shopping list, dish notes) | https://taykuy.github.io/taykuy.git.io/hungrysquirrel.html | the skill's `meal-plan.html`   |
| `HungryMenu.html`    | Guest-facing menu                 | https://taykuy.github.io/taykuy.git.io/HungryMenu.html         | the skill's `dinner-menu.html` |
| `index.html`         | Landing page                      | https://taykuy.github.io/taykuy.git.io/                        | (edit directly)          |

> **Filename mapping matters.** The meal-plan skill names its outputs
> `meal-plan.html` and `dinner-menu.html`. In this repo they are
> `hungrysquirrel.html` and `HungryMenu.html`. **Rename on publish** — upload
> with the repo's filenames or you'll create duplicate pages instead of
> updating the live ones.

## How to publish (from a Cowork chat)

The Cowork cloud sandbox has **no git push credentials** — `git push` from the
sandbox fails. Publish through the user's browser, where they're already signed
in to GitHub. (This is how the last several updates were made.)

1. **Get the latest page HTML** — from the meal-plan skill's output, or a file
   the user attaches.
2. **Save it to the computer** at `~/Downloads/hungry-squirrel-site/`, using the
   **repo filenames** (`hungrysquirrel.html`, `HungryMenu.html`). This keeps a
   canonical local copy.
3. **Upload to GitHub via the logged-in browser** (Claude in Chrome):
   - Open **https://github.com/taykuy/taykuy.git.io/upload/main**
   - Add the file(s) via the upload drop zone — **same filenames replace the
     live files**.
   - Type a commit message, keep **"Commit directly to the `main` branch"**
     selected, and click **Commit changes**.
4. **Verify:**
   - The repo home should show your new commit at the top.
   - After ~1 minute, reload the live URL(s) above and confirm the change
     (the plan's "Tonight" highlight tracks the current date via `PLAN_START`).

## Notes

- Only change `hungrysquirrel.html` / `HungryMenu.html` when the plan changes;
  leave `index.html` alone unless you're updating the landing page.
- The pages are self-contained HTML (inline CSS/JS, Google Fonts from CDN). No
  build step — whatever is committed is what's served.
- If a future chat can't find this repo: it's the only HTML repo under the
  **taykuy** GitHub account, and "claude" is a listed contributor.

_Last updated by a Cowork session on 2026-07-27._
