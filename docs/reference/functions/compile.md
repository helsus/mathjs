---
layout: default
---

# Function compile

Parse and compile an expression.
Returns a an object with a function `eval([scope])` to evaluate the
compiled expression.


## Syntax

```js
math.compile(expr)                       // returns one node
math.compile([expr1, expr2, expr3, ...]) // returns an array with nodes
```

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`expr` | String &#124; String[] &#124; Matrix |  The expression to be compiled

### Returns

Type | Description
---- | -----------
{eval: Function} &#124; Array.<{eval: Function}> | code An object with the compiled expression


## Examples

```js
var code = math.compile('sqrt(3^2 + 4^2)');
code.eval(); // 5

var scope = {a: 3, b: 4}
var code = math.compile('a * b'); // 12
code.eval(scope); // 12
scope.a = 5;
code.eval(scope); // 20

var nodes = math.compile(['a = 3', 'b = 4', 'a * b']);
nodes[2].eval(); // 12
```


## See also

[parse](parse.html),
[eval](eval.html)


<!-- Note: This file is automatically generated from source code comments. Changes made in this file will be overridden. -->