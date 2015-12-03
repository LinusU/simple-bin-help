# simple-bin-help

> Simple help and sanity checks for Node CLI bin scripts

[![NPM][simple-bin-help-icon] ][simple-bin-help-url]

[![Build status][simple-bin-help-ci-image] ][simple-bin-help-ci-url]
[![dependencies][simple-bin-help-dependencies-image] ][simple-bin-help-dependencies-url]
[![devdependencies][simple-bin-help-devdependencies-image] ][simple-bin-help-devdependencies-url]
[![semantic-release][semantic-image] ][semantic-url]
[![standard](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](http://standardjs.com/)

## Install

    npm install --save simple-bin-help

## Use example

Imagine for example that your bin script needs at least a single string argument, like
this `my-tool "foo"`. Then we can output simple help like this

```js
#!/usr/bin/env node

require('simple-bin-help')({
  minArguments: 3,
  packagePath: __dirname + '/../package.json',
  help: 'use: my-tool <a string>'
});
```

## Api

Single options object, with the following properties

```js
var options = {
  noExit: true | false, // simple-bin-help by default calls process.exit
  help: 'help string',  // to display if invalid arguments
  minArguments: n,      // min number of arguments to check
  pkg: packageObject,   // package (or pkg) object or path for better message
  packagePath: 'path/to/package.json',
  onFail: fn            // user-supplied function to be called after help has been shown
};
require('simple-bin-help')(options);
```

If `noExit` is true, the call simply shows the error message if number of arguments is
invalid and returns a boolean result.

For more examples, see [examples/basic.js](examples/basic.js) file that calls the method
with several permutations.

## Bonus features

* Includes and calls the [update-notifier]() module by default.
* If passed `-h` or `--help` option, shows the help message.

### Small print

Author: Gleb Bahmutov &copy; 2015

* [@bahmutov](https://twitter.com/bahmutov)
* [glebbahmutov.com](http://glebbahmutov.com)
* [blog](http://glebbahmutov.com/blog/)

License: MIT - do anything with the code, but don't blame me if it does not work.

Spread the word: tweet, star on github, etc.

Support: if you find any problems with this module, email / tweet /
[open issue](https://github.com/bahmutov/simple-bin-help/issues) on Github

## MIT License

Copyright (c) 2015 Gleb Bahmutov

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the "Software"), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

[simple-bin-help-icon]: https://nodei.co/npm/simple-bin-help.png?downloads=true
[simple-bin-help-url]: https://npmjs.org/package/simple-bin-help
[simple-bin-help-ci-image]: https://travis-ci.org/bahmutov/simple-bin-help.png?branch=master
[simple-bin-help-ci-url]: https://travis-ci.org/bahmutov/simple-bin-help
[simple-bin-help-dependencies-image]: https://david-dm.org/bahmutov/simple-bin-help.png
[simple-bin-help-dependencies-url]: https://david-dm.org/bahmutov/simple-bin-help
[simple-bin-help-devdependencies-image]: https://david-dm.org/bahmutov/simple-bin-help/dev-status.png
[simple-bin-help-devdependencies-url]: https://david-dm.org/bahmutov/simple-bin-help#info=devDependencies
[semantic-image]: https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg
[semantic-url]: https://github.com/semantic-release/semantic-release
