# [Brian Yandell](https://byandell.github.io/ESIIL)

Welcome to the README for 
[Brian Yandell's ESIIL Collaboration](https://byandell.github.io/ESIIL) repository.
ESIIL is the [Environmental Data Science Innovation and Inclusion Lab](https://esiil.org),
with GitHub pages at
<https://github.com/CU-ESIIL>.
This repository is a fork of
<https://github.com/CU-ESIIL/Postdoc_OASIS>,
with my changes to have this serve as a hub for my research
collaboration with ESIIL researchers.
It creates a (virtual) subfolder `ESIIL` to my GitHub portfolio
[byandell.github.io](https://byandell.github.io),
displayed as
[byandell.github.io/ESIIL](https://byandell.github.io/ESIIL).

All development of GitHub Page occurs in the `gh-pages` branch.
See <https://github.com/byandell/ESIIL/tree/gh-pages>.

### Open questions

There are some things I do not understand.

- What is purpose of files in `main` if deployment is in `gh-pages`.
  - I see how this makes sense using `mkdocs` to make documents from `main` to `gh-pages`. Then I would want to only edit on `main`.
  - If I am not using `mkdocs`, what needs to be in `main`?
- The Postdoc page has a nice banner, which seems to be in
[gh-pages/index.html](https://github.com/CU-ESIIL/Postdoc_OASIS/blob/gh-pages/index.html).
  - Presumably this was created by `mkdocs` using the info in
[main/mkdocs.html](https://github.com/CU-ESIIL/Postdoc_OASIS/blob/main/mkdocs.yml)
- Without using `mkdocs`, why do my pages have header
[ESIIL](https://byandell.github.io/ESIIL/)?
  - Where is this in code tree?
