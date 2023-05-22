# build_my_react
Zenn の React を自作しようをやってみる

## ReactElement から JS までの変換過程

```jsx
  const element = <h1 title="foo">Hello</h1> // JSX で要素を作成
  const container = document.getElementById("root") // root DOM を取得して
  ReactDOM.render(element, container) // React要素をコンテナにレンダリング
```

**JSX は JS へ変換する必要があるので、Babel などで build する**

変換方法
```javascript
 const element = React.createElement(
  "h1", // タグ名
  { title: "foo" }, // props
  "Hello", // children
  // and more...
 )
```

React.createElement で引数のバリデーションとオブジェクトの作成が実行される

```javascript
  const element = {
    type: "h1",
    props: {
      title: "hoo",
      children: "Hello"
    }
  }
```

type は DOM ノードタイプを表す。HTML 要素を作成する際に document.createElement に渡す tagName。


[参考](https://zenn.dev/akatsuki/articles/a2cbd26488fa151b828b)
