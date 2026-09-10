# research_portfolio

Research homepage for **Changwoo Do** — Scientific Staff and EQ-SANS Point of Contact,
Neutron Scattering Division, Spallation Neutron Source, Oak Ridge National Laboratory.

Live page: <https://cw-do.github.io/research_portfolio/>

## This is a build artifact — don't hand-edit `index.html`

`index.html` is generated. The source of truth for every fact on the page is
`vault/areas/CV/cv_current.md` in the private `Research_ORNL` knowledge vault, and the page
is built from it by `scripts/make_cv_html.py`:

```
python scripts/make_cv_html.py          # writes vault/areas/CV/index.html
cp vault/areas/CV/index.html <clone>/index.html
git -C <clone> commit -am "CV update" && git push
```

Editing `index.html` here would be silently overwritten by the next build, and would put the
web page out of step with the CV it is supposed to mirror.

What the generator reads:

| Source | Feeds |
|---|---|
| `cv_current.md` | every section, the publication list, and the stat tiles (all counted, none typed in) |
| `update.md` | the "Recent additions" timeline (only the citation lines; the internal log prose stays private) |

The generator deliberately drops the personal cell number that `cv_current.md` carries. The
office number and work email are published; the cell number is not.

## Enabling GitHub Pages

Settings → Pages → Source: *Deploy from a branch* → `main` / `/ (root)`.

The page is one self-contained file: no build step, no dependencies, no external assets.
`.nojekyll` keeps Pages from running Jekyll over it.
