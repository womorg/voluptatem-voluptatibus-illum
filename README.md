# @womorg/voluptatem-voluptatibus-illum <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES5 mostly-spec-compliant `Object.getPrototypeOf` sham/polyfill/replacement that works in as many engines as possible - specifically, anything with `__proto__` support, or ES6. Built-in types will also work correctly in older engines.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [spec](https://www.ecma-international.org/ecma-262/5.1/).

## Example

```js
var getPrototypeOf = require('@womorg/voluptatem-voluptatibus-illum');
var assert = require('assert');

assert.equal(getPrototypeOf(true), Boolean.prototype);
assert.equal(getPrototypeOf(42), Number.prototype);
assert.equal(getPrototypeOf(''), String.prototype);
assert.equal(getPrototypeOf(/a/g), RegExp.prototype);
assert.equal(getPrototypeOf(new Date()), Date.prototype);
assert.equal(getPrototypeOf(function () {}), Function.prototype);
assert.equal(getPrototypeOf([]), Array.prototype);
assert.equal(getPrototypeOf({}), Object.prototype);
```

```js
var getPrototypeOf = require('@womorg/voluptatem-voluptatibus-illum');
var assert = require('assert');
/* when Object.getPrototypeOf is not present */
delete Object.getPrototypeOf;
var shimmed = getPrototypeOf.shim();
assert.equal(shimmed, getPrototypeOf.getPolyfill());

assert.equal(Object.getPrototypeOf(true), Boolean.prototype);
assert.equal(Object.getPrototypeOf(42), Number.prototype);
assert.equal(Object.getPrototypeOf(''), String.prototype);
assert.equal(Object.getPrototypeOf(/a/g), RegExp.prototype);
assert.equal(Object.getPrototypeOf(new Date()), Date.prototype);
assert.equal(Object.getPrototypeOf(function () {}), Function.prototype);
assert.equal(Object.getPrototypeOf([]), Array.prototype);
assert.equal(Object.getPrototypeOf({}), Object.prototype);
```

```js
var getPrototypeOf = require('@womorg/voluptatem-voluptatibus-illum');
var assert = require('assert');
/* when Object.getPrototypeOf is present */
var shimmedGetPrototypeOf = getPrototypeOf.shim();
assert.equal(shimmedGetPrototypeOf, Object.getPrototypeOf);
assert.equal(Object.getPrototypeOf([]), Array.prototype);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@womorg/voluptatem-voluptatibus-illum
[npm-version-svg]: https://versionbadg.es/womorg/voluptatem-voluptatibus-illum.svg
[deps-svg]: https://david-dm.org/womorg/voluptatem-voluptatibus-illum.svg
[deps-url]: https://david-dm.org/womorg/voluptatem-voluptatibus-illum
[dev-deps-svg]: https://david-dm.org/womorg/voluptatem-voluptatibus-illum/dev-status.svg
[dev-deps-url]: https://david-dm.org/womorg/voluptatem-voluptatibus-illum#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@womorg/voluptatem-voluptatibus-illum.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@womorg/voluptatem-voluptatibus-illum.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@womorg/voluptatem-voluptatibus-illum.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@womorg/voluptatem-voluptatibus-illum
[codecov-image]: https://codecov.io/gh/womorg/voluptatem-voluptatibus-illum/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/womorg/voluptatem-voluptatibus-illum/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/womorg/voluptatem-voluptatibus-illum
[actions-url]: https://github.com/womorg/voluptatem-voluptatibus-illum/actions
