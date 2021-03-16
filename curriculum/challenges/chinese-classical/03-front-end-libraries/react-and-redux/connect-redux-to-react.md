---
id: 5a24c314108439a4d4036147
title: 連接 Redux 和 React
challengeType: 6
forumTopicId: 301426
dashedName: connect-redux-to-react
---

# --description--

你已經寫了`mapStateToProps()`、`mapDispatchToProps()` 兩個函數，現在可以用它們來把 `state` 和 `dispatch` 映射到 React 組件的 `props` 了。 React Redux 的 `connect` 方法可以完成這個任務。 此方法有 `mapStateToProps()`、`mapDispatchToProps()` 兩個可選參數， 它們是可選的，原因是你的組件可能僅需要訪問 `state` 但不需要分發任何 actions，反之亦然。

爲了使用此方法，需要傳入函數參數並在調用時傳入組件。 這種語法有些不尋常，如下所示：

`connect(mapStateToProps, mapDispatchToProps)(MyComponent)`

**注意：** 如果要省略 `connect` 方法中的某個參數，則應當用 `null` 替換這個參數。

# --instructions--

在編輯器上有兩個函數：`mapStateToProps()`、`mapDispatchToProps()`，還有一個叫 `Presentational` 的 React 組件。 用 `ReactRedux` 全局對象中的 `connect` 方法將此組件連接到 Redux，並立即在 `Presentational` 組件中調用， 把結果賦值給一個名爲 `ConnectedComponent` 的代表已連接組件的新 `const`。 大功告成，已成功把 React 連接到 Redux！ 嘗試更改任何一個 `connect` 參數爲 `null` 並觀察測試結果。

# --hints--

應渲染 `Presentational` 組件。

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(AppWrapper));
    return mockedComponent.find('Presentational').length === 1;
  })()
);
```

`Presentational` 組件應通過 `connect` 接收一個 `messages` 屬性。

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(AppWrapper));
    const props = mockedComponent.find('Presentational').props();
    return props.messages === '__INITIAL__STATE__';
  })()
);
```

`Presentational` 組件應通過 `connect` 接收一個 `submitNewMessage` 屬性。

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(AppWrapper));
    const props = mockedComponent.find('Presentational').props();
    return typeof props.submitNewMessage === 'function';
  })()
);
```

# --seed--

## --after-user-code--

```jsx
const store = Redux.createStore(
  (state = '__INITIAL__STATE__', action) => state
);
class AppWrapper extends React.Component {
  render() {
    return (
      <ReactRedux.Provider store = {store}>
        <ConnectedComponent/>
      </ReactRedux.Provider>
    );
  }
};
ReactDOM.render(<AppWrapper />, document.getElementById('root'))
```

## --seed-contents--

```jsx
const addMessage = (message) => {
  return {
    type: 'ADD',
    message: message
  }
};

const mapStateToProps = (state) => {
  return {
    messages: state
  }
};

const mapDispatchToProps = (dispatch) => {
  return {
    submitNewMessage: (message) => {
      dispatch(addMessage(message));
    }
  }
};

class Presentational extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <h3>This is a Presentational Component</h3>
  }
};

const connect = ReactRedux.connect;
// Change code below this line
```

# --solutions--

```jsx
const addMessage = (message) => {
  return {
    type: 'ADD',
    message: message
  }
};

const mapStateToProps = (state) => {
  return {
    messages: state
  }
};

const mapDispatchToProps = (dispatch) => {
  return {
    submitNewMessage: (message) => {
      dispatch(addMessage(message));
    }
  }
};

class Presentational extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <h3>This is a Presentational Component</h3>
  }
};

const connect = ReactRedux.connect;
// Change code below this line

const ConnectedComponent = connect(mapStateToProps, mapDispatchToProps)(Presentational);
```
