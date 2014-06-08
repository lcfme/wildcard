# wildcard

Very simple wildcard matching, which is designed to provide the same
functionality that is found in the
[eve](https://github.com/adobe-webplatform/eve) eventing library.


[![NPM](https://nodei.co/npm/wildcard.png)](https://nodei.co/npm/wildcard/)

[![Build Status](https://img.shields.io/travis/DamonOehlman/wildcard.svg?branch=master)](https://travis-ci.org/DamonOehlman/wildcard) [![stable](https://img.shields.io/badge/stability-stable-green.svg)](https://github.com/badges/stability-badges) 

## Usage

It works with strings:

```js
var wildcard = require('wildcard');

console.log(wildcard('foo.*', 'foo.bar'));
// --> true

console.log(wildcard('foo.*', 'foo'));
// --> true

```

Arrays:

```js
var wildcard = require('wildcard');
var testdata = [
  'a.b.c',
  'a.b',
  'a',
  'a.b.d'
];

console.log(wildcard('a.b.*', testdata));
// --> ['a.b.c', 'a.b', 'a.b.d']

```

Objects (matching against keys):

```js
var wildcard = require('wildcard');
var testdata = {
  'a.b.c' : {},
  'a.b'   : {},
  'a'     : {},
  'a.b.d' : {}
};

console.log(wildcard('a.*.c', testdata));
// --> { 'a.b.c': {} }

```

While the library works in Node, if you are are looking for file-based
wildcard matching then you should have a look at:

<https://github.com/isaacs/node-glob>

## License(s)

### MIT

Copyright (c) 2014 Damon Oehlman <damon.oehlman@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
