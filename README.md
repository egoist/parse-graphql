# parse-graphql

[![NPM version](https://badgen.net/npm/v/parse-graphql)](https://npmjs.com/package/parse-graphql) [![NPM downloads](https://badgen.net/npm/dm/parse-graphql)](https://npmjs.com/package/parse-graphql) [![CircleCI](https://badgen.net/circleci/github/egoist/parse-graphql/master)](https://circleci.com/gh/egoist/parse-graphql/tree/master) [![donate](https://badgen.net/badge/support%20me/donate/ff69b4)](https://patreon.com/egoist) [![chat](https://badgen.net/badge/chat%20on/discord/7289DA)](https://chat.egoist.moe)

Given a GraphQL source, parses it into a Document.

Throws GraphQLError if a syntax error is encountered.

This module is basically a standalone version (70KB unminified) for `require('graphql').parse` (1.8MB).

## Install

```bash
yarn add parse-graphql
```

## Usage

```js
const { parse } = require('parse-graphql')

const document = parse(`{
  user {
    name
    id
  }
}`)
```

The `document` is:

```js
{
  kind: 'Document',
  definitions: [
    {
      kind: 'OperationDefinition',
      operation: 'query',
      name: undefined,
      variableDefinitions: [],
      directives: [],
      selectionSet: {
        kind: 'SelectionSet',
        selections: [
          {
            kind: 'Field',
            alias: undefined,
            name: { kind: 'Name', value: 'user', loc: { start: 4, end: 8 } },
            arguments: [],
            directives: [],
            selectionSet: {
              kind: 'SelectionSet',
              selections: [
                {
                  kind: 'Field',
                  alias: undefined,
                  name: {
                    kind: 'Name',
                    value: 'name',
                    loc: { start: 15, end: 19 }
                  },
                  arguments: [],
                  directives: [],
                  selectionSet: undefined,
                  loc: { start: 15, end: 19 }
                },
                {
                  kind: 'Field',
                  alias: undefined,
                  name: {
                    kind: 'Name',
                    value: 'id',
                    loc: { start: 24, end: 26 }
                  },
                  arguments: [],
                  directives: [],
                  selectionSet: undefined,
                  loc: { start: 24, end: 26 }
                }
              ],
              loc: { start: 9, end: 30 }
            },
            loc: { start: 4, end: 30 }
          }
        ],
        loc: { start: 0, end: 32 }
      },
      loc: { start: 0, end: 32 }
    }
  ],
  loc: { start: 0, end: 32 }
}
```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Author

**parse-graphql** © [EGOIST](https://github.com/egoist), Released under the [MIT](./LICENSE) License.<br>
Authored and maintained by EGOIST with help from contributors ([list](https://github.com/egoist/parse-graphql/contributors)).

> [github.com/egoist](https://github.com/egoist) · GitHub [@EGOIST](https://github.com/egoist)
