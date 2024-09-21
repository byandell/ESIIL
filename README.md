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

Note that the Postdoc [README.md](https://github.com/CU-ESIIL/Postdoc_OASIS/blob/main/README.md)
is merely a copy of the [docs/index.md](https://github.com/CU-ESIIL/Postdoc_OASIS/blob/main/docs/index.md)
file in the same repo, prepended by a DOI signifier.
I have modified my
[README.md](https://github.com/byandell/ESIIL/blob/main/README.md)
(this file) to show how to set up such a repo.

## Construction

This site was created under direction of ESIIL staff (Ty Tuff)
using the following steps:

- Go to <https://github.com/CU-ESIIL/Postdoc_OASIS>
- Fork your own copy of this repo to your GitHub account.  Mine is <https://github.com/byandell/ESIIL>.
  - Click `Use this Template` (green button to right) menu.
  - Click `Create a new repository` entry.
  - Type in repository name (owner should be your github ID; repo name should be what you want as subfolder of your portfolio)
  - Click `Create Repository` (green button on lower right corner)
- Modify a few things on this repo
  - `Settings: Actions: General: Workflow permissions`: change to `Read and Write Permissions` and save
  - `Settings: Pages: Build and development: Branch`: select `deploy from a branch` and (can only do this after you do a few more steps (below)
    - Select branch `gh-pages`
    - Select folder `/docs`
- Modify "mkdocs.yml" file under `Code`
  - `site_url`: https://byandell.github.io/ESIIL (be sure this does not conflict with any pages on your personal website if you have one -- see https://github.com/byandell/byandell.github.io
  - `repo_url`: https://github.com/byandell/ESIIL 
  - other changes are optional, but these are needed.

Once steps 1-4 (except 3b) are done, your repo should be building. You can check with Actions to see progress. Then go to <https://byandell.github.io/ESIIL>
to see the result.

**Work displayed on your `gh-pages` branch in the folder `docs/`**
will be the main content of your web page.
That is, git-commits of modifications to `index.md` in
<https://github.com/byandell/ESIIL/docs>
will appear on
<https://byandell.github.io/ESIIL>.

## References on Creating a Portfolio Website

- [ESIIL Data Short Course: Create your own portfolio webpage](https://cu-esiil-edu.github.io/esiil-learning-portal/shortcourse/pages/03-git-github/03-github-portfolio/01-create-portfolio-website.html)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Publish Your Project Documentation with GitHub Pages](https://github.blog/developer-skills/github/publish-your-project-documentation-with-github-pages/)
