# 2.3.2 Strings

Dart 字符串是 UTF-16 编码的字符序列。可以使用单引号或者双引号来创建字符串：

Tips：UTF-16 是Unicode字符编码五层次模型的第三层：字符编码表（Character Encoding Form，也称为"storage format"）的一种实现方式。即把Unicode字符集的抽象码位映射为16位长的整数（即码元）的序列，用于数据存储或传递。Unicode字符的码位，需要1个或者2个16位长的码元来表示，因此这是一个变长表示。


```javascript
var s1 = 'Single quotes work well for string literals.';
var s2 = "Double quotes work just as well.";
var s3 = 'It\'s easy to escape the string delimiter.';
var s4 = "It's even easier to use the other delimiter.";

// 代码中文解释
var s1 = '使用单引号创建字符串字面量。';
var s2 = "双引号也可以用于创建字符串字面量。";
var s3 = '使用单引号创建字符串时可以使用斜杠来转义那些与单引号冲突的字符串：\'。';
var s4 = "而在双引号中则不需要使用转义与单引号冲突的字符串：'";
```

可以在字符串中以 ${表达式} 的形式使用表达式，如果表达式是一个标识符，可以省略掉 {}。如果表达式的结果为一个对象，则 Dart 会调用该对象的 toString 方法来获取一个字符串。

```javascript
var s = 'string interpolation';

assert('Dart has $s, which is very handy.' ==
    'Dart has string interpolation, ' +
        'which is very handy.');
assert('That deserves all caps. ' +
        '${s.toUpperCase()} is very handy!' ==
    'That deserves all caps. ' +
        'STRING INTERPOLATION is very handy!');

// 代码中文解释
var s = '字符串插值';

assert('Dart 有$s，使用起来非常方便。' == 'Dart 有字符串插值，使用起来非常方便。');
assert('使用${s.substring(3,5)}表达式也非常方便' == '使用插值表达式也非常方便。');
```

Tips：assert 断言。

assert() 的用法像是一种"契约式编程"，在我的理解中，其表达的意思就是，程序在我的假设条件下，能够正常良好的运作，其实就相当于一个 if 语句：

```c++
if(假设成立)
{
     程序正常运行；
}
else
{
      报错&&终止程序！（避免由程序运行引起更大的错误）  
}
```

但是这样写的话，就会有无数个 if 语句，甚至会出现，一个 if 语句的括号从文件头到文件尾，并且大多数情况下，我们要进行验证的假设，只是属于偶然性事件，又或者我们仅仅想测试一下，一些最坏情况是否发生，所以这里有了 assert()。

assert 宏的原型定义在 assert.h 中，其作用是如果它的条件返回错误，则终止程序执行。

assert 只有在 Debug 版本中才有效，如果编译为 Release 版本则被忽略。

Tips:

== 运算符判断两个对象的内容是否一样，如果两个字符串包含一样的字符编码序列，则表示相等。

可以使用 + 运算符将两个字符串连接为一个，也可以将多个字符串挨着放一起变为一个：

```javascript
var s1 = 'String '
    'concatenation'
    " works even over line breaks.";
assert(s1 ==
    'String concatenation works even over '
        'line breaks.');

var s2 = 'The + operator ' + 'works, as well.';
assert(s2 == 'The + operator works, as well.');

// 代码中文解释
var s1 = '可以拼接'
    '字符串'
    "即便它们不在同一行。";
assert(s1 == '可以拼接字符串即便它们不在同一行。');

var s2 = '使用加号 + 运算符' + '也可以达到相同的效果。';
assert(s2 == '使用加号 + 运算符也可以达到相同的效果。');
```

可以使用三个单引号或者三个双引号创建多行字符串：

```javascript
var s1 = '''
你可以像这样创建多行字符串。
''';

var s2 = """这也是一个多行字符串。""";
```

在字符串前加上 r 作为前缀创建 “raw” 字符串（即不会被做任何处理（比如转义）的字符串）：

```javascript
var s = r'In a raw string, not even \n gets special treatment.';

// 代码中文解释
var s = r'在 raw 字符串中，转义字符串 \n 会直接输出 “\n” 而不是转义为换行。';
```

你可以查阅 [Runes and grapheme clusters](https://dart.cn/guides/language/language-tour#runes-and-grapheme-clusters) 获取更多关于如何在字符串中表示 Unicode 字符的信息。

字符串字面量是一个编译时常量，只要是编译时常量都可以作为字符串字面量的插值表达式：

```javascript
// 可以将下面三个常量作为字符串插值拼接到字符串字面量中。(These work in a const string.)
const aConstNum = 0;
const aConstBool = true;
const aConstString = 'a constant string';

// 而下面三个常量则不能作为字符串插值拼接到字符串字面量。
var aNum = 0;
var aBool = true;
var aString = 'a string';
const aConstList = [1, 2, 3];

const validConstString = '$aConstNum $aConstBool $aConstString';
// const invalidConstString = '$aNum $aBool $aString $aConstList';
```

可以查阅 [字符串和正则表达式](https://dart.cn/guides/libraries/library-tour#strings-and-regular-expressions) 获取更多关于如何使用字符串的信息。
