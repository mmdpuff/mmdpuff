# Setup guide — @mmdpuff profile

This folder is designed to live in **https://github.com/mmdpuff/mmdpuff** (a public profile repository that already exists).

## Upload to GitHub

1. Open https://github.com/mmdpuff/mmdpuff and make sure you are on `main`.
2. Replace its root `README.md` with the provided one.
3. Add all three files in `assets/`: `hero.svg`, `terminal.svg`, and `footer.svg`. **Keep their names and directory.**
4. Add both `.github/workflows/snake.yml` and `.github/workflows/profile-3d.yml`, and commit.
5. Open **Settings → Actions → General → Workflow permissions**; choose **Read and write permissions**, and save if your policy permits. The workflow needs write permission to publish the `output` branch.
6. Go to **Actions → Animate GitHub contributions → Run workflow** once. The first run creates the `output` branch and makes the contribution snake visible. Then run **Actions → Build 3D contribution city → Run workflow** once to generate the 3D contribution illustration in `profile-3d-contrib/` on `main`. GitHub may require manually enabling workflows first.
7. The snake updates automatically daily. Other remote widgets refresh through their respective providers.

### Easiest method for all files at once

Clone the repo, copy the files from this zip, and push:

```bash
git clone https://github.com/mmdpuff/mmdpuff.git
cd mmdpuff
# Copy README.md, assets/, and .github/workflows/ from the zip into this directory.
git add README.md assets/ .github/workflows/snake.yml .github/workflows/profile-3d.yml
git commit -m "Redesign GitHub profile with a neon mobile x embedded theme"
git push origin main
```

If you use GitHub Web UI, be sure to create the nested directory `.github/workflows` (dot folder) and include the SVG assets. Uploading only `README.md` won't display local graphics.

## Personalize

- Profile name appears in `assets/hero.svg` and `README.md`.
- Main palette: violet `#A78BFA`, cyan `#38E8DE`, dark `#0B1021`.
- Featured project links point to verified repositories `LUMIO` and `todolist_app`.
- No email address, website, social account, fake stats, or unverified experience was added.

## Dependency notes

The bespoke SVG artwork is stored in your own repository. Third-party badges and graphs are embedded as images; if a provider is down, that particular widget may fail temporarily. The activity graph uses the new Cloudflare Workers endpoint documented by its maintainer (not the deprecated Vercel address). The snake is generated through a scheduled action using Platane/snk and published to an `output` branch. The 3D contribution city is generated with `yoshi389111/github-profile-3d-contrib` and committed to the `main` branch. Both animations need their first successful workflow runs to appear. No personal access token is required for public contributions with the standard Actions token.
