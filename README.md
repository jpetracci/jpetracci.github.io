# jpetracci.github.io

Personal website — Arik and Anna are here too!

A static personal and family site with writing, art, music, and browser-game
exports. Hosting family work here does not make Joel the sole author of every
page or game.

## Structure and authorship

- Root pages and `about/`, `contact/`, `projects/`, and `resume/`: Joel's site
  sections, with front matter/Liquid and a shared `_layouts/default.html`.
- `anna/`: Anna's writing, book pages, and Traveler's Guide material.
- `arik/`: Arik's art, music, and games, including Unity and Godot web exports.
- `arik/games/index.html`: the game catalog and its authorship/tutorial notes.
  Block Dodge follows [this tutorial](https://www.youtube.com/playlist?list=PLPV2KyIb3jR53Jce9hP7G5xC4O9AgnOuL);
  Tower Defense is also tutorial-based. The catalog describes Gold Rush and
  Don't Fall as Arik's independent work, with Don't Fall made in Godot rather
  than Unity. Preserve those distinctions when updating the site.

## Editing and preview

Edit the relevant section's HTML and keep relative asset paths and export
folders together. Changes to the shared layout affect pages that select it in
front matter; some game/catalog pages are standalone HTML instead.

A raw static preview can be served from the repository root:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open http://127.0.0.1:8000/. This serves files only: it does **not** render
Liquid/front matter or apply Jekyll layouts. A full-site preview needs a
GitHub Pages-compatible Jekyll environment, but this snapshot does not pin one
with a Gemfile. Browser-game exports may have engine-specific browser/hosting
requirements; serving their files is not evidence that they run correctly.

## Publishing caveats

The intended public site is [petracci.org](http://www.petracci.org/). Verify the
repository's actual GitHub Pages source and domain settings before publishing;
the repository name alone does not establish the current deployment path.

The checked-in `.github/workflows/main.yml` is a separate Godot **3.3.3** HTML5
export workflow, triggered for `main` and configured to deploy `build/web` to
`main`. The reviewed default branch is `master`, and the tree contains exported
games but no `project.godot` source project. This is an apparent workflow/source
mismatch to clarify, not proof of a failed deployment or a working whole-site
publisher. Do not use it blindly to publish the family site. No workflow,
Pages settings, game launch, or deployment has been changed or verified by this
documentation update.
