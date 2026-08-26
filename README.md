# Top 10 Songs of the Summer

A modern Jekyll starter site for publishing a personal ranking of the top 10 songs of the summer through GitHub Pages.

## Project structure

```text
.
├── _config.yml
├── _layouts/
│   ├── default.html
│   └── song.html
├── _songs/
│   ├── 01-song-title.md
│   ├── 02-song-title.md
│   └── ...10 song files
├── assets/css/style.css
├── index.md
├── Gemfile
└── README.md
```

The `_songs` directory is a Jekyll collection. Each Markdown file becomes a page at `/songs/<filename-without-extension>/`.

## Creating a song page

1. Copy one of the numbered files in `_songs/`.
2. Keep the numeric prefix to preserve the countdown order.
3. Rename it using a short, URL-friendly filename, such as `01-example-song.md`.
4. Replace the front matter values.
5. Write your review below the second `---`.

Use this template:

```markdown
---
title: "Song title"
performer: "Performer name"
rank: 1
rating: "★ ★ ★ ★ ☆"
image: "/assets/images/song-cover.jpg"
image_alt: "Description of the cover image"
description: "A short description for search engines."
---

Write the first paragraph of your review here.

Write the second paragraph of your review here. Add more paragraphs if needed.
```

### Front matter fields

- `title`: The song title shown on the page.
- `performer`: The artist or artists.
- `rank`: A number from 1 through 10. The home page sorts by this value.
- `rating`: Your star rating. Use filled stars (`★`) and empty stars (`☆`).
- `image`: Optional path to an image. Store images in `assets/images/` and use a path beginning with `/assets/`.
- `image_alt`: Descriptive alternative text for accessibility.
- `description`: Optional search-engine description.

If you leave out `image`, the page displays a styled image placeholder. If you leave out `rating`, it displays five empty stars.

## Adding images

Create `assets/images/` and add your image files there. Example:

```text
assets/images/example-song.jpg
```

Then set:

```yaml
image: "/assets/images/example-song.jpg"
```

Only use images you have permission to publish. Add meaningful `image_alt` text.

## Run the site locally

Install Ruby and Bundler, then from the project directory run:

```bash
bundle install
bundle exec jekyll serve --livereload
```

Open http://localhost:4000 in your browser. The `--livereload` option refreshes the page as you edit files. Stop the server with `Ctrl+C`.

If you do not use Bundler, the equivalent command is:

```bash
jekyll serve --livereload
```

## Publish with GitHub Pages

1. Create a new GitHub repository.
2. Put all project files at the repository root.
3. Commit and push the files:

```bash
git init
git add .
git commit -m "Create summer songs site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

4. In GitHub, open **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select the `main` branch and the `/ (root)` folder.
7. Click **Save** and wait for the deployment workflow to finish.
8. Visit the URL GitHub Pages provides.

For a project site, update `_config.yml` if needed:

```yaml
url: "https://YOUR-USERNAME.github.io"
baseurl: "/YOUR-REPOSITORY"
```

Keep the `relative_url` filters in the layouts and leave `image` paths beginning with `/assets/`; Jekyll will apply the base URL when rendering links.

## Updating the site

Edit or add Markdown files, commit the changes, and push:

```bash
git add .
git commit -m "Update song reviews"
git push
```

GitHub Pages will rebuild the site automatically.
