# get-started-with-Apollo-Server

Minimal example that reproduces the bug

## Installation

```
npm i && node index.js
```

## Issue reproduction

Navigate to http://localhost:4000/, open the sandbox and type the following query:

```gql
query {
  books(first: "one", second: "two") {
    title
    author
  }
}
```

Hovering the second argument of the query shows the following error message:

```
Unknown argument "second" on field "Query.books".
```

## Explanation

This is happening when a query has more than one arguments and one of them is deprecated.

It is then removed from the schema in the Apollo Studio explorer.
