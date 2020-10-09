# 2.2.3 Dart变量和常量

## 1.Dart 变量

  dart是一个强大的脚本类语言，可以不预先定义变量类型 ，自动会类型推倒

  dart中定义变量可以通过var关键字可以通过类型来申明变量

  如：
```javascript
    var str='this is var';

    String str='this is var';

    int str=123;
```

  注意： var 后就不要写类型 ，  写了类型 不要var   两者都写   var  a int  = 5;  报错

```javascript
void main(){

    var str='你好dart';

    var myNum=1234;

    print(str);

    print(myNum);


    字符串

      String str='你好dart';

      print(str);

    数字类型
      int myNum=12354;

      print(myNum);




  dart里面有类型校验

      var str='';

      str=1234;

      print(str);


      String str="2131242";

      print(str);


      int myNum=1243214;

      print(myNum);


}
```


## 2.Dart 常量

Dart 常量：   final 和 const修饰符  


    const值不变 一开始就得赋值

    final 可以开始不赋值 只能赋一次 ; 而final不仅有const的编译时常量的特性，最重要的它是运行时常量，并且final是惰性初始化，即在运行时第一次使用前才初始化


    永远不改量的量，请使用final或const修饰它，而不是使用var或其他变量类型。

```javascript
void main(){


  var str='this is a str';

  str='你好 str';

  print(str);


  int myNum=1234;

  myNum=4567;

  print(myNum);


const常量

  const PI=3.14159;

  PI=123.1243; //错误的写法 常量不可以修改

  print(PI);




final 常量

    final PI=3.14159;
    PI=124214.214124;   //错误写法
    print(PI);


    final a=new DateTime.now();

    print(a);   //2019-05-10 15:59:02.966122



    const a=new DateTime.now();   //报错了



  区别：final 可以开始不赋值 只能赋一次 ;
  而final不仅有const的编译时常量的特性，最重要的它是运行时常量，并且final是惰性初始化，即在运行时第一次使用前才初始化

}
```
