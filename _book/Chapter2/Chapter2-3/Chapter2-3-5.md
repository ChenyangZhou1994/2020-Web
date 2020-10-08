# 2.3.5 Maps

通常来说， Map 是用来关联 keys 和 values 的对象。

keys 和 values 可以是任何类型的对象。在一个 Map 对象中一个 key 只能出现一次。但是 value 可以出现多次。

Dart 中 Map 通过 Map 字面量和 Map 类型来实现。

通常来说，Map 是一个键值对相关的对象。

其中键和值都可以是任何类型的对象。每个 **键** 只能出现一次但是 **值** 可以重复出现多次。

Dart 中 Map 提供了 Map 字面量以及 Map 类型两种形式的 Map。

```javascript
var gifts = {
  // 键:    值
  'first': 'partridge',
  'second': 'turtledoves',
  'fifth': 'golden rings'
};

var nobleGases = {
  2: 'helium',
  10: 'neon',
  18: 'argon',
};
```

Tips:

Dart 将 gifts 变量的类型推断为 Map<String, String>，而降 nobleGases 的类型推断为 Map<int, String>。如果你向这两个 Map 对象中添加不正确的类型值，将导致运行时异常。你可以阅读 [类型推断](https://dart.cn/guides/language/type-system#type-inference) 获取更多相关信息。

你也可以使用 Map 的构造器创建 Map：

```javascript
var gifts = Map();
gifts['first'] = 'partridge';
gifts['second'] = 'turtledoves';
gifts['fifth'] = 'golden rings';

var nobleGases = Map();
nobleGases[2] = 'helium';
nobleGases[10] = 'neon';
nobleGases[18] = 'argon';
```

Tips:

这里为什么使用 Map() 而不是使用 new Map() 构造 Map 对象。因为从 Dart2 开始，构造对象的 new 关键字可以被省略掉。你可以查阅 [构造函数的使用](https://dart.cn/guides/language/language-tour#using-constructors) 获取更多相关信息。

向现有的 Map 中添加键值对与 JavaScript 的操作类似：

```javascript
var gifts = {'first': 'partridge'};
gifts['fourth'] = 'calling birds'; // 添加键值对 (Add a key-value pair)
```

从一个 Map 中获取一个值的操作也与 JavaScript 类似。

```javascript
var gifts = {'first': 'partridge'};
assert(gifts['first'] == 'partridge');
```

如果检索的 Key 不存在于 Map 中则会返回一个 null：

```javascript
var gifts = {'first': 'partridge'};
assert(gifts['fifth'] == null);
```

使用 .length 可以获取 Map 中键值对的数量：

```javascript
var gifts = {'first': 'partridge'};
gifts['fourth'] = 'calling birds';
assert(gifts.length == 2);
```

在一个 Map 字面量前添加 const 关键字可以创建一个 Map 编译时常量：

```javascript
final constantMap = const {
  2: 'helium',
  10: 'neon',
  18: 'argon',
};
// constantMap[2] = 'Helium'; // 取消注释将导致出错 (Uncommenting this causes an error).
```

从 Dart 2.3 Map 可以像 List 一样支持使用扩展操作符（... 和 ...?）以及 Collection If 和 Collection For 操作。你可以查阅 List 扩展操作符和 List 集合操作符获取更多相关信息。

你也可以查阅 [泛型](https://dart.cn/guides/language/language-tour#generics) 以及 Maps 获取更多相关信息。
