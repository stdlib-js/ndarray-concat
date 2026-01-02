# CHANGELOG

> Package changelog.

<section class="release" id="unreleased">

## Unreleased (2026-01-02)

<section class="features">

### Features

-   [`a7cbc8d`](https://github.com/stdlib-js/stdlib/commit/a7cbc8dbdbd69453891b1d5ffc1fcca9126910e2) - move optional argument to options object in `ndarray/concat` [(#9480)](https://github.com/stdlib-js/stdlib/pull/9480)
-   [`1a6e701`](https://github.com/stdlib-js/stdlib/commit/1a6e701ed9749678827c69b83d4780bd96d78015) - add `ndarray/concat` [(#7969)](https://github.com/stdlib-js/stdlib/pull/7969)

</section>

<!-- /.features -->

<section class="breaking-changes">

### BREAKING CHANGES

-   [`a7cbc8d`](https://github.com/stdlib-js/stdlib/commit/a7cbc8dbdbd69453891b1d5ffc1fcca9126910e2): move `dim` argument to options object

    -   To migrate, users should replace any usage of an optional `dim` argument with an options object with a `dim` property (e.g., `{'dim': -1}`).

</section>

<!-- /.breaking-changes -->

<section class="commits">

### Commits

<details>

-   [`a7cbc8d`](https://github.com/stdlib-js/stdlib/commit/a7cbc8dbdbd69453891b1d5ffc1fcca9126910e2) - **feat:** move optional argument to options object in `ndarray/concat` [(#9480)](https://github.com/stdlib-js/stdlib/pull/9480) _(by Muhammad Haris, Athan Reines)_
-   [`542bbf7`](https://github.com/stdlib-js/stdlib/commit/542bbf774737915ba7cd359d904e007239e397f6) - **refactor:** pass ndarray view to internal function _(by Athan Reines)_
-   [`1a6e701`](https://github.com/stdlib-js/stdlib/commit/1a6e701ed9749678827c69b83d4780bd96d78015) - **feat:** add `ndarray/concat` [(#7969)](https://github.com/stdlib-js/stdlib/pull/7969) _(by Muhammad Haris, Athan Reines, stdlib-bot)_

</details>

</section>

<!-- /.commits -->

<section class="contributors">

### Contributors

A total of 2 people contributed to this release. Thank you to the following contributors:

-   Athan Reines
-   Muhammad Haris

</section>

<!-- /.contributors -->

</section>

<!-- /.release -->

