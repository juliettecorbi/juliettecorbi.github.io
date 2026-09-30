# How to update your site

This repo is the "Academic Pages" Jekyll template, now trimmed down to five
sections: **Intro** (the homepage), **Publications**, **Teaching**, **CV**,
and **Blog**. Talks and Portfolio are switched off (see below) since you
didn't ask for them.

## Where each section lives

| Section | File(s) to edit |
|---|---|
| Site title, your name, bio, email, social links | `_config.yml` (under `author:`) |
| Intro / homepage | `_pages/about.md` |
| CV | `files/CV_Corbi.pdf` (the file itself) — the CV page just links to it |
| Publications | `_publications/` — one `.md` file per publication |
| Teaching | `_teaching/` — one `.md` file per course |
| Blog | `_posts/` — one `.md` file per post |
| Top navigation menu | `_data/navigation.yml` |
| Your photo | replace `images/profile.png` with your own (same filename, or update `avatar:` in `_config.yml`) |
| PDFs (papers, slides, your CV) | drop them in `files/`, then link to `/files/your-file.pdf` |

## Updating your CV

The CV page (`_pages/cv.md`) is just a short page linking to
`files/CV_Corbi.pdf` — it doesn't pull from any other file. To update it:

1. Export your updated CV as a PDF.
2. Replace `files/CV_Corbi.pdf` with the new file, **keeping the same
   filename** — that way the link on the CV page keeps working and you don't
   need to touch `_pages/cv.md` at all.
3. (Optional) Update the "Last updated" line in `_pages/cv.md`.

If you'd rather rename the file, just update the link in `_pages/cv.md` to
match.

## Adding a publication, course, or blog post

Each is a separate Markdown file with a block of metadata (front matter) at
the top. To add a new one:

1. Duplicate the closest example file already in `_publications/`,
   `_teaching/`, or `_posts/`.
2. Rename the copy — the filename's date matters for sorting, so use
   `YYYY-MM-DD-short-title.md`.
3. Fill in every bracketed field in the front matter (between the `---`
   lines).
4. Write the body text below the front matter in Markdown.
5. Delete the `<!-- TEMPLATE: ... -->` comment near the top once you're done
   — it's just a reminder and won't show on the live site either way.

There's one hidden template left in `_publications/` (a conference-paper
example, `published: false`) for whenever you add your first one — set
`published: true` and fill it in, or duplicate it.

## Previewing before you publish

You don't strictly need to preview locally — pushing to GitHub is enough,
since GitHub Pages rebuilds the site automatically (see below). But if you
want to check your changes first:

1. Install Ruby + Bundler (see `README.md` for OS-specific commands).
2. From this folder, run `bundle install` once.
3. Run `bundle exec jekyll serve -l -H localhost` and open
   `http://localhost:4000`.

## Publishing your changes

I edited these files directly in your local folder, but I can't push to
GitHub from here — you'll need to commit and push yourself, the same way you
would any other change:

* **With GitHub Desktop:** open the app, review the changes, write a commit
  message, click "Commit", then "Push origin".
* **With the command line**, from this folder:
  ```
  git add -A
  git commit -m "Set up site structure and add my content"
  git push
  ```

Then double-check, on GitHub, that **Settings → Pages** has a source
configured (branch `master`, folder `/ (root)`) — that's the one setting
that has to be turned on for the site to actually go live at
`https://juliettecorbi.github.io`. If it's already set, GitHub rebuilds the
site automatically within a minute or two of every push.

## Optional cleanup: Talks & Portfolio

Talks and Portfolio are switched off (their pages are hidden and their
collections are set to not build), so they won't appear anywhere on the live
site. I couldn't delete files from here, so if you want the repo itself
cleaner, you can manually delete these in File Explorer — none of them are
used anymore:

* `_pages/talks.html`, `_pages/portfolio.html`, `_pages/talkmap.html`
* `_talks/` and `_portfolio/` (folders)
* `talkmap.py`, `talkmap.ipynb`, and the `talkmap/` folder

If you ever want either section back instead, see the comments at the top of
those hidden page files, and flip `output: true` for that collection in
`_config.yml`.

## Note on your files

You have two identical copies of this project on your computer —
`juliettecorbi.github.io` and `Website`. All of the above changes were made
in `juliettecorbi.github.io` (the one matching your GitHub repo). The
`Website` copy was left untouched, as you asked.
