# 2.8.5 Dart中把类单独抽离成一个模块


Animal类

```javascript

class Animal{
  String _name;   //私有属性
  int age;
  //默认构造函数的简写
  Animal(this._name,this.age);

  void printInfo(){   
    print("${this._name}----${this.age}");
  }

  String getName(){
    return this._name;
  }
  void _run(){
    print('这是一个私有方法');
  }

  execRun(){
    this._run();  //类里面方法的相互调用
  }
}

```

Person类

```javascript

class Person{
  String name;
  int age;
  //默认构造函数的简写
  Person(this.name,this.age);

  Person.now(){
    print('我是命名构造函数');
  }

  Person.setInfo(String name,int age){
    this.name=name;
    this.age=age;
  }

  void printInfo(){   
    print("${this.name}----${this.age}");
  }
}


```

```javascript

import 'lib/Person.dart';

void main(){

  Person p1=new Person.setInfo('李四1',30);
  p1.printInfo();

}

```
