---
id: 587d7b7e367417b2b2512b23
title: 使用 parseInt 函數
challengeType: 1
videoUrl: 'https://scrimba.com/c/cm83LSW'
forumTopicId: 301183
dashedName: use-the-parseint-function
---

# --description--

`parseInt()` 函數解析一個字符串返回一個整數。 下面是一個示例：

`var a = parseInt("007");`

上述函數將字符串 `007` 轉換爲整數 `7`。 如果字符串參數的第一個字符是字符串類型的，結果將不會轉換成數字，而是返回 `NaN`。

# --instructions--

在 `convertToInteger` 函數中使用 `parseInt()` 將字符串 `str` 轉換爲正數並返回。

# --hints--

`convertToInteger` 應該使用 `parseInt()` 函數

```js
assert(/parseInt/g.test(code));
```

`convertToInteger("56")` 應該返回一個數字

```js
assert(typeof convertToInteger('56') === 'number');
```

`convertToInteger("56")` 應該返回 56

```js
assert(convertToInteger('56') === 56);
```

`convertToInteger("77")`應該返回 77

```js
assert(convertToInteger('77') === 77);
```

`convertToInteger("JamesBond")`應該返回 `NaN`

```js
assert.isNaN(convertToInteger('JamesBond'));
```

# --seed--

## --seed-contents--

```js
function convertToInteger(str) {

}

convertToInteger("56");
```

# --solutions--

```js
function convertToInteger(str) {
  return parseInt(str);
}
```
