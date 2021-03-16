---
id: 56bbb991ad1ed5201cd392cf
title: 用函數編寫可重用代碼
challengeType: 1
videoUrl: 'https://scrimba.com/c/cL6dqfy'
forumTopicId: 18378
dashedName: write-reusable-javascript-with-functions
---

# --description--

在 JavaScript 中，我們可以把代碼的重複部分抽取出來，放到一個函數 （<dfn>functions</dfn>）中。

舉個例子：

```js
function functionName() {
  console.log("Hello World");
}
```

你可以通過函數名加上後面的小括號來調用（<dfn>invoke</dfn>）這個函數，就像這樣： `functionName();` 每次調用函數時，它都會在控制檯上打印消息 `Hello World`。 每次調用函數時，大括號之間的所有代碼都將被執行。

# --instructions--

<ol><li>先創建一個名爲 <code>reusableFunction</code> 的函數，這個函數可以打印 <code>"Hi World"</code> 到控制檯上。</li><li>然後調用這個函數。</li></ol>

# --hints--

`reusableFunction` 應該是一個函數。

```js
assert(typeof reusableFunction === 'function');
```

`reusableFunction` 應該將字符串 `Hi World` 輸出到控制檯。

```js
assert(hiWorldWasLogged);
```

在你定義 `reusableFunction` 之後記得調用它。

```js
assert(/^\s*reusableFunction\(\)\s*/m.test(code));
```

# --seed--

## --before-user-code--

```js
var logOutput = "";
var originalConsole = console;
var nativeLog = console.log;
var hiWorldWasLogged = false;
function capture() {
    console.log = function (message) {
        if(message === 'Hi World')  hiWorldWasLogged = true;
        if(message && message.trim) logOutput = message.trim();
        if(nativeLog.apply) {
          nativeLog.apply(originalConsole, arguments);
        } else {
          var nativeMsg = Array.prototype.slice.apply(arguments).join(' ');
          nativeLog(nativeMsg);
        }
    };
}

function uncapture() {
  console.log = nativeLog;
}

capture();
```

## --after-user-code--

```js
uncapture();

if (typeof reusableFunction !== "function") { 
  (function() { return "reusableFunction is not defined"; })();
} else {
  (function() { return logOutput || "console.log never called"; })();
}
```

## --seed-contents--

```js

```

# --solutions--

```js
function reusableFunction() {
  console.log("Hi World");
}
reusableFunction();
```
