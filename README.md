# marked-ast

A modified version of [marked](https://github.com/chjj/marked) and [marked-ast](https://github.com/pdubroy/marked-ast) that can produce an abstract syntax tree for Markdown from a single js file.

*IMPORTANT* This fork of the project not set up to update from npm sources, I'll work on that later. I just needed a non-nodejs version of this for a project and thought someone else might find it useful.

## Usage

```js
//var marked = require('marked-ast');

var ast = marked.parse('_This is **Markdown**_, he said.');
var html = marked.render(ast);
```

The package is just a wrapper for `marked`, so the produced HTML should be identical (if it isn't it's a bug). The AST produced in the example would look like this:

```json
[
  {
    "type": "paragraph",
    "text": [
      {
        "type": "em",
        "text": [
          "This is ",
          {
            "type": "strong",
            "text": [ "Markdown" ]
          }
        ]
      },
      ", he said."
    ]
  }
]
```

## Development

Basic setup:

```bash
git clone https://github.com/elijahz/marked-ast.git
cd marked-ast
cp ./markedast.js ~/ProjectDir/markedast.js
```
