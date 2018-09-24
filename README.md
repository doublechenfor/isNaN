# isNaN
定义 NAN：全局属性 NaN 的值表示不是一个数字（Not-A-Number）。
判断一个数是不是NAN 等号运算符不能判断一个数是不是NAN（==/===均为false），必须用number.isNaN()或者isNaN()函数，在执行自比较之中：NaN，也只有NaN，比                    较之中不等于它自己。
                    NaN === NaN;        // false
                    Number.NaN === NaN; // false
                    isNaN(NaN);         // true
                    isNaN(Number.NaN);  // true
NaN的产生  当算术运算返回一个未定义的或无法表示的值时，NaN就产生了。但是，NaN并不一定用于表示某些值超出表示范围的情况。将某些不能强制转换为数值的非数值            转换为数值的时候，也会得到NaN。
           例如，0 除以0会返回NaN —— 但是其他数除以0则不会返回NaN。
           如果isNaN函数的参数不是Number类型， isNaN函数会首先尝试将这个参数转换为数值，然后才会对转换后的结果是否是NaN进行判断。
 Example：
              isNaN(NaN);       // true
              isNaN(undefined); // true
              isNaN({});        // true

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
        
