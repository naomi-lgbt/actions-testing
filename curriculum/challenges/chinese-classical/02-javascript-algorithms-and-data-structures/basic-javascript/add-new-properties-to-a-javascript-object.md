---
id: 56bbb991ad1ed5201cd392d2
title: 給 JavaScript 對象添加新屬性
challengeType: 1
videoUrl: 'https://scrimba.com/c/cQe38UD'
forumTopicId: 301169
dashedName: add-new-properties-to-a-javascript-object
---

# --description--

你也可以像更改屬性一樣給 JavaScript 對象添加屬性。

這裏展示瞭如何給 `ourDog` 添加一個屬性 `bark`：

`ourDog.bark = "bow-wow";`

或者

`ourDog["bark"] = "bow-wow";`

現在，當我們執行 `ourDog.bark` 時，我們就能得到他的叫聲，`bow-wow`。

例如：

```js
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};

ourDog.bark = "bow-wow";
```

# --instructions--

給 `myDog` 添加一個屬性 `bark` ，並將其設置爲狗的聲音，比如“woof“. 你可以使用點號表示法或方括號表示法來完成此挑戰。

# --hints--

你應該將屬性 `bark` 添加到 `myDog`。

```js
assert(myDog.bark !== undefined);
```

你不應該在 Setup 部分添加 `bark`。

```js
assert(!/bark[^\n]:/.test(code));
```

# --seed--

## --after-user-code--

```js
(function(z){return z;})(myDog);
```

## --seed-contents--

```js
// Setup
var myDog = {
  "name": "Happy Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};

// Only change code below this line
```

# --solutions--

```js
var myDog = {
  "name": "Happy Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};
myDog.bark = "Woof Woof";
```
