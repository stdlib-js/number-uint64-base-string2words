<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

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

# string2words

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Parse a string representation of a 64-bit unsigned integer into high and low 32-bit words.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

```javascript
import string2words from 'https://cdn.jsdelivr.net/gh/stdlib-js/number-uint64-base-string2words@esm/index.mjs';
```

You can also import the following named exports from the package:

```javascript
import { assign } from 'https://cdn.jsdelivr.net/gh/stdlib-js/number-uint64-base-string2words@esm/index.mjs';
```

#### string2words( str, radix )

Parses a string representation of a 64-bit unsigned integer into high and low 32-bit words.

```javascript
var w = string2words( '1234', 10 );
// returns [ 0, 1234 ]
```

The function returns an array containing two elements: a higher order word and a lower order word. The lower order word contains the less significant bits, while the higher order word contains the more significant bits.

#### string2words.assign( str, radix, out, stride, offset )

Parses a string representation of a 64-bit unsigned integer into high and low 32-bit words and assigns results to a provided output array.

```javascript
import Uint32Array from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-uint32@esm/index.mjs';

var out = new Uint32Array( 2 );
// returns <Uint32Array>[ 0, 0 ]

var w = string2words.assign( 'ffffffffffffffff', 16, out, 1, 0 );
// returns <Uint32Array>[ 4294967295, 4294967295 ]

var bool = ( w === out );
// returns true
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   The input string must be a valid representation of an unsigned 64-bit integer in the specified radix, containing no whitespace, sign symbols, or leading zeros.
-   If the provided string represents a value greater than `2^64-1` or the radix is invalid, then `0` is assigned to both high and low words.

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="module">

import string2words from 'https://cdn.jsdelivr.net/gh/stdlib-js/number-uint64-base-string2words@esm/index.mjs';

var w = string2words( '1234', 10 );
console.log( w );
// => [ 0, 1234 ]

w = string2words( 'abcd', 16 );
console.log( w );
// => [ 0, 43981 ]

w = string2words( '18446744073709551615', 10 );
console.log( w );
// => [ 4294967295, 4294967295 ]

w = string2words( '3w5e11264sgsf', 36 );
console.log( w );
// => [ 4294967295, 4294967295 ]

</script>
</body>
</html>
```

</section>

<!-- /.examples -->

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

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/number-uint64-base-string2words.svg
[npm-url]: https://npmjs.org/package/@stdlib/number-uint64-base-string2words

[test-image]: https://github.com/stdlib-js/number-uint64-base-string2words/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/number-uint64-base-string2words/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/number-uint64-base-string2words/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/number-uint64-base-string2words?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/number-uint64-base-string2words.svg
[dependencies-url]: https://david-dm.org/stdlib-js/number-uint64-base-string2words/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/number-uint64-base-string2words/tree/deno
[deno-readme]: https://github.com/stdlib-js/number-uint64-base-string2words/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/number-uint64-base-string2words/tree/umd
[umd-readme]: https://github.com/stdlib-js/number-uint64-base-string2words/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/number-uint64-base-string2words/tree/esm
[esm-readme]: https://github.com/stdlib-js/number-uint64-base-string2words/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/number-uint64-base-string2words/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/number-uint64-base-string2words/main/LICENSE

<!-- <related-links> -->

<!-- </related-links> -->

</section>

<!-- /.links -->
