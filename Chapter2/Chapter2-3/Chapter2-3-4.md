# 2.3.4 Lists

数组 Array 是几乎所有编程语言中最常见的集合类型，在 Dart 中数组由 [List](https://api.dart.cn/stable/2.9.3/dart-core/List-class.html) 对象表示。通常称之为 List。

Dart 中 List 字面量看起来与 JavaScript 中数组字面量一样。下面是一个 Dart List 的示例：

```javascript
var list = [1, 2, 3];
```

Tips:

这里 Dart 推断出 list 的类型为 List<int>，如果往该数组中添加一个非 int 类型的对象则会报错。你可以阅读 [类型推断](https://dart.cn/guides/language/type-system#type-inference) 获取更多相关信息。

List 的下标索引从 0 开始，第一个元素的下标为 0，最后一个元素的下标为 list.length - 1。你可以像 JavaScript 中的用法那样获取 Dart 中 List 的长度以及元素：

```javascript
var list = [1, 2, 3];
assert(list.length == 3);
assert(list[1] == 2);

list[1] = 1;
assert(list[1] == 1);
```

如果想要创建一个编译时常量的 List，在 List 字面量前添加 const 关键字即可：

```javascript
var constantList = const [1, 2, 3];
// constantList[1] = 1; // 取消注释将导致出错 (Uncommenting this causes an error.)
```

Dart 在 2.3 引入了 扩展操作符（...）和 null-aware 扩展操作符（...?），它们提供了一种将多个元素插入集合的简洁方法。

例如，你可以使用扩展操作符（...）将一个 List 中的所有元素插入到另一个 List 中：

```javascript
var list = [1, 2, 3];
var list2 = [0, ...list];
assert(list2.length == 4);
```

如果扩展操作符右边可能为 null ，你可以使用 null-aware 扩展操作符（...?）来避免产生异常：

```javascript
var list;
var list2 = [0, ...?list];
assert(list2.length == 1);
```



可以查阅[扩展操作符](https://github.com/dart-lang/language/blob/master/accepted/2.3/spread-collections/feature-specification.md)建议获取更多关于如何使用扩展操作符的信息。

Dart 在 2.3 还同时引入了 Collection If 和 Collection For，在构建集合时，可以使用条件判断（if）和循环（for）。

下面示例是使用 Collection If 来创建一个 List 的示例，它可能包含 3 个或 4 个元素：

```javascript
var nav = [
  'Home',
  'Furniture',
  'Plants',
  if (promoActive) 'Outlet'
];
```

下面示例是使用 Collection For 将列表中的元素修改后添加到另一个列表中的示例：

```javascript
var listOfInts = [1, 2, 3];
var listOfStrings = [
  '#0',
  for (var i in listOfInts) '#$i'
];
assert(listOfStrings[1] == '#1');
```

你可以查阅[集合中使用控制流建议](https://github.com/dart-lang/language/blob/master/accepted/2.3/control-flow-collections/feature-specification.md)获取更多关于使用 Collection If 和 Collection For 的细节内容和示例。

List 类中有许多用于操作 List 的便捷方法，你可以查阅[泛型](https://dart.cn/guides/language/language-tour#generics)和[集合](https://dart.cn/guides/libraries/library-tour#collections)获取更多与之相关的信息。
