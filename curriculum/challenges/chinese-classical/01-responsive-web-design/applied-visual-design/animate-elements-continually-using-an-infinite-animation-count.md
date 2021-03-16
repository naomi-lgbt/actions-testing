---
id: 587d78a8367417b2b2512ae3
title: 使用無限的動畫計數製作永不停止的動畫
challengeType: 0
videoUrl: 'https://scrimba.com/c/cVJDVfq'
forumTopicId: 301041
dashedName: animate-elements-continually-using-an-infinite-animation-count
---

# --description--

之前的關卡里介紹了一些動畫屬性以及 `@keyframes` 規則的用法。 還有一個常用的動畫屬性是 `animation-iteration-count`，這個屬性允許你控制動畫循環的次數。 下面是一個例子：

`animation-iteration-count: 3;`

在這種情況下，動畫將在運行 3 次後停止，但可以通過設置該值爲 `infinite` 來繼續運行動畫。

# --instructions--

把 `animation-iteration-count` 屬性值改成 `infinite`，以使右邊的球持續跳躍。

# --hints--

`animation-iteration-count` 屬性應有一個值 `infinite`。

```js
assert($('#ball').css('animation-iteration-count') == 'infinite');
```

# --seed--

## --seed-contents--

```html
<style>

  #ball {
    width: 100px;
    height: 100px;
    margin: 50px auto;
    position: relative;
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    animation-name: bounce;
    animation-duration: 1s;
    animation-iteration-count: 3;
  }

  @keyframes bounce{
    0% {
      top: 0px;
    }
    50% {
      top: 249px;
      width: 130px;
      height: 70px;
    }
    100% {
      top: 0px;
    }
  }
</style>
<div id="ball"></div>
```

# --solutions--

```html
<style>
  #ball {
    width: 100px;
    height: 100px;
    margin: 50px auto;
    position: relative;
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    animation-name: bounce;
    animation-duration: 1s;
    animation-iteration-count: infinite;
  }

  @keyframes bounce{
    0% {
      top: 0px;
    }
    50% {
      top: 249px;
      width: 130px;
      height: 70px;
    }
    100% {
      top: 0px;
    }
  }
</style>
<div id="ball"></div>
```
