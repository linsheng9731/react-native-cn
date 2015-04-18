A StyleSheet is an abstraction similar to CSS StyleSheets

Create a new StyleSheet:

```javascript
var styles = StyleSheet.create({
  container: {
    borderRadius: 4,
    borderWidth: 0.5,
    borderColor: '#d6d7da',
  },
  title: {
    fontSize: 19,
    fontWeight: 'bold',
  },
  activeTitle: {
    color: 'red',
  },
});
```

Use a StyleSheet:

```html
<View style={styles.container}>
  <Text style={[styles.title, this.props.isActive && styles.activeTitle]} />
</View>
```

Code quality:

* By moving styles away from the render function, you're making the code code easier to understand.
* Naming the styles is a good way to add meaning to the low level components in the render function.

Performance:

* Making a stylesheet from a style object makes it possible to refer to it by ID instead of creating a new style object every time.
* It also allows to send the style only once through the bridge. All subsequent uses are going to refer an id (not implemented yet).

## Methods 

static **create**(obj: {[key: string]: any})


StyleSheet 是一个和 CSS 样式很相似的概念。(官方称 native 实现了 css 的子集)

创建一个新的 StyleSheet:

```javascript
var styles = StyleSheet.create({
  container: {
    borderRadius: 4,
    borderWidth: 0.5,
    borderColor: '#d6d7da',
  },
  title: {
    fontSize: 19,
    fontWeight: 'bold',
  },
  activeTitle: {
    color: 'red',
  },
});
```

使用 StyleSheet:

```html
<View style={styles.container}>
  <Text style={[styles.title, this.props.isActive && styles.activeTitle]} />
</View>
```

代码质量:

* 通过将样式从 render 函数中移除，使代码变的更加易懂。
* 在 render 函数中，给样式命名以增加底层组件的字面意义可以增加代码可读性。

性能:

* 如果我们通过定义一个样式对象来获得 stylesheet,那么我们就可以通过 ID 引用 stylesheet,而不是每次都去产生一个新的样式对象。 
* 这样做的另一好处是允许 native 底层在通信的时候只发送一次样式对象，之后对相同样式的所有的请求都是通过 ID 引用同一个样式对象（目前还没实现）

## 方法 

static **create**(obj: {[key: string]: any}) 