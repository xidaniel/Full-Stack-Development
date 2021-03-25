# JavaScript

JavaScript == ECMAScript

new version: ECMAScript --> ES6

## 基本语法:

- 类似于java, 不要求每个语句以 ; 结尾,浏览器会自动加上

## 数据类型和变量

- Number

  ```javascript
  //JavaScript不区分整数和浮点数，统一用Number表示，以下都是合法的Number类型：
  
  123; // 整数123
  0.456; // 浮点数0.456
  1.2345e3; // 科学计数法表示1.2345x1000，等同于1234.5
  -99; // 负数
  NaN; // NaN表示Not a Number，当无法计算结果时用NaN表示
  Infinity; // Infinity表示无限大，当数值超过了JavaScript的Number所能表示的最大值时，就表示为Infinity
  
  ```

- String

  - Javascript 接受单引号和双引号

  - 如果String既包含 ' 又包含 " ,  可以用转义字符 \

    ```javascript
    'I\'m \"OK\"!';
    ```

  - 转义字符

    ```javascript
    \n    换行  
    \t    制表
    \\    转义到 \
    ```

  - 反引号表示多行字符 ES6

    ```javascript
    console.log(`多行
    字符串
    测试`)
    
    //
    多行
    字符串
    测试
    ```

  - 模版字符串链接 ES6

    ```javascript
    var name = '小明';
    var age = 20;
    console.log(`你好, ${name}, 你今年${age}岁了!`);
    ```

  - 基本操作

    | APIs          |                         |
    | ------------- | :---------------------- |
    | get length    | s.length                |
    | get char      | s[index]                |
    | to upper case | s.toUpperCase           |
    | to lower case | s.toLowerCase           |
    | get index     | s.indexOf("string")     |
    | substring     | s.substring(start, end) |

  

- array

  可以包含任意数据类型

  ```javascript
  var arr = [1, 2, 3.14, 'Hello', null, true];
  
  new Array(1,2,3)
  
  var arr = [1, 2, 3.14, 'Hello', null, true];
  
  arr[0]; // 返回索引为0的元素，即1
  arr[5]; // 返回索引为5的元素，即true
  arr[6]; // 索引超出了范围，返回undefined
  ```

  - 基本操作

    | APIs           |                       |
    | -------------- | :-------------------- |
    | get length     | arr.length            |
    | change length  | arr.length = 5        |
    | change element | arr[1] = 4            |
    | get index      | arr.indexOf(1)        |
    | sub array      | arr.slice(start, end) |
    | push/pop       | operate tail          |
    | unshift/shift  | operate head          |
    | sorting        | arr.sort()            |
    | reverse        | arr.reverse()         |
    | splice         | delete and add        |
    | concat         | merge two array       |
    | join           | arr.join('-')         |
    |                |                       |

- Object

  - 是一组由key-value组成的无序集合
  -  key只能是字符串,为解决这个问题,ES6引进了Map

  ```javascript
  var person = {
      name: 'Bob',
      age: 20,
      tags: ['js', 'web', 'mobile'],
      city: 'Beijing',
      hasCar: true,
      zipcode: null
  };
  
  person.name; // 'Bob'
  ```

  - iteration

    ```javascript
    for (var j in person) {
      console.log(j + ":" + person.j)
    }
    ```

  - 基本操作

    | APIs         |                               |      |      |      |      |
    | ------------ | :---------------------------: | ---- | ---- | ---- | ---- |
    | delete       |       delete person.age       |      |      |      |      |
    | update       |        person.age = 18        |      |      |      |      |
    | contains     |       "name" in person        |      |      |      |      |
    | contains own | person.hasOwnProperty("name") |      |      |      |      |

- Map & Set

  - Map

    ```javascript
    //初始化Map需要一个二维数组，或者直接初始化一个空Map。
    var m = new Map([['Michael', 95], ['Bob', 75], ['Tracy', 85]]);
    m.get('Michael'); // 95
    
    var m = new Map(); // 空Map
    m.set('Adam', 67); // 添加新的key-value
    m.set('Bob', 59);
    m.has('Adam'); // 是否存在key 'Adam': true
    m.get('Adam'); // 67
    m.delete('Adam'); // 删除key 'Adam'
    m.get('Adam'); // undefined
    
    //由于一个key只能对应一个value，所以，多次对一个key放入value，后面的值会把前面的值冲掉：
    var m = new Map();
    m.set('Adam', 67);
    m.set('Adam', 88);
    m.get('Adam'); // 88
    ```

  - Set

    ```javascript
    //要创建一个Set，需要提供一个Array作为输入，或者直接创建一个空Set
    var s1 = new Set(); // 空Set
    var s2 = new Set([1, 2, 3]); // 含1, 2, 3
    
    //add
    s.add(4);
    s; // Set {1, 2, 3, 4}
    s.add(4);
    s; // 仍然是 Set {1, 2, 3, 4}
    
    //delete
    var s = new Set([1, 2, 3]);
    s; // Set {1, 2, 3}
    s.delete(3);
    s; // Set {1, 2}
    
    ```

    

- Iterable

  - Array,Map,Set都可以用 **for....of** 来循环

    ```javascript
    var a = ['A', 'B', 'C'];
    var s = new Set(['A', 'B', 'C']);
    var m = new Map([[1, 'x'], [2, 'y'], [3, 'z']]);
    for (var x of a) { // 遍历Array
        console.log(x);
    }
    for (var x of s) { // 遍历Set
        console.log(x);
    }
    for (var x of m) { // 遍历Map
        console.log(x[0] + '=' + x[1]);
    }
    ```

  - forEach 

    - 它接收一个函数，每次迭代就自动回调该函数

    ```javascript
    var a = ['A', 'B', 'C'];
    a.forEach(function (element, index, array) {
        // element: 指向当前元素的值
        // index: 指向当前索引
        // array: 指向Array对象本身
        console.log(element + ', index = ' + index);
    });
    ```

    ```javascript
    //Set没有索引，因此回调函数的前两个参数都是元素本身：
    var s = new Set(['A', 'B', 'C']);
    s.forEach(function (element, sameElement, set) {
        console.log(element);
    });
    ```

    ```javascript
    //Map的回调函数参数依次为value、key和map
    var m = new Map([[1, 'x'], [2, 'y'], [3, 'z']]);
    m.forEach(function (value, key, map) {
        console.log(value);
    });
    ```

    - 如果对某些参数不感兴趣，由于JavaScript的函数调用不要求参数必须一致，因此可以忽略,但是在参数列表中位置左侧的参数不能省略。例如，只需要获得`Array`的`element`：

      ```javascript
      var a = ['A', 'B', 'C'];
      a.forEach(function (element) {
          console.log(element);
      });
      ```

      

- Variable

  ```javascript
  //不能用数字开头
  //变量本身不固定,所以为动态语言,Java是静态语言
  // var 声明变量意思是:这个变量为局部变量
  var a; // 申明了变量a，此时a的值为undefined
  var $b = 1; // 申明了变量$b，同时给$b赋值，此时$b的值为1
  var s_007 = '007'; // s_007是一个字符串
  var Answer = true; // Answer是一个布尔值true
  var t = null; // t的值是null
  ```

- Print

  ```javascript
  console.log(x) //直接打印
  alert(x)//弹出对话框
  ```

## 函数

- JavaScript的函数也是一个对象，上述定义的`abs()`函数实际上是一个函数对象，而函数名`abs`可以视为指向该函数的变量

  ```javascript
  //标准定义函数
  function abs(x) {
      if (x >= 0) {
          return x;
      } else {
          return -x;
      }
  }
  
  //第二种定义方法, 末尾必须加 ;
  var abs = function (x) {
      if (x >= 0) {
          return x;
      } else {
          return -x;
      }
  };
  ```

- 由于JavaScript允许传入**任意个参数**而不影响调用，因此传入的参数比定义的参数**多或者少**也都没有问题，虽然函数内部并不需要这些参数

- 利用`arguments`，你可以获得调用者传入的所有参数

  ```javascript
  function abs() {
      if (arguments.length === 0) {
          return 0;
      }
      var x = arguments[0];
      return x >= 0 ? x : -x;
  }
  
  abs(); // 0
  abs(10); // 10
  abs(-9); // 9
  ```

- 利用`rest`，你可以获得额外剩余的参数, rest参数只能写在最后

- return 语句

  ```javascript
  function foo() {
      return { // 这里不会自动加分号，因为{表示语句尚未结束
          name: 'foo'
      };
  }
  ```

- 命名空间

  ```javascript
  //把自己的代码全部放入唯一的名字空间MYAPP中，会大大减少全局变量冲突的可能。许多著名的JavaScript库都是这么干的：jQuery，YUI，underscore等等。
  
  // 唯一的全局变量MYAPP:
  var MYAPP = {};
  
  // 其他变量:
  MYAPP.name = 'myapp';
  MYAPP.version = 1.0;
  
  // 其他函数:
  MYAPP.foo = function () {
      return 'foo';
  };
  ```

- 常量和变量

  - const
  - let var

- 解构赋值

  ```javascript
  var [x, y, z] = ['hello', 'JavaScript', 'ES6'];
  ```

- 方法

  - 声明在object内部的函数叫做方法

    ```javascript
    var xiaoming = {
        name: '小明',
        birth: 1990,
        age: function () {
            var y = new Date().getFullYear();
            return y - this.birth;
        }
    };
    
    xiaoming.age; // function xiaoming.age()
    xiaoming.age(); // 今年调用是25,明年调用就变成26了
    ```

- sort

  - 排序是根据ASCII的大小比较进行排序,注意大小写

  - 会把数字转为字符串再排序,所以通过以下方式对数字进行排序

    ```javascript
    arr.sort(function (x, y) {
        if (x < y) {
            return -1;
        }
        if (x > y) {
            return 1;
        }
        return 0;
    });
    console.log(arr); // [1, 2, 10, 20]
    ```

- forEach

  - 遍历数组

    ```javascript
    var arr = ['Apple', 'pear', 'orange'];
    arr.forEach(console.log); // 依次打印每个元素
    ```

- 箭头函数Arrow Function

  ```javascript
  x => x * x
  
  function (x) {
      return x * x;
  }
  
  //如果参数不是一个就需要用`()``括起来
  
  // 两个参数:
  (x, y) => x * x + y * y
  
  // 无参数:
  () => 3.14
  
  // 可变参数:
  (x, y, ...rest) => {
      var i, sum = x + y;
      for (i=0; i<rest.length; i++) {
          sum += rest[i];
      }
      return sum;
  }
  
  //如果要返回一个对象，就要注意
  x => ({ foo: x })
  
  //sort
  arr.sort((x, y) => {
      return x - y;
  });
  ```

## 标准对象

- Date

  ```javascript
  var now = new Date();
  now; // Wed Jun 24 2015 19:49:22 GMT+0800 (CST)
  now.getFullYear(); // 2015, 年份
  now.getMonth(); // 5, 月份，注意月份范围是0~11，5表示六月
  now.getDate(); // 24, 表示24号
  now.getDay(); // 3, 表示星期三
  now.getHours(); // 19, 24小时制
  now.getMinutes(); // 49, 分钟
  now.getSeconds(); // 22, 秒
  now.getMilliseconds(); // 875, 毫秒数
  now.getTime(); // 1435146562875, 以number形式表示的时间戳
  ```

- RegExp
  - `\d`可以匹配一个数字，`\w`可以匹配一个字母或数字
  - `.`可以匹配任意字符
  - 用`*`表示任意个字符（包括0个）
  - `\s`可以匹配一个空格（也包括Tab等空白符）
  - 用`+`表示至少一个字符，用`?`表示0个或1个字符，用`{n}`表示n个字符，用`{n,m}`表示n-m个字符

- **JSON**

  - 有以下几种数据类型

    - number：和JavaScript的`number`完全一致；
    - boolean：就是JavaScript的`true`或`false`；
    - string：就是JavaScript的`string`；必须用`""`
    - null：就是JavaScript的`null`；
    - array：就是JavaScript的`Array`表示方式——`[]`；
    - object：就是JavaScript的`{ ... }`表示方式。

  - 如果我们收到一个JSON格式的字符串，只需要把它反序列化成一个JavaScript对象，就可以在JavaScript中直接使用这个对象了

    ```javascript
    //把对象序列化成JSON格式
    //input:
    var xiaoming = {
        name: '小明',
        age: 14,
        gender: true,
        height: 1.65,
        grade: null,
        'middle-school': '\"W3C\" Middle School',
        skills: ['JavaScript', 'Java', 'Python', 'Lisp']
    };
    
    //序列化
    var s = JSON.stringify(xiaoming, null, '   ');
    
    //output:
    {
      "name": "小明",
      "age": 14,
      "gender": true,
      "height": 1.65,
      "grade": null,
      "middle-school": "\"W3C\" Middle School",
      "skills": [
        "JavaScript",
        "Java",
        "Python",
        "Lisp"
      ]
    }
    ```

    ```javascript
    //第二个参数用于控制如何筛选对象的键值，如果我们只想输出指定的属性，可以传入Array
    JSON.stringify(xiaoming, ['name', 'skills'], '  ');
    
    //output
    {
      "name": "小明",
      "skills": [
        "JavaScript",
        "Java",
        "Python",
        "Lisp"
      ]
    }
    ```

    ```javascript
    //还可以传入一个函数，这样对象的每个键值对都会被函数先处理：
    function convert(key, value) {
        if (typeof value === 'string') {
            return value.toUpperCase();
        }
        return value;
    }
    
    JSON.stringify(xiaoming, convert, '  ');
    ```

  - 反序列化

    ```javascript
    //拿到一个JSON格式的字符串，我们直接用JSON.parse()把它变成一个JavaScript对象：
    
    JSON.parse('[1,2,3,true]'); // [1, 2, 3, true]
    JSON.parse('{"name":"小明","age":14}'); // Object {name: '小明', age: 14}
    JSON.parse('true'); // true
    JSON.parse('123.45'); // 123.45
    
    //JSON.parse()还可以接收一个函数，用来转换解析出的属性
    
    var obj = JSON.parse('{"name":"小明","age":14}', function (key, value) {
        if (key === 'name') {
            return value + '同学';
        }
        return value;
    });
    console.log(JSON.stringify(obj)); // {name: '小明同学', age: 14}
    ```

    

  