<!--

@license Apache-2.0

Copyright (c) 2024 The Stdlib Authors.

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

# at3d

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Return an element from a three-dimensional nested array.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

```javascript
import at3d from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-at3d@v0.2.1-esm/index.mjs';
```

#### at3d( x, i0, i1, i2 )

Return an element from a three-dimensional nested array.

```javascript
var x = [ [ [ 1, 2 ], [ 3, 4 ] ] ];

var out = at3d( x, 0, 0, 1 );
// returns 2

out = at3d( x, 0, 1, 0 );
// returns 3
```

The function accepts the following arguments:

-   **x**: three-dimensional nested input array.
-   **i0**: first dimension index.
-   **i1**: second dimension index.
-   **i2**: third dimension index.

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   Negative indices are resolved relative to the last element along the respective dimension, with the last element corresponding to `-1`.
-   If provided out-of-bounds indices, the function always returns `undefined`.

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="module">

import papply from 'https://cdn.jsdelivr.net/gh/stdlib-js/utils-papply@esm/index.mjs';
var discreteUniform = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/random-base-discrete-uniform' ).factory;
import filled3dBy from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-filled3d-by@esm/index.mjs';
import ternary3d from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-ternary3d@esm/index.mjs';
import zeros3d from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-zeros3d@esm/index.mjs';
import at3d from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-at3d@v0.2.1-esm/index.mjs';

var shape = [ 3, 3, 3 ];

// Define a nested input array:
var x = filled3dBy( shape, discreteUniform( -100, 100 ) );
console.log( x );

// Define arrays containing random index values:
var i0 = filled3dBy( shape, discreteUniform( -shape[0], shape[0]-1 ) );
console.log( i0 );

var i1 = filled3dBy( shape, discreteUniform( -shape[1], shape[1]-1 ) );
console.log( i1 );

var i2 = filled3dBy( shape, discreteUniform( -shape[2], shape[2]-1 ) );
console.log( i2 );

// Define an output array:
var out = zeros3d( shape );
console.log( out );

// Fill the output array with randomly selected values from the input array:
ternary3d( [ i0, i1, i2, out ], shape, papply( at3d, x ) );
console.log( out );

</script>
</body>
</html>
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

Copyright &copy; 2016-2024. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/array-base-at3d.svg
[npm-url]: https://npmjs.org/package/@stdlib/array-base-at3d

[test-image]: https://github.com/stdlib-js/array-base-at3d/actions/workflows/test.yml/badge.svg?branch=v0.2.1
[test-url]: https://github.com/stdlib-js/array-base-at3d/actions/workflows/test.yml?query=branch:v0.2.1

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/array-base-at3d/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/array-base-at3d?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/array-base-at3d.svg
[dependencies-url]: https://david-dm.org/stdlib-js/array-base-at3d/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/array-base-at3d/tree/deno
[deno-readme]: https://github.com/stdlib-js/array-base-at3d/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/array-base-at3d/tree/umd
[umd-readme]: https://github.com/stdlib-js/array-base-at3d/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/array-base-at3d/tree/esm
[esm-readme]: https://github.com/stdlib-js/array-base-at3d/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/array-base-at3d/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/array-base-at3d/main/LICENSE

</section>

<!-- /.links -->
