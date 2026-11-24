# Jiahe Cao — Academic website

Personal academic website for Jiahe Cao, a Computer Science Ph.D. student at the University of Nebraska–Lincoln, advised by Prof. Qiang Liu.

Site: <https://jiahecao.github.io> · [Google Scholar](https://scholar.google.com/citations?user=ckOANXsAAAAJ&hl=en)

Built with Jekyll and the versioned al-folio v1 gems. The site includes a biography, research interests, selected publications, and a searchable publication list.

## Edit the content

| Content                                    | File                                      |
| ------------------------------------------ | ----------------------------------------- |
| Biography, affiliation, research interests | `_pages/about.md`                         |
| Publications and paper links               | `_bibliography/papers.bib`                |
| Email, Google Scholar, GitHub              | `_data/socials.yml`                       |
| Profile photo                              | `assets/img/jiahe_cao.jpg`                |
| Site metadata, URL, navigation exclusions  | `_config.yml`                             |
| Venue labels and coauthor links            | `_data/venues.yml`, `_data/coauthors.yml` |

Set `selected = {true}` on a BibTeX entry to feature it on the homepage. The publications page renders every entry and groups them by year.
Use `abbr = {arXiv}` and an explicit preprint venue for work that has not been published; update the venue and DOI once publication is confirmed.

Unused starter pages and sample posts remain excluded from the published site in `_config.yml`; their demo assets have been deleted.
Add your own content and assets before enabling these pages. The example CV generator and upstream Lighthouse report workflow have also been removed.
Citation counts are disabled; Google Scholar remains the source for current metrics.

## Preview and validate

Use Ruby 3.3 or newer and Bundler 4.0.6 (the version in `Gemfile.lock`), plus Node.js and npm.

```bash
bundle install
npm ci
npm run lint:prettier
npm run lint:style-contract
bundle exec jekyll build
bundle exec al-folio upgrade audit
bundle exec jekyll serve
```

On this Apple Silicon Mac, Ruby 3.3 was installed with Homebrew. Select it before running the commands above if the shell still uses macOS system Ruby:

```bash
export PATH="/opt/homebrew/opt/ruby@3.3/bin:/opt/homebrew/lib/ruby/gems/3.3.0/bin:$PATH"
```

Open <http://localhost:4000/>. This is a personal GitHub Pages site, so `baseurl` is empty; do not add the starter demo's `/al-folio` prefix.
The profile photo is already sized for the web, so ImageMagick processing is disabled. The site does not need notebook rendering.

## GitHub Pages

The existing `.github/workflows/deploy.yml` builds on pushes to `main` or `master` and publishes the output to `gh-pages`.
In the repository's **Settings → Pages**, use **Deploy from a branch**, select **gh-pages**, and choose **/ (root)** after the first successful deployment.
Pull requests build for validation without publishing. Local edits alone do not update the live site.

## Content sources

- [Google Scholar profile](https://scholar.google.com/citations?user=ckOANXsAAAAJ&hl=en): publication list, cross-checked against publisher and preprint records.
- [Qiang Liu's student directory](https://liuqiang12040913.github.io/people/): prior M.S. at UC Riverside.
- [UNL ToShare profile](https://toshare.unl.edu/person/jiahe-cao/): affiliation.
- Current Ph.D. status, advisor, email, and emphasis on embodied intelligence were confirmed by the site owner.
- Profile photo: supplied by the site owner as `IMG_3967.jpg`; a web-sized copy is stored in `assets/img/jiahe_cao.jpg`.

Publication identifiers and links are stored with each BibTeX entry. Do not merge same-name authors from other institutions without checking the Scholar profile.

For the underlying starter, see [agent guidelines](AGENTS.md), [architecture](docs/ARCHITECTURE.md), and [customization guide](docs/CUSTOMIZE.md).
