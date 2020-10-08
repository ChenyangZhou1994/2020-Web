# 2.3.1 Numbers

Dart 语言的 Number 有两种类型。

## 1.int

整数值不大于 64 位，具体取决于平台。

在 Dart VM 上，值的范围从 $-2^{63}$ 到 $2^{63} - 1$。

Dart 被编译为 JavaScript 时，使用 JavaScript numbers，值的范围从 $-2^{53}$ 到 $2^{53} - 1$。


## 2.double

64位（双精度）浮点数，依据 IEEE 754 标准。

int 和 double 都是 [num](https://api.dart.cn/stable/2.9.3/dart-core/num-class.html) 的亚类型。

num 类型包括基本运算 + ， - ，/ ，和 * ，以及 abs() ，ceil() ，和 floor() ，等函数方法。

如果 num 及其亚类型找不到你想要的方法， 尝试查找使用 [dart:math](https://api.dart.cn/stable/2.9.3/dart-math/dart-math-library.html) 库。

整数类型不包含小数点。

下面是定义整数类型字面量的例子：

Tips: var = **var**iable 变量

```javascript
var x = 1;
var hex = 0xDEADBEEF;
```

如果一个数字包含小数点，那么就是小数类型。

下面是定义小数类型字面量的例子：

```javascript
var y = 1.1;
var exponents = 1.42e5;
```

从 Dart 2.1 开始，必要的时候 int 字面量会自动转换成 double 类型。

```javascript
double z = 1; // 相当于 double z = 1.0.
```

<table><tr><td bgcolor=Cyan>版本提示： 在 2.1 之前，在 double 上下文中使用 int 字面量是错误的。
