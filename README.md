# copy [![NPM version](https://img.shields.io/npm/v/copy.svg?style=flat)](https://www.npmjs.com/package/copy) [![NPM downloads](https://img.shields.io/npm/dm/copy.svg?style=flat)](https://npmjs.org/package/copy) [![Build Status](https://img.shields.io/travis/jonschlinkert/copy.svg?style=flat)](https://travis-ci.org/jonschlinkert/copy)

Copy files or directories using globs.

## Table of Contents

- [Install](#install)
- [Usage](#usage)
- [Examples](#examples)
- [API](#api)
- [CLI](#cli)
- [History](#history)
- [About](#about)
  * [Related projects](#related-projects)
  * [Contributing](#contributing)
  * [Building docs](#building-docs)
  * [Running tests](#running-tests)
  * [Author](#author)
  * [License](#license)

_(TOC generated by [verb](https://github.com/verbose/verb) using [markdown-toc](https://github.com/jonschlinkert/markdown-toc))_

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save copy
```

## Usage

```js
var copy = require('copy');
```

See the [API documentation](#api) for usage details and available methods.

## Examples

The main export is a function that takes:

* `src` - glob pattern or file path(s)
* `dest` - the destination directory
* `cb` - callback function

```js
copy('*.js', 'foo', function(err, files) {
  if (err) throw err;
  // `files` is an array of the files that were copied
});
```

**Usage with [gulp](http://gulpjs.com)**

In your project's gulpfile.js:

```js
var gulp = require('gulp');
var copy = require('copy');

gulp.task('default', function (cb) {
  copy('fixtures/*.txt', 'actual', cb);
});
```

## API

### [copy](index.js#L27)

Copy a filepath, vinyl file, array of files, or glob of files to the given destination `directory`, with `options` and callback function that exposes `err` and the array of vinyl files that are created by the copy operation.

**Params**

* `patterns` **{String|Object|Array}**: Filepath(s), vinyl file(s) or glob of files.
* `dir` **{String}**: Destination directory
* `options` **{Object|Function}**: or callback function
* `cb` **{Function}**: Callback function if no options are specified

**Example**

```js
copy('*.js', 'dist', function(err, file) {
  // exposes the vinyl `file` created when the file is copied
});
```

### [.copy.each](index.js#L79)

Copy an array of files to the given destination `directory`, with `options` and callback function that exposes `err` and the array of vinyl files that are created by the copy operation.

**Params**

* `files` **{Array}**: Filepaths or vinyl files.
* `dir` **{String}**: Destination directory
* `options` **{Object|Function}**: or callback function
* `cb` **{Function}**: Callback function if no options are specified

**Example**

```js
copy.each(['foo.txt', 'bar.txt', 'baz.txt'], 'dist', function(err, files) {
  // exposes the vinyl `files` created when the files are copied
});
```

### [.copy.one](index.js#L122)

Copy a single `file` to the given `dest` directory, using the specified options and callback function.

**Params**

* `file` **{String|Object}**: Filepath or vinyl file
* `dir` **{String}**: Destination directory
* `options` **{Object|Function}**: or callback function
* `cb` **{Function}**: Callback function if no options are specified

**Example**

```js
copy.one('foo.txt', 'dist', function(err, file) {
  if (err) throw err;
  // exposes the vinyl `file` that is created when the file is copied
});
```

## CLI

To use the CLI, install `copy` globally with the following command:

```js
$ npm install --global copy
```

This adds `copy` to your system path, allowing the `copy` command to be executed anywhere.

**CLI usage**

```sh
$ copy <patterns> <dir>
```

* `patterns`: glob pattern or array of file paths
* `dir`: destination directory

**Example**

Copy* all files with the `.js` extension to the `foo` directory

```sh
$ copy *.js foo
```

*Note that glob patterns may need to be wrapped in quotes depending on the shell you're using.

## History

**v0.2.0 - breaking changes**

* The API was changed in 0.2.0. please review the [API documentation](#api)

## About

### Related projects

* [expand-config](https://www.npmjs.com/package/expand-config): Expand tasks, targets and files in a declarative configuration. | [homepage](https://github.com/jonschlinkert/expand-config "Expand tasks, targets and files in a declarative configuration.")
* [expand-files](https://www.npmjs.com/package/expand-files): Expand glob patterns in a declarative configuration into src-dest mappings. | [homepage](https://github.com/jonschlinkert/expand-files "Expand glob patterns in a declarative configuration into src-dest mappings.")
* [expand-target](https://www.npmjs.com/package/expand-target): Expand target definitions in a declarative configuration. | [homepage](https://github.com/jonschlinkert/expand-target "Expand target definitions in a declarative configuration.")
* [expand-task](https://www.npmjs.com/package/expand-task): Expand and normalize task definitions in a declarative configuration. | [homepage](https://github.com/jonschlinkert/expand-task "Expand and normalize task definitions in a declarative configuration.")
* [export-files](https://www.npmjs.com/package/export-files): node.js utility for exporting a directory of files as modules. | [homepage](https://github.com/jonschlinkert/export-files "node.js utility for exporting a directory of files as modules.")
* [write](https://www.npmjs.com/package/write): Write files to disk, creating intermediate directories if they don't exist. | [homepage](https://github.com/jonschlinkert/write "Write files to disk, creating intermediate directories if they don't exist.")

### Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

### Building docs

_(This document was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme) (a [verb](https://github.com/verbose/verb) generator), please don't edit the readme directly. Any changes to the readme must be made in [.verb.md](.verb.md).)_

To generate the readme and API documentation with [verb](https://github.com/verbose/verb):

```sh
$ npm install -g verb verb-generate-readme && verb
```

### Running tests

Install dev dependencies:

```sh
$ npm install -d && npm test
```

### Author

**Jon Schlinkert**

* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

### License

Copyright © 2016, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT license](https://github.com/jonschlinkert/copy/blob/master/LICENSE).

***

_This file was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme), v0.1.30, on August 11, 2016._