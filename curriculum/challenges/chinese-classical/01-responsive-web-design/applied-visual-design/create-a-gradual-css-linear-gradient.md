---
id: 587d78a5367417b2b2512ad6
title: 創建一個 CSS 線性漸變
challengeType: 0
videoUrl: 'https://scrimba.com/c/cg4dpt9'
forumTopicId: 301047
dashedName: create-a-gradual-css-linear-gradient
---

# --description--

HTML 元素的背景色並不侷限於單色。 CSS 還爲我們提供了顏色漸變。 可通過 `background` 裏的 `linear-gradient()` 實現線性漸變， 以下是它的語法：

`background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...);`

第一個參數用來表明顏色漸變的初始方向。 它的值是一個角度，比如 `90deg` 代表水平漸變（從左到右），再比如 `45deg` 代表對角線方向的漸變（從左下到右上）。 後續的參數指定了漸變顏色的順序。

例如：

`background: linear-gradient(90deg, red, yellow, rgb(204, 204, 255));`

# --instructions--

使用 `linear-gradient()` 將 `div` 的 `background` 設置爲漸變色，漸變的起始角度爲 35 度，顏色從 `#CCFFFF` 過渡到 `#FFCCCC`。

# --hints--

`div` 元素應有一個指定方向和顏色的 `linear-gradient` 來設置 `background`。

```js
assert(
  $('div')
    .css('background-image')
    .match(
      /linear-gradient\(35deg, rgb\(204, 255, 255\), rgb\(255, 204, 204\)\)/gi
    )
);
```

# --seed--

## --seed-contents--

```html
<style>
  div {
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin: 50px auto;

  }

</style>

<div></div>
```

# --solutions--

```html
<style>
  div {
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin: 50px auto;
    background: linear-gradient(35deg, #CCFFFF, #FFCCCC);
  }
</style>
<div></div>
```
