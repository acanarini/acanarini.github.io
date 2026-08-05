# MICSO Lab website

This repository contains the source of the MICSO Lab website:
<https://canarinialberto.com/>.

The site presents the lab's research and projects, full publication record,
team and alumni, teaching, opportunities, news, and yearly reports.

## Editing the site

See **[EDITING_THE_WEBSITE.md](EDITING_THE_WEBSITE.md)** for simple browser-based
instructions and direct links to every content area.

No local Ruby or Jekyll installation is required. Changes saved to the `main`
branch are checked, built, and published automatically. The generated website
is stored on the `master` branch for GitHub Pages.

## Repository structure

- `_pages/` — main pages such as research, projects, teaching, and opportunities
- `_data/` — news, team members, alumni, grants, and highlighted publications
- `assets/ref.bib` — complete publication bibliography
- `images/` — team, project, research, and publication images
- `cv/` — curriculum vitae PDF
- `.github/workflows/` — automatic website building and publishing

## Hosting

The website is hosted free of charge with GitHub Pages. The custom domain is
recorded in `CNAME`; the domain remains registered separately with GoDaddy.

## License and template acknowledgement

The site was originally adapted from the academic website template by Spencer
H. Bryngelson and the Allan Lab website. The inherited template code is
available under the MIT License; see [LICENSE](LICENSE).
