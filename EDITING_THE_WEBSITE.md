# Editing the MICSO Lab website

The website is published automatically by GitHub. You do **not** need Ruby,
Jekyll, Bundler, gems, or administrator access on your computer.

## The normal workflow

1. Open the relevant file using one of the links below.
2. Click the pencil icon (`Edit this file`).
3. Make the change in your browser.
4. Click `Commit changes` and save it to the `main` branch.
5. GitHub rebuilds and publishes the website automatically. This normally takes
   a few minutes.

The public address remains <https://canarinialberto.com/>. The GoDaddy domain
and its DNS settings do not need to be changed.

## Where each type of content lives

| I want to update… | File to edit |
| --- | --- |
| News | [`_data/news.yml`](https://github.com/acanarini/acanarini.github.io/edit/main/_data/news.yml) |
| Principal investigator profile | [`_data/pi.yml`](https://github.com/acanarini/acanarini.github.io/edit/main/_data/pi.yml) |
| Postdoctoral researchers | [`_data/post_docs.yml`](https://github.com/acanarini/acanarini.github.io/edit/main/_data/post_docs.yml) |
| PhD candidates | [`_data/phd.yml`](https://github.com/acanarini/acanarini.github.io/edit/main/_data/phd.yml) |
| Visiting researchers | [`_data/visiting.yml`](https://github.com/acanarini/acanarini.github.io/edit/main/_data/visiting.yml) |
| Alumni | [`_data/alumni.yml`](https://github.com/acanarini/acanarini.github.io/edit/main/_data/alumni.yml) |
| Research | [`_pages/research.md`](https://github.com/acanarini/acanarini.github.io/edit/main/_pages/research.md) |
| Projects | [`_pages/projects.md`](https://github.com/acanarini/acanarini.github.io/edit/main/_pages/projects.md) |
| Teaching | [`_pages/teaching.md`](https://github.com/acanarini/acanarini.github.io/edit/main/_pages/teaching.md) |
| Opportunities | [`_pages/opportunities.md`](https://github.com/acanarini/acanarini.github.io/edit/main/_pages/opportunities.md) |
| Yearly reports | [`_pages/yearly_report.md`](https://github.com/acanarini/acanarini.github.io/edit/main/_pages/yearly_report.md) |
| Full publication list | [`assets/ref.bib`](https://github.com/acanarini/acanarini.github.io/edit/main/assets/ref.bib) |
| Highlighted publications | [`_data/highlights.yml`](https://github.com/acanarini/acanarini.github.io/edit/main/_data/highlights.yml) |

## Adding a news item

Open `_data/news.yml` and add the new item at the very top:

```yaml
- date: 5 August, 2026
  headline: "A short description of the news."
```

Keep the two spaces before `headline`. If the item links to another page, use
this format:

```yaml
- date: 5 August, 2026
  headline: "Our new <a href='https://doi.org/example' class='text-info'>paper</a> is available."
```

## Adding or changing a team member

Edit the appropriate file in `_data`. Copy an existing person and change the
fields:

```yaml
- name: First name Last name
  photo: Photo.jpg
  info: PhD candidate, started November 2026. Research description.
  email: name@unibo.it
  website: https://www.unibo.it/example
  number_educ: 1
  education1: "(2026) M.S. Subject, University (Country)"
```

Upload the photograph to the `images` folder, then use exactly that filename in
the `photo` field. Filenames are case-sensitive.

## Updating publications

The complete publication list is generated from `assets/ref.bib`. Export the
updated bibliography as BibTeX from Zotero and replace the contents of that
file. Highlighted papers on top of the publications page are edited separately
in `_data/highlights.yml`.

## Asking ChatGPT to make a change

You can describe the update in ordinary language. For example:

> Add this paper to my publications and news, and make it the first highlighted
> paper. DOI: 10.xxxx/xxxxx.

or:

> Move Jane Doe from visiting researchers to alumni. Say that she visited from
> September 2025 to July 2026 and is now at Example University.

ChatGPT can prepare the changes for review. Nothing needs to be installed on
your university computer.

## If something goes wrong

Open the repository's **Actions** tab. A green check means the website was
built and published. A red cross means the content contains an error, commonly
an indentation or quotation-mark problem in a YAML file. The previously
published website stays available while the error is corrected.
