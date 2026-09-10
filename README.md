# cw-do.github.io

Research homepage of **Changwoo Do** — Scientific Staff and EQ-SANS Point of Contact,
Neutron Scattering Division, Spallation Neutron Source, Oak Ridge National Laboratory.

- Homepage: <https://cw-do.github.io/>
- Full CV: <https://cw-do.github.io/cv/>

## This repository is a build artifact — don't edit it here

Everything in it is generated. The sources live in the private `Research_ORNL` knowledge
vault under `vault/areas/CV/` and are built by `scripts/make_cv_html.py`:

| Source | Feeds |
|---|---|
| `cv_current.md` | every fact and number on both pages: sections, the publication list, stat tiles, software list, selected publications |
| `homepage.md` | the homepage's hand-written prose — intro and research themes, each citing CV entry numbers so citation text is never retyped |
| `update.md` | the News timeline (citation lines only) |

```
python scripts/make_cv_html.py            # writes vault/areas/CV/site/
cp -r vault/areas/CV/site/. <this clone>/
git commit -am "..." && git push
```

Editing files here would be silently overwritten by the next build and would put the site
out of step with the CV it mirrors.

The generator deliberately omits the personal cell number that the source CV carries; the
office number and work email are published.

One self-contained HTML file per page, no build step, no dependencies. `.nojekyll` keeps
GitHub Pages from running Jekyll over it.
