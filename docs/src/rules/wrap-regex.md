---
title: wrap-regex
layout: doc
edit_link: https://github.com/eslint/eslint/edit/main/docs/src/rules/wrap-regex.md
rule_type: layout
---

<!--FIXABLE-->

Requires regex literals to be wrapped.

When a regular expression is used in certain situations, it can end up looking like a division operator. For example:

```js
function a() {
    return /foo/.test("bar");
}
```

## Rule Details

This is used to disambiguate the slash operator and facilitates more readable code.

Example of **incorrect** code for this rule:

::: incorrect

```js
/*eslint wrap-regex: "error"*/

function a() {
    return /foo/.test("bar");
}
```

:::

Example of **correct** code for this rule:

::: correct

```js
/*eslint wrap-regex: "error"*/

function a() {
    return (/foo/).test("bar");
}
```

:::
