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
            
            
## 数组的扩展
替代数组的 apply 方法

下面是扩展运算符取代apply方法的一个实际的例子，应用Math.max方法，简化求出一个数组最大元素的写法。


// ES5 的写法
Math.max.apply(null, [14, 3, 77])

// ES6 的写法
Math.max(...[14, 3, 77])

// 等同于
Math.max(14, 3, 77);

## 2.Array.from() 

Array.from方法用于将两类对象转为真正的数组：类似数组的对象（array-like object）和可遍历（iterable）的对象（包括ES6新增的数据结构Set和Map）。

下面是一个类似数组的对象，Array.from将它转为真正的数组。

let arrayLike = {
    '0': 'a',
    '1': 'b',
    '2': 'c',
    length: 3
};

// ES5的写法
var arr1 = [].slice.call(arrayLike); // ['a', 'b', 'c']

// ES6的写法
let arr2 = Array.from(arrayLike); // ['a', 'b', 'c']

实际应用中，常见的类似数组的对象是DOM操作返回的NodeList集合，以及函数内部的arguments对象。Array.from都可以将它们转为真正的数组。

// NodeList对象
let ps = document.querySelectorAll('p');
Array.from(ps).forEach(function (p) {
  console.log(p);
});

// arguments对象
function foo() {
  var args = Array.from(arguments);
  // ...
}


# 数组的解构赋值
ES6 允许按照一定模式，从数组和对象中提取值，对变量进行赋值，这被称为解构

let [a, b, c] = [1, 2, 3];


由于大括号被解释为代码块，所以如果箭头函数直接返回一个对象，必须在对象外面加上括号，否则会报错。
// 报错
let getTempItem = id => { id: id, name: "Temp" };

// 不报错
let getTempItem = id => ({ id: id, name: "Temp" });
