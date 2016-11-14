# mdast-util-to-string [![Build Status][build-badge]][build-status] [![Coverage Status][coverage-badge]][coverage-status] [![Chat][chat-badge]][chat]

Get the plain text content of an [MDAST][] node.

## Installation

[npm][]:

```bash
npm install mdast-util-to-string
```

## Usage

```js
var remark = require('remark');
var toString = require('mdast-util-to-string');

var tree = remark().parse('Some *emphasis*, **importance**, and `code`.');

console.log(toString(tree)); //=> 'Some emphasis, importance, and code.'
```

## API

### `toString(node)`

Get the text content of a node.

The algorithm checks `value` of `node`, then `alt`, and finally `title`.
If no value is found, the algorithm checks the children of `node` and
joins them (without spaces or newlines).

> This is not a markdown to plain-text library.
> Use [`strip-markdown`][strip-markdown] for that.

## License

[MIT][license] © [Titus Wormer][author]

<!-- Definitions -->

[build-badge]: https://img.shields.io/travis/wooorm/mdast-util-to-string.svg

[build-status]: https://travis-ci.org/wooorm/mdast-util-to-string

[coverage-badge]: https://img.shields.io/codecov/c/github/wooorm/mdast-util-to-string.svg

[coverage-status]: https://codecov.io/github/wooorm/mdast-util-to-string

[chat-badge]: https://img.shields.io/gitter/room/wooorm/remark.svg

[chat]: https://gitter.im/wooorm/remark

[license]: LICENSE

[author]: http://wooorm.com

[npm]: https://docs.npmjs.com/cli/install

[mdast]: https://github.com/wooorm/mdast

[strip-markdown]: https://github.com/wooorm/strip-markdown
