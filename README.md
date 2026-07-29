# jayrmotta.github.io

Personal blog, built with [Hugo](https://gohugo.io) and the [terminal](https://github.com/panr/hugo-theme-terminal) theme.

## Tech stack

- **Hugo Extended** — static site generator
- **Theme**: [hugo-theme-terminal](https://github.com/panr/hugo-theme-terminal) by panr (MIT licensed) — vendored as a git submodule in `themes/terminal`
- **Hosting**: GitHub Pages (user site), deployed via GitHub Actions on every push to `main`

## Local development

1. Install Hugo Extended (v0.90+ required by the theme). Check with `hugo version` — it must print `extended`.
2. Clone with submodules:
   ```
   git clone --recurse-submodules https://github.com/jayrmotta/jayrmotta.github.io.git
   ```
   If already cloned without `--recurse-submodules`:
   ```
   git submodule update --init --recursive
   ```
3. Run the dev server:
   ```
   hugo server -D
   ```
   Visit http://localhost:1313

## Adding a new blog post

```
hugo new posts/my-post-title.md
```

Edit the generated file under `content/posts/`. Posts publish as soon as they're pushed to `main` — there is no default draft field — so add `draft: true` to the front matter while you're still working, then remove it (or set it to `false`) when ready to publish, commit, and push to `main`.

## Adding a new static page

1. `hugo new <slug>.md` — creates `content/<slug>.md` (not under `posts/`).
2. Add a menu entry in `hugo.toml` under `[languages.en.menu.main]`.
3. Bump `showMenuItems` in `[params]` to match the new total menu-item count.
4. Commit and push.

## Deployment

Every push to `main` triggers `.github/workflows/deploy.yml`, which builds the site with Hugo and publishes it via GitHub Pages' Actions-based deployment. No manual build/publish step is needed. Check the Actions tab for build status; the live site is at https://jayrmotta.github.io/.

## Updating the theme

The theme is a git submodule pinned to a specific tag. Dependabot opens PRs to bump it automatically. To update manually:

```
cd themes/terminal && git fetch --tags && git checkout <new-tag> && cd ../..
git add themes/terminal && git commit -m "Bump hugo-theme-terminal to <new-tag>"
```

## License

This repository has no license — all rights reserved. The hugo-theme-terminal theme itself is © panr and used under its own MIT license (see `themes/terminal/LICENSE`).
