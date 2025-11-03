<!--

@license Apache-2.0

Copyright (c) 2025 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# concat

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Concatenate a list of [ndarrays][@stdlib/ndarray/ctor] along a specified [ndarray][@stdlib/ndarray/ctor] dimension.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

```javascript
import concat from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-concat@deno/mod.js';
```

You can also import the following named exports from the package:

```javascript
import { assign } from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-concat@deno/mod.js';
```

#### concat( arrays\[, dim] )

Concatenates a list of [ndarrays][@stdlib/ndarray/ctor] along a specified [ndarray][@stdlib/ndarray/ctor] dimension.

```javascript
import array from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-array@deno/mod.js';
import ndarray2array from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-to-array@deno/mod.js';

var x = array( [ [ -1.0, 2.0 ], [ -3.0, 4.0 ] ] );
var y = array( [ [ -5.0, 6.0, -7.0 ], [ 8.0, -9.0, 10.0 ] ] );

var out = concat( [ x, y ], -1 );
// returns <ndarray>

var arr = ndarray2array( out );
// returns [ [ -1.0, 2.0, -5.0, 6.0, -7.0 ], [ -3.0, 4.0, 8.0, -9.0, 10.0 ] ]
```

The function accepts the following arguments:

-   **arrays**: a list of input [ndarrays][@stdlib/ndarray/ctor]. Must be [broadcast compatible][@stdlib/ndarray/base/broadcast-shapes] except for the dimension along which to concatenate. The data type of the output [ndarray][@stdlib/ndarray/ctor] is determined by applying [type promotion rules][@stdlib/ndarray/promotion-rules] to the list of input [ndarrays][@stdlib/ndarray/ctor]. If provided [ndarrays][@stdlib/ndarray/ctor] having different [memory layouts][@stdlib/ndarray/orders], the output [ndarray][@stdlib/ndarray/ctor] has the [default order][@stdlib/ndarray/defaults].
-   **dim**: dimension along which to concatenate input [ndarrays][@stdlib/ndarray/ctor] (_optional_). Must be a negative integer. The index of the dimension along which to concatenate is resolved relative to the last dimension, with the last dimension corresponding to the value `-1`. Default: `-1`.

#### concat.assign( arrays, out\[, dim] )

Concatenates a list of ndarrays along a specified ndarray dimension and assigns results to an output ndarray.

```javascript
import array from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-array@deno/mod.js';
import zeros from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-zeros@deno/mod.js';
import ndarray2array from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-to-array@deno/mod.js';

var x = array( [ [ -1.0, 2.0 ], [ -3.0, 4.0 ] ] );
var y = array( [ [ -5.0, 6.0, -7.0 ], [ 8.0, -9.0, 10.0 ] ] );

var z = zeros( [ 2, 5 ] );

var out = concat.assign( [ x, y ], z, -1 );
// returns <ndarray>

var bool = ( out === z );
// returns true

var arr = ndarray2array( z );
// returns [ [ -1.0, 2.0, -5.0, 6.0, -7.0 ], [ -3.0, 4.0, 8.0, -9.0, 10.0 ] ]
```

The function accepts the following arguments:

-   **arrays**: a list of input [ndarrays][@stdlib/ndarray/ctor]. Must be [broadcast compatible][@stdlib/ndarray/base/broadcast-shapes] except for the dimension along which to concatenate. Must [promote][@stdlib/ndarray/promotion-rules] to a [data type][@stdlib/ndarray/dtypes] which can be (mostly) [safely cast][@stdlib/ndarray/mostly-safe-casts] to the [data type][@stdlib/ndarray/dtypes] of the output [ndarray][@stdlib/ndarray/ctor].
-   **out**: output [ndarray][@stdlib/ndarray/ctor].
-   **dim**: dimension along which to concatenate input [ndarrays][@stdlib/ndarray/ctor] (_optional_). Must be a negative integer. The index of the dimension along which to concatenate is resolved relative to the last dimension, with the last dimension corresponding to the value `-1`. Default: `-1`.

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

```javascript
import discreteUniform from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-array-discrete-uniform@deno/mod.js';
import ndarray from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-ctor@deno/mod.js';
import ndarray2array from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-to-array@deno/mod.js';
import concat from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-concat@deno/mod.js';

var xbuf = discreteUniform( 6, 0, 10, {
    'dtype': 'generic'
});
var x = new ndarray( 'generic', xbuf, [ 2, 3 ], [ 3, 1 ], 0, 'row-major' );
console.log( ndarray2array( x ) );

var ybuf = discreteUniform( 8, 0, 10, {
    'dtype': 'generic'
});
var y = new ndarray( 'generic', ybuf, [ 2, 4 ], [ 4, 1 ], 0, 'row-major' );
console.log( ndarray2array( y ) );

var out = concat( [ x, y ], -1 );
console.log( ndarray2array( out ) );
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ndarray-concat.svg
[npm-url]: https://npmjs.org/package/@stdlib/ndarray-concat

[test-image]: https://github.com/stdlib-js/ndarray-concat/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/ndarray-concat/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ndarray-concat/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ndarray-concat?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ndarray-concat.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ndarray-concat/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ndarray-concat/tree/deno
[deno-readme]: https://github.com/stdlib-js/ndarray-concat/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/ndarray-concat/tree/umd
[umd-readme]: https://github.com/stdlib-js/ndarray-concat/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/ndarray-concat/tree/esm
[esm-readme]: https://github.com/stdlib-js/ndarray-concat/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/ndarray-concat/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ndarray-concat/main/LICENSE

[@stdlib/ndarray/ctor]: https://github.com/stdlib-js/ndarray-ctor/tree/deno

[@stdlib/ndarray/dtypes]: https://github.com/stdlib-js/ndarray-dtypes/tree/deno

[@stdlib/ndarray/orders]: https://github.com/stdlib-js/ndarray-orders/tree/deno

[@stdlib/ndarray/defaults]: https://github.com/stdlib-js/ndarray-defaults/tree/deno

[@stdlib/ndarray/promotion-rules]: https://github.com/stdlib-js/ndarray-promotion-rules/tree/deno

[@stdlib/ndarray/mostly-safe-casts]: https://github.com/stdlib-js/ndarray-mostly-safe-casts/tree/deno

[@stdlib/ndarray/base/broadcast-shapes]: https://github.com/stdlib-js/ndarray-base-broadcast-shapes/tree/deno

</section>

<!-- /.links -->
