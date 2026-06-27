# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

All packages in this monorepo are released together under a single version.
Releases prior to `3.2.0` are documented in the
[GitHub Releases](https://github.com/oramasearch/orama/releases).

## [Unreleased]

_Nothing yet._

## [3.2.0] - 2026-06-27

### Added

- **Vietnamese language support** — Vietnamese stemmer, stopwords, and tokenizer
  registration, available via `@orama/stemmers/vietnamese` and
  `@orama/stopwords/vietnamese`. Thanks to
  [@xirothedev](https://github.com/xirothedev).
  ([#1013](https://github.com/oramasearch/orama/pull/1013))
- **Experimental Korean tokenizer** — new `@orama/tokenizers/korean`, built on
  `Intl.Segmenter`. Thanks to [@dayongkr](https://github.com/dayongkr).
  ([#1018](https://github.com/oramasearch/orama/pull/1018))

### Changed

- **`@orama/plugin-astro`: migrated to Astro 5**, adopting the Content Layer API
  and the `assets`-based `astro:build:done` hook. Thanks to
  [@strlrd-29](https://github.com/strlrd-29).
  ([#1020](https://github.com/oramasearch/orama/pull/1020))
- **`@orama/plugin-nextra`: `next`, `react`, and `react-dom` are now
  `peerDependencies`** (Next 14–16, React 18 & 19) rather than hard
  dependencies, so the plugin no longer bundles a second React/Next runtime onto
  consumers. A `tsc --noEmit` typecheck now guards framework compatibility in CI.
  ([#1025](https://github.com/oramasearch/orama/pull/1025))
- Bumped `markdown-it` from 13.0.2 to 14.1.1 in `@orama/plugin-docusaurus` and
  `@orama/plugin-vitepress`.
  ([#1017](https://github.com/oramasearch/orama/pull/1017))

### Fixed

- **`@orama/orama`: resolved a circular dependency in the search module** that
  caused a fatal `fetchDocuments is not a function` error under Metro/Expo
  bundling with `experimentalImportSupport` (tree-shaking). The `fetchDocuments`
  and `fetchDocumentsWithDistinct` helpers were extracted into a dedicated
  module, removing the cycle for every bundler with no bundled artifact required.
  Reported by [@isaachinman](https://github.com/isaachinman)
  ([#961](https://github.com/oramasearch/orama/issues/961)).
  ([#1026](https://github.com/oramasearch/orama/pull/1026))

[Unreleased]: https://github.com/oramasearch/orama/compare/v3.2.0...HEAD
[3.2.0]: https://github.com/oramasearch/orama/compare/v3.1.18...v3.2.0
