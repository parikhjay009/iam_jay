# five-nines

Jay Parikh's resume site — a single static page (HTML/CSS, no build step) auto-deployed to GitHub Pages via GitHub Actions every time `main` is updated.

## Structure

```
index.html                     the whole site (markup + styles)
assets/jay-parikh.png          headshot
assets/Jay_Parikh_Resume.pdf   downloadable PDF version
.github/workflows/deploy.yml   deploys to Pages on every push to main
```

## One-time setup

1. Create a new **public** GitHub repository named `five-nines` (or any name you like — see "Renaming" below).
2. Push this folder to it:
   ```bash
   cd five-nines
   git init
   git add .
   git commit -m "Initial resume site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/five-nines.git
   git push -u origin main
   ```
3. In the repo on GitHub: **Settings → Pages → Build and deployment → Source**, select **GitHub Actions**. (You only need to do this once — after this, the workflow file handles everything.)
4. Push will kick off the `Deploy resume site to GitHub Pages` action automatically. Watch it under the **Actions** tab.
5. Once it's green, your site is live at:
   ```
   https://<your-username>.github.io/five-nines/
   ```

## Updating your resume

Just edit `index.html` (and swap `assets/Jay_Parikh_Resume.pdf` if you update the PDF), then:

```bash
git add .
git commit -m "Update resume"
git push
```

The Action re-runs automatically and the live site updates within a minute or two — no manual redeploy needed.

## Renaming the site

The repo name becomes part of the URL (`<username>.github.io/<repo-name>`), so pick something relevant to your field. A few options if `five-nines` (a nod to 99.999% uptime) isn't your favorite:

- `sre-jay`
- `uptime-jay`
- `jayparikh.dev` (if you also want to point a custom domain at it — see GitHub's docs on custom domains for Pages)

To rename, just rename the GitHub repo in Settings — Pages will pick up the new URL automatically.
