# blog-template

A minimal, resource-light Markdown-to-HTML personal site/blog template.
No JS framework, no build tooling beyond `pandoc` and `make` — just plain
HTML and Markdown, deployed as a static site.

This repo is meant to be used as a starting point (via GitHub's "Use this
template" button, or as a fork) for your own personal site. See
[szge/homepage](https://github.com/szge/homepage) for a real example built
from this template.

## Local development

Requires pandoc and entr (`brew install pandoc entr`).

Build all blog posts: `make`

Rebuild from scratch: `make clean && make`

Watch for changes: `make watch`

Blog posts are written as `.md` files in `blog/`. The title is derived from the filename by default, but you can also declare a title by adding a `title: Your Title` line at the top of the file (a pandoc YAML metadata field).

Generated `.html` files in `blog/` are gitignored and are not committed.

## Production (Vercel)

- Just add the project in Vercel and deploy — `vercel.json` runs `build.sh` on every deployment, which downloads a static pandoc binary and runs `make` to regenerate the blog HTML from markdown before the site is served. No extra configuration needed.

## Customizing

- Edit `index.html` with your own bio, links, and post list.
- Add your own `.md` files to `blog/`.
- Replace `favicon.png` and add a `Resume.pdf` if you want a resume link.
- `blog/template.html` is the pandoc layout shared by all posts — edit it to change the shared page structure/styling.
