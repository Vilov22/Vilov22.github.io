# Personal website starter

A small Jekyll website for GitHub Pages. No paid theme, external fonts, analytics or JavaScript dependencies. Edit the content in Markdown; colours and layout are in `assets/style.css`.

## Before publishing

1. Your name and GitHub Pages URL are set in `_config.yml`.
2. Review `index.md`: introduction, institution, email and GitHub URL.
3. Projects and posts are empty; add real content when ready.
4. When ready, add your **finished public CV** as `assets/cv.pdf` and enable the link in `cv.md`. The PDF is intentionally not included yet.
5. Remove any personal information you do not want public. Everything you commit to a public repository, including its history, can be read by anyone. Only upload this website folder, not the surrounding Career folder.

## Publish on GitHub Pages (recommended: account website)

1. Sign in to GitHub and create a **public repository named `YOUR-USERNAME.github.io`**, replacing YOUR-USERNAME with your exact GitHub username. Do not add a README or other starter files on GitHub if following the commands below. If that repository already exists, inspect it first; do not overwrite an existing website.
2. Set these values in `_config.yml`:

   ```yaml
   url: "https://YOUR-USERNAME.github.io"
   baseurl: ""
   ```

3. Open a terminal in **this website folder** and run these commands individually:

   ```bash
   git init
   git add .
   git commit -m "Add personal website"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-USERNAME.github.io.git
   git push -u origin main
   ```

   Replace both username placeholders. GitHub requires an authenticated credential helper, token or SSH key; an account password alone will not work for Git pushes. You can also publish using GitHub's web file uploader without terminal authentication.

4. In the repository, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, then **main** and **/ (root)**. Save.
5. Wait for the Pages build to finish (usually a few minutes). Your site will appear at **https://YOUR-USERNAME.github.io**. Check the repository's **Actions** tab if deployment fails. It must build with Jekyll: do not add a `.nojekyll` file.

### Alternative: a project repository

If the repository is named `personal-website`, set:

```yaml
url: "https://YOUR-USERNAME.github.io"
baseurl: "/personal-website"
```

The site address becomes `https://YOUR-USERNAME.github.io/personal-website/`. The templates use `relative_url` so navigation and assets work at either address.

## Update the site

Edit the source files, then run:

```bash
git add .
git commit -m "Update website"
git push
```

GitHub Pages rebuilds automatically. Alternatively, edit Markdown files directly on GitHub. Never commit passwords, access tokens or private documents.

## Preview locally (optional)

Install Ruby and Bundler if needed. From this directory:

```bash
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve --host 127.0.0.1
```

Open **http://127.0.0.1:4000**. Stop the server with Ctrl+C. Restart it after changing `_config.yml`. Opening the source HTML directly or serving it with Python will not render the Jekyll templates.

## Add content

- **Project:** add a heading, description and links in `projects.md`.
- **Post:** add `_posts/YYYY-MM-DD-title.md` with `title` in YAML front matter. Future-dated posts are not published by default.
- **Images:** add files under `assets/` and use `![Description]({{ '/assets/image.png' | relative_url }})`.
- **CV:** replace `assets/cv.pdf`; the URL stays the same.
- **Appearance:** edit CSS variables in `assets/style.css`.

Official guide: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll
