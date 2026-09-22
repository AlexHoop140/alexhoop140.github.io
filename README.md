# Personal website

Source folder: `C:\Users\lephu\OneDrive\personal_page`

Live site: https://phuongtrungle.page · Blog: https://phuongtrungle.page/blog/

GitHub Pages builds this website with Jekyll. Activities are Markdown files; no HTML is needed to write an entry. Each published entry automatically appears on the Blog page and, if among the top five, in the homepage News section.

## Add an activity on GitHub (no local software needed)

1. Open this repository on GitHub. Copy the contents of `templates/activity.md`.
2. Select **Add file → Create new file**. Name it `_activities/your-event-name.md` (lowercase, hyphen-separated; keep this filename stable because it becomes the URL).
3. Paste the template. Edit the title, date label, type, location, summary, and story. Increase `order` to put a new entry first; larger numbers appear first. `date_label` is display text: use just a year if exact dates are unknown.
4. To keep a draft, leave `published: false`. When ready, change it to `published: true`.
5. Commit the file to `main`. GitHub Pages publishes it automatically, usually within a few minutes. Check the Actions tab if the update does not appear.

## Add photos

Upload photos into `assets/images/your-event-name/` using **Add file → Upload files**, or create the folder and copy photos there locally. Use simple filenames without spaces. Resize large photos before uploading (around 1600 pixels wide is usually enough).

For a cover image, enable these lines in the entry's metadata:

```yaml
cover: "/assets/images/your-event-name/photo.jpg"
cover_alt: "Presenting my poster at the conference"
cover_caption: "A short optional caption."
```

For additional photos anywhere in the story:

```markdown
![Describe what is in the photo](/assets/images/your-event-name/photo.jpg)
```

Always upload the image before publishing its reference. The existing entries have no cover image because event photos have not been supplied.

## Writing in Markdown

```markdown
A normal paragraph about the event.

## A section heading

**Bold text**, *italic text*, and [a link](https://example.com).

- First highlight
- Second highlight
```

## Edit an existing entry

Open its file in `_activities/`, select the pencil icon, edit, and commit. No homepage or Blog changes are needed. You can also ask Codex to update an event and provide text/photos.

## Local publishing

Work in this folder, then commit and push the specific files you changed:

```powershell
git add -- _activities/your-event-name.md assets/images/your-event-name/
git commit -m "Add conference activity"
git push origin main
```

The portable GitHub CLI is in `.tools/github-cli/runtime/bin/gh.exe`; it is excluded from Git and the published site. Authentication is already configured on this computer.

## Site structure

- `index.html`: academic homepage and automatic News list.
- `_activities/`: event stories in Markdown.
- `blog/index.html`: automatic Blog listing.
- `_layouts/` and `_includes/`: shared page templates.
- `assets/site.css`: shared styling.
- `_config.yml`: Jekyll settings.
- `templates/activity.md`: copyable draft, excluded from the public site.

Opening index.html directly will not render the templates. Use the GitHub Pages build for the complete site, or a local Jekyll installation (`jekyll serve`) if available. Private notes should not be committed even as drafts: this repository is public.
