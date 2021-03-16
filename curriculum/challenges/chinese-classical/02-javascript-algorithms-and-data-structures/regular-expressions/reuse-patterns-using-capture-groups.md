---
id: 587d7dbb367417b2b2512baa
title: 使用捕獲組重用模式
challengeType: 1
forumTopicId: 301364
dashedName: reuse-patterns-using-capture-groups
---

# --description--

一些你所搜尋的匹配模式會在字符串中出現多次， 手動重複該正則表達式顯得不夠簡潔。 當字符串中出現多個重複子字符串時，有一種更好的方式來編寫模式。

可以使用 <dfn>捕獲組</dfn> 搜尋重複的子字符串。 括號 `(` 和 `)` 可以用來匹配重複的子字符串。 把需要重複匹配的模式放在括號中即可。

要指定重複字符串將出現的位置，可以使用反斜槓（<code>\\</code>）後接一個數字。 這個數字從 1 開始，隨着你使用的每個捕獲組的增加而增加。 這裏有一個示例，`\1`可以匹配第一個組。

下面的示例展示的是匹配被空格隔開的兩個相同單詞：

```js
let repeatStr = "regex regex";
let repeatRegex = /(\w+)\s\1/;
repeatRegex.test(repeatStr); // Returns true
repeatStr.match(repeatRegex); // Returns ["regex regex", "regex"]
```

在字符串上調用 `.match()` 方法將返回一個數組，其中包含它最終匹配到的字符串及其捕獲組。

# --instructions--

Use capture groups in `reRegex` to match a string that consists of only the same number repeated exactly three times separated by single spaces.

# --hints--

你的正則表達式應該使用數字的簡寫字符類。

```js
assert(reRegex.source.match(/\\d/));
```

你的正則表達式應該使用兩次捕獲組。

```js
assert(reRegex.source.match(/\\1|\\2/g).length >= 2);
```

Your regex should match `"42 42 42"`.

```js
assert(reRegex.test('42 42 42'));
```

Your regex should match `"100 100 100"`.

```js
assert(reRegex.test('100 100 100'));
```

Your regex should not match `"42 42 42 42"`.

```js
assert.equal('42 42 42 42'.match(reRegex.source), null);
```

Your regex should not match `"42 42"`.

```js
assert.equal('42 42'.match(reRegex.source), null);
```

Your regex should not match `"101 102 103"`.

```js
assert(!reRegex.test('101 102 103'));
```

Your regex should not match `"1 2 3"`.

```js
assert(!reRegex.test('1 2 3'));
```

Your regex should match `"10 10 10"`.

```js
assert(reRegex.test('10 10 10'));
```

# --seed--

## --seed-contents--

```js
let repeatNum = "42 42 42";
let reRegex = /change/; // Change this line
let result = reRegex.test(repeatNum);
```

# --solutions--

```js
let repeatNum = "42 42 42";
let reRegex = /^(\d+)\s\1\s\1$/;
let result = reRegex.test(repeatNum);
```
