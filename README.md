# yaoyaoliu.web.illinois.edu

[![LICENSE](https://img.shields.io/github/license/yaoyao-liu/homepage?style=flat-square&logo=creative-commons&color=EF9421)](https://github.com/yaoyao-liu/homepage/blob/main/LICENSE)

This is the latest version of [my personal website](https://yaoyaoliu.web.illinois.edu/)'s source code. Feel free to use and share.
<br />
For more details, please refer to this repository: <https://github.com/yaoyao-liu/minimal-light>.

## Quick start

You need [Ruby](https://www.ruby-lang.org/en/) and [Jekyll](https://jekyllrb.com/).

```bash
bundle install
bundle exec jekyll serve
```

Open <http://localhost:4000>. The generated HTML is written to `_site/`.

## Configurations

1. **`_config.yml`** — name, position, affiliation, departments, e-mail, links (Google Scholar, DBLP, CV, GitHub, LinkedIn, Twitter, Bluesky), avatar, SEO fields and optional extras. Every option is commented in the file.
2. **`index.md`** — the short introduction on the home page.
3. **`_includes/news.md`** — news items. Entries inside `<div id="newsmore">` are hidden behind the "Show more" button.
4. **`_includes/contact.md`** — mailing address, office and phone.
5. **`_data/publications.yml`** and **`_data/preprints.yml`** — the publication list. Each entry supports `title`, `authors`, `conference_short` (the badge), `conference`, `year`, `pdf`, `code`, `page`, `data`, `bibtex`, `image`, `notes` and `others` (raw HTML). Publications are grouped by year; set `pub_archive_year` in `_config.yml` to collapse older years under one heading. Delete the entries in `preprints.yml` to hide the Preprints section.
6. **`teaching.md`, `group.md`, `service.md`/`_includes/service.md`, `talks.md`/`_includes/talks.md`, `awards.md`, `biography.md`** — replace the sample content.
7. **`_data/navigation.yml`** — the menu. Items with `children` become drop-downs; `right: true` aligns an item to the right edge.
8. **Images** — put your photo somewhere public and set `avatar` in `_config.yml` (an absolute URL makes it appear in social-media previews). Replace `assets/img/logo.svg` (top-bar logo), `favicon.ico`, and the icon set in `assets/favicon/`.

Delete any page you do not need (for example `awards.md`) and remove it from `_data/navigation.yml`.

## Layouts

| Layout     | Used by                         | Description                                         |
|------------|---------------------------------|-----------------------------------------------------|
| `homepage` | `index.md`                      | Hero + content + footnote and optional visitor map  |
| `default`  | all other content pages         | Hero + content                                      |
| `simple`   | `403.md`, `404.md`              | Content only, no hero                               |

The layouts share `_includes/head.html`, `topnav.html`, `hero.html`, `navigation.html`, `page-end.html` and `footer.html`. Links inside the site are relative (`./` on the home page, `../` on sub-pages), so the site can be hosted at a sub-path such as `https://www.example.edu/~yourname/` without a `baseurl`.

## Styling

Colours, fonts and spacing are defined in `_sass/minimal-light.scss` (general), `assets/css/nav.css` (top bar) and `assets/css/pub.css` (publication list). The design tokens at the bottom of `minimal-light.scss` (`--navy`, `--orange`, ...) are the quickest place to change the colour scheme.

## Deploying

The site is plain static HTML. It works on GitHub Pages (push the repository and enable Pages), or copy `_site/` to any web server after `bundle exec jekyll build`. `robots.txt` and `sitemap.xml` are generated from `canonical` in `_config.yml`.

## Acknowledgements

This template builds on the following projects:

* [pages-themes/minimal](https://github.com/pages-themes/minimal)
* [orderedlist/minimal](https://github.com/orderedlist/minimal)
* [al-folio](https://github.com/alshedivat/al-folio)
* [AcadHomepage](https://github.com/RayeRen/acad-homepage.github.io)
* [minimal-light](https://github.com/yaoyao-liu/minimal-light)

## License

Released under the [CC0 1.0 Universal](LICENSE) license. Feel free to use and share.
