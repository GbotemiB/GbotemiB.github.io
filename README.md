# Emmanuel Bolarinwa - Personal Website

Source for [gbotemib.github.io](https://gbotemiB.github.io), built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme.

## Where things live

- `_pages/` - top-level pages (about, publications, projects, cv)
- `_projects/` - project pages
- `_bibliography/papers.bib` - publications
- `_data/cv.yml` - CV content
- `_config.yml` - site settings and social links

## Running locally

With Docker:

```bash
docker compose up
```

Then open http://localhost:8080.

Without Docker (requires Ruby and Bundler):

```bash
bundle install
bundle exec jekyll serve
```

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the site and publishes it to GitHub Pages.

## License

The al-folio theme is MIT licensed, see [LICENSE](LICENSE).
