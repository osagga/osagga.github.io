# osagga.github.io

My personal website, live at https://osagga.com.

Built with [Hugo](https://gohugo.io/) **0.91.2 (extended)** and the [Hermit](https://github.com/Track3/hermit) theme.
Everything needed to build the site lives in this repo. The theme is vendored in `themes/hermit/`
(pinned at upstream commit `2dc35c5`, with a few local tweaks), not pulled in as a submodule.

## Layout

| Path | What it is |
| --- | --- |
| `config.toml` | Site settings: title, description, social links, menu |
| `content/posts/` | Blog posts (Markdown) |
| `content/about.md` | About page |
| `static/` | Files copied as-is: profile photo, `CNAME` |
| `themes/hermit/` | Vendored theme |
| `bin/hugo` | Runs the pinned Hugo version. It downloads Hugo on first use, checks it against its sha256, and caches it in `.hugo/` |
| `.github/workflows/deploy.yml` | Builds with `bin/hugo` and deploys to GitHub Pages on every push to `main` |
| `.github/dependabot.yml` | Opens a monthly PR when the pinned GitHub Actions have updates |

`public/` (build output) and `.hugo/` (cached Hugo binary) are git-ignored.

## Writing a post

```sh
bin/hugo new posts/my-new-post.md   # creates a draft
bin/hugo server -D                  # preview at http://localhost:1313, drafts included
```

Set `draft: false` in the post's front matter and push to `main`. GitHub Actions builds the site and publishes it.
