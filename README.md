# geo-huanwang.com

Personal academic website of **Huan Wang** — engineer/researcher in offshore geotechnics: foundations and anchors, physical and numerical modelling, soil–structure interaction.

**Live site: [https://geo-huanwang.com](https://geo-huanwang.com)**

## What's on the site

- **[Publications](https://geo-huanwang.com/publications/)** — journal papers, conference papers, and theses
- **[Research Projects](https://geo-huanwang.com/portfolio/)** — research programmes and projects, including the MIDAS centrifuge testing programme
- **[Centrifuge 101](https://geo-huanwang.com/centrifuge-101/)** — a knowledge hub on geotechnical centrifuge modelling
- **[CPT 101](https://geo-huanwang.com/cpt-101/)** — a knowledge hub on cone penetration testing and interpretation
- **[Datasets](https://geo-huanwang.com/datasets/)** — open research datasets (centrifuge tests on monopiles, sand triaxial test database), hosted on 4TU.ResearchData
- **[Blog](https://geo-huanwang.com/year-archive/)** — technical articles and reviews
- **[CV](https://geo-huanwang.com/cv/)**

## Repository layout

The site is built with [Jekyll](https://jekyllrb.com/) and served by GitHub Pages from the `master` branch.

| Path | Content |
|------|---------|
| `_pages/` | Top-level pages (about, publications, datasets, CV, …) |
| `_posts/` | Blog posts |
| `_publications/` | One markdown file per publication |
| `_portfolio/` | Research project pages |
| `_centrifuge101/`, `_cpt101/` | Knowledge-hub article collections |
| `images/` | Figures and profile images (`images/posts/<slug>/` per blog post) |
| `files/` | PDFs and other downloadable files |
| `_config.yml` | Site configuration |

## Running locally

```bash
bundle install --path vendor/bundle
bundle exec jekyll serve
```

Then open http://localhost:4000. Requires Ruby with Bundler.

## Credits and license

Built on the [Academic Pages](https://github.com/academicpages/academicpages.github.io) template, itself a fork of [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) — see [LICENSE](LICENSE) for the template's MIT license. Site content (text, figures, and data) © Huan Wang unless noted otherwise; blog articles and linked datasets are released under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) where stated.
