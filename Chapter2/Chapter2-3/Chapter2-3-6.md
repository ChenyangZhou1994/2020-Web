# 2.3.6 Sets

在 Dart 中，set 是一组特定元素的无序集合。 Dart 所支持的 set 由 set literals 和 [Set](https://api.dart.cn/stable/2.9.3/dart-core/Set-class.html) 类所提供。

Tips:

尽管 Set 类型(type) 一直都是 Dart 的一项核心功能，但是 Set 字面量(literals) 却是在 Dart2.2 中才加入的。

下面是使用 Set 字面量来创建一个 Set 集合的方法：

```javascript
var halogens = {'fluorine', 'chlorine', 'bromine', 'iodine', 'astatine'};
```

Tips：

Dart 推断 halogens 变量是一个 Set<String> 类型的集合，如果往该 Set 中添加类型不正确的对象则会报错。你可以查阅 [类型推断](https://dart.cn/guides/language/type-system#type-inference) 获取更多与之相关的内容。

可以使用在 {} 前加上类型参数的方式创建一个空的 Set，或者将 {} 赋值给一个 Set 类型的变量：

```javascript
var names = <String>{}; // 类型+{}的形式创建Set。
// Set<String> names = {}; // 声明类型变量的形式创建 Set (This works, too).
// var names = {}; // 这样的形式将创建一个 Map 而不是 Set (Creates a map, not a set.)
```

Tips：Set 还是 map ?

Map 字面量语法同 Set 字面量语法非常相似。因为先有的 Map 字面量语法，所以 {} 默认是 Map 类型。如果忘记在 {} 上注释类型或赋值到一个未声明类型的变量上，那么 Dart 会创建一个类型为 Map<dynamic, dynamic> 的对象。


向一个已存在的 Set 中添加项目可以使用 add() 方法或 addAll() 方法：

```javascript
var elements = <String>{};
elements.add('fluorine');
elements.addAll(halogens);
```

使用 .length 可以获取 Set 中元素的数量：

```javascript
var elements = <String>{};
elements.add('fluorine');
elements.addAll(halogens);
assert(elements.length == 5);
```

可以在 Set 字面量前添加 const 关键字创建一个 Set 编译时常量：

```javascript
final constantSet = const {
  'fluorine',
  'chlorine',
  'bromine',
  'iodine',
  'astatine',
};
// constantSet.add('helium'); // 取消注释将导致出错 (Uncommenting this causes an error).
```

从 Dart 2.3 开始，Set 可以像 List 一样支持使用扩展操作符（... 和 ...?）以及 Collection If 和 Collection For 操作。你可以查阅 List 扩展操作符 和 List 集合操作符 获取更多相关信息。

你也可以查阅 [泛型](https://dart.cn/guides/language/language-tour#generics) 以及 Set 获取更多相关信息。
