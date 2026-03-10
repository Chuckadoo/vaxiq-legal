# Publish these pages to GitHub

This folder is meant to be pushed to a **separate public repo** so the Privacy Policy has a public URL (App Store / Play Store requirement). Your main VaxIQ repo stays private.

## One-time setup

1. **Create the repo on GitHub**  
   Go to [github.com/new](https://github.com/new). Name it `vaxiq-legal`, set visibility to **Public**, do **not** add a README or .gitignore. Create the repository.

2. **Push this folder** (from your machine, in the VaxIQ project root):
   ```bash
   cd vaxiq-legal
   git init
   git add .
   git commit -m "Initial legal pages"
   git branch -M main
   git remote add origin https://github.com/Chuckadoo/vaxiq-legal.git
   git push -u origin main
   ```
   (If your GitHub username is not `Chuckadoo`, change the URL.)

3. **Turn on GitHub Pages**  
   In the `vaxiq-legal` repo: **Settings → Pages → Build and deployment → Source**: Deploy from a branch. **Branch**: `main`, folder **/ (root)**. Save.

After a minute or two, the Privacy Policy will be live at:

**https://chuckadoo.github.io/vaxiq-legal/**

Use that URL in App Store Connect (Privacy Policy URL) and in `constants/legalUrls.ts` (already set).

## Updating the policy later

Edit `index.md` in this folder, then:

```bash
cd vaxiq-legal
git add index.md
git commit -m "Update privacy policy"
git push
```

GitHub Pages will update automatically.
