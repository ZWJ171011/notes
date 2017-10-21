类:
            function Person(){}

        ES6:
            class Person{
                constructor(形参){
                    //一般初始化都放在这里。
                }
            }
            //键值对
            {
                name:name
            }
            {
                name
            }
            //函数
            {
                fn:function(){}
            }
            {
                fn(){

                }
            }
            
            
class Person { //class类，类的数据类型就是函数，类本身就指向构造函数。
//构造函数的prototype属性，在 ES6 的“类”上面继续存在。事实上，类的所有方法都定义在类的prototype属性上面。
        constructor(name,age,sex){
            this.name = name;
            this.age = age;
            this.sex = sex;
        }
        say(){
            alert(this.name);
        }
    }   
    
var p = new Person('邢永旺',80,'看着办');
    p.say();
    console.log(p);    
    
## 2.严格模式    
    类和模块的内部，默认就是严格模式，所以不需要使用use strict指定运行模式。只要你的代码写在类或模块之中，就只有严格模式可用。

考虑到未来所有的代码，其实都是运行在模块之中，所以 ES6 实际上把整个语言升级到了严格模式。
    
    
## constructor 方法
    constructor方法是类的默认方法，通过new命令生对象实例时，自动调用该方法。一个类必须有constructor方法，如果没有定义，一个空的constructor方法会被默认添加
    class Point{
        
    }
//等同于
class Point{
    constructor(){}
}

constructor方法默认返回实例对象（即this），完全可以指定返回另外一个对象。

class Foo {
  constructor() {
    return Object.create(null);
  }
}

new Foo() instanceof Foo  // instanceof 二元运算符

        实例化(对象)***  instanceof  构造函数

        左值是不是右值构造出来的  左值必须要为对象

        返回的是boolean值
// false
上面代码中，constructor函数返回一个全新的对象，结果导致实例对象不是Foo类的实例。

类必须使用new调用，否则会报错。这是它跟普通构造函数的一个主要区别，后者不用new也可以执行。
## 箭头函数
箭头函数:
            var fn2 = () => 10;

            var fn2 = (a,b) => a+b;

            var fn2 = (a,b) => {
                return a+b;
            };

        this永远（一辈子）跟父级走。

            var fn = function(){}