# osagga.github.io

My personal website, live at https://osagga.com.

Built with [Hugo](https://gohugo.io/) **0.91.2 (extended)** and the [Hermit](https://github.com/Track3/hermit) theme.
Everything needed to build the site lives in this repo. The theme is vendored in `themes/hermit/`
(pinned at upstream commit `2dc35c5`), not pulled in as a submodule.

## Layout

| Path | What it is |
| --- | --- |
| `config.toml` | Site settings: title, social links, menu |
| `content/posts/` | Blog posts (Markdown) |
| `content/about.md` | About page |
| `static/` | Files copied as-is: profile photo, resume, `CNAME` |
| `themes/hermit/` | Vendored theme |
| `.github/workflows/deploy.yml` | Builds and deploys to GitHub Pages on every push to `main` |

`public/` is the build output. It's git-ignored and never committed.

## Writing a post

```sh
hugo new posts/my-new-post.md   # creates a draft
hugo server -D                  # preview at http://localhost:1313, drafts included
```

Set `draft: false` in the post's front matter and push to `main`. GitHub Actions builds the site and publishes it.
