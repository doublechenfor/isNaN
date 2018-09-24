# isNaN
===
## 定义 NAN：全局属性 NaN 的值表示不是一个数字（Not-A-Number）。<br>
## 判断一个数是不是NAN 等号运算符不能判断一个数是不是NAN（==/===均为false），必须用number.isNaN()或者isNaN()函数，在执行自比较之中：NaN，也只有NaN，比较之中不等于它自己。<br> 
                    NaN === NaN;        // false<br> 
                    Number.NaN === NaN; // false<br> 
                    isNaN(NaN);         // true<br> 
                    isNaN(Number.NaN);  // true<br> 
## NaN的产生  当算术运算返回一个未定义的或无法表示的值时，NaN就产生了。但是，NaN并不一定用于表示某些值超出表示范围的情况。将某些不能强制转换为数值的非数值转换为数值的时候，也会得到NaN。<br> 
           例如，0 除以0会返回NaN —— 但是其他数除以0则不会返回NaN。<br> 
           如果isNaN函数的参数不是Number类型， isNaN函数会首先尝试将这个参数转换为数值，然后才会对转换后的结果是否是NaN进行判断。<br> 
 ## Example：<br> 
              isNaN(NaN);       // true<br> 
              isNaN(undefined); // true<br> 
              isNaN({});        // true<br> 

              isNaN(true);      // false
              isNaN(null);      // false
              isNaN(37);        // false

              // strings
              isNaN("37");      // false: 可以被转换成数值37
              isNaN("37.37");   // false: 可以被转换成数值37.37
              isNaN("37,5");    // true
              isNaN('123ABC');  // true:  parseInt("123ABC")的结果是 123, 但是Number("123ABC")结果是 NaN
              isNaN("");        // false: 空字符串被转换成0
              isNaN(" ");       // false: 包含空格的字符串被转换成0

              // dates
              isNaN(new Date());                // false
              isNaN(new Date().toString());     // true

              isNaN("blabla")   // true: "blabla"不能转换成数值
                                // 转换成数值失败， 返回NaN

# typeof
===
## 定义 typeof操作符返回一个字符串，表示未经计算的操作数的类型。
## 语法 typeof operand or typeof (operand)
## 描述 下表总结了typeof可能的返回值。有关类型和原始值的更多信息，可查看 JavaScript数据结构 页面。
类型	                                      结果<br> 
Undefined                             	"undefined"<br> 
Null	                                 "object"（见下文）<br> 
Boolean	                                 "boolean"<br> 
Number	                                  "number"<br> 
String	                                  "string"<br> 
Symbol （ECMAScript 6 新增）	             "symbol"<br> 
宿主对象（由JS环境提供）             	Implementation-dependent<br> 
函数对象（[[Call]] 在ECMA-262条款中实现了）	"function"<br> 
任何其他对象	                            "object"<br> 
## 示例
// Numbers
typeof 37 === 'number';
typeof 3.14 === 'number';
typeof Math.LN2 === 'number';
typeof Infinity === 'number';
typeof NaN === 'number'; // 尽管NaN是"Not-A-Number"的缩写
typeof Number(1) === 'number'; // 但不要使用这种形式!

// Strings
typeof "" === 'string';
typeof "bla" === 'string';
typeof (typeof 1) === 'string'; // typeof总是返回一个字符串
typeof String("abc") === 'string'; // 但不要使用这种形式!

// Booleans
typeof true === 'boolean';
typeof false === 'boolean';
typeof Boolean(true) === 'boolean'; // 但不要使用这种形式!

// Symbols
typeof Symbol() === 'symbol';
typeof Symbol('foo') === 'symbol';
typeof Symbol.iterator === 'symbol';

// Undefined
typeof undefined === 'undefined';
typeof declaredButUndefinedVariable === 'undefined';
typeof undeclaredVariable === 'undefined'; 

// Objects
typeof {a:1} === 'object';

// 使用Array.isArray 或者 Object.prototype.toString.call
// 区分数组,普通对象
typeof [1, 2, 4] === 'object';

typeof new Date() === 'object';

// 下面的容易令人迷惑，不要使用！
typeof new Boolean(true) === 'object';
typeof new Number(1) === 'object';
typeof new String("abc") === 'object';

// 函数
typeof function(){} === 'function';
typeof class C{} === 'function'
typeof Math.sin === 'function';
typeof new Function() === 'function';
### null
typeof null === 'object'; // 从一开始出现JavaScript就是这样的<br>
### new操作
// All constructor functions while instantiated with 'new' keyword will always be typeof 'object'
var str = new String('String');
var num = new Number(100);

typeof str; // It will return 'object'
typeof num; // It will return 'object'

// But there is a exception in case of Function constructor of Javascript

var func = new Function();

typeof func; // It will return 'function'
