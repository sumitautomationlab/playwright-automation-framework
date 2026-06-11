# Changelog

All notable changes to this project are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Per-release notes are also drafted automatically on GitHub Releases via
[Release Drafter](.github/workflows/release-drafter.yml); this file tracks the
notable, human-curated highlights.

## [Unreleased]

### Added

- Reusable CI workflow (`.github/workflows/reusable-test.yml`) that all
  container-based Playwright suites call, removing duplicated job definitions
  from the Quality Gate pipeline.
- Local git hooks via [husky](https://typicode.github.io/husky/): `lint-staged`
  runs ESLint `--fix` on staged sources (pre-commit) and
  [commitlint](https://commitlint.js.org/) enforces Conventional Commits
  (commit-msg).
- This changelog.

### Changed

- The `Quality Gate` aggregator now runs unconditionally and fails unless every
  required suite succeeds, so a skipped/failed suite can no longer slip through
  branch protection.
- Pinned `cspell` as a devDependency (run via `npm run spellcheck`) instead of
  fetching it unpinned through `npx`.
- The Playwright auto-update workflow now bumps the container image tags in
  lockstep with the `@playwright/test` package.
- Hardened workflow permissions (`contents: read`) on the link-check, spellcheck
  and external-demo workflows.

### Fixed

- README now uses a static MIT license badge (the dynamic badge intermittently
  errored) and a dark-theme Allure screenshot; removed the unused Codecov badge
  and upload step.

## Released

Tagged releases (`v1.2.0`, `v1.3.0`, `v1.3.1`, …) and their notes are published
on the [GitHub Releases](https://github.com/yousufwaqar/playwright-automation-framework/releases)
page. Highlights to date include the composite Quality Gate CI, accessibility,
security, performance and visual-regression suites, unit-test coverage gating
with c8, and the Allure report published live to GitHub Pages with trend history.

[Unreleased]: https://github.com/yousufwaqar/playwright-automation-framework/compare/v1.3.1...HEAD
