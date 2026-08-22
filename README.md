# KeViNYuAn0314.github.io

Personal academic homepage for Bowen Yuan, built on the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme.

## Editing

| What you want to change            | File                                    |
| ---------------------------------- | --------------------------------------- |
| Bio, research interests, education, experience, projects | `_pages/about.md`     |
| Papers (adds to both the home page and `/publications`)  | `_bibliography/papers.bib` |
| Email, GitHub, Scholar, LinkedIn, CV link                | `_data/socials.yml`   |
| Venue badge colours                | `_data/venues.yml`                      |
| Site title, URL, description, feature flags | `_config.yml`                  |
| CV PDF                             | `assets/pdf/Bowen_Yuan_CV.pdf`          |

A paper shows on the home page when its bib entry has `selected = {true}`. Everything in
`papers.bib` shows on `/publications` regardless.

## Preview locally

Requires Docker only, no Ruby install:

```bash
docker compose up -d      # http://127.0.0.1:8080
docker compose logs -f    # build output
docker compose down
```

Edits to content reload automatically. Editing `_config.yml` restarts Jekyll, which takes a few
seconds longer.

## Deploying

`.github/workflows/deploy.yml` builds the site and pushes the result to the `gh-pages` branch on
every push to `main`. In the repository settings, set Pages to serve from `gh-pages` / root.

The upstream al-folio CI workflows were removed because they test the theme itself rather than this
site. They are kept locally in `_template_demo/`, which is gitignored along with the rest of the
template's demo content.
