# TSC_SUMT Project Reports

Tractor Supply Sumter, South Carolina project reports and coordination briefs.

## Live construction report

- [Open Construction Status](https://harvey-buck.github.io/TSC_SUMT-Project-Reports/construction-status.html)
- [Open site](https://harvey-buck.github.io/TSC_SUMT-Project-Reports/)

The root `index.html` redirects to `construction-status.html`. These are
standalone HTML files; no application build or package installation is required.
The report uses externally hosted Google Fonts and has no local asset files.

## Publishing

This repository belongs to [Harvey-Buck](https://github.com/Harvey-Buck/TSC_SUMT-Project-Reports).
GitHub Pages uses **GitHub Actions**, configured in Settings → Pages → Build
and deployment → Source. The workflow is `.github/workflows/pages.yml`.

The workflow runs when the report, root redirect, or workflow changes are pushed
to `main`, and can also be started manually from Actions. It stages only
`index.html` and `construction-status.html`, uploads that directory as the Pages
artifact, and deploys it to the `github-pages` environment.

For weekly updates, edit the centralized `dashboardData` object in
`construction-status.html`, preserve the approved layout and CSS, validate the
report, then commit and push to `main`. Wait for the workflow to succeed for
that exact commit and verify the live root and construction report.

`gc-coordination-brief.html`, `civil-coordination-brief.html`, and
`internal-status.html` remain in the repository but are excluded from this
Pages artifact. Adding a local asset requires explicitly adding it to the
workflow's staging command and adjusting its file-count check and path filters.
