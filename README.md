# JavaScript-Senior
###  JavaScript 高阶

1. JavaScript 的核心 ECMAScript 描述了该语言的语法和基本对象
                     DOM 描述了处理网页内容的方法和接口
                     BOM 描述了与浏览器进行交互的方法和接口

2. 语法
    2-1）ECMAScript 中的变量无特定的类型，定义变量时只用 var 运算符
    可以将它初始化为任意值
    命名变量需要遵守以下规则：
        a 第一个字符必须是字母、下划线（_）或美元符号（$）
        b 余下的字符可以是下划线、美元符号或任何字母或数字字符
        c Camel 标记法  Pascal 标记法
    每行结尾的分号可有可无
    有两种类型的注释：
        单行注释以双斜杠开头（//）
        多行注释以单斜杠和星号开头（/*），以星号和单斜杠结尾（*/）
    括号表示代码块（）{}


    2-2）关键字
    break  case  catch  continue  default  delete
    do  else  finally  for
    function  if  in  instanceof  new  return
    switch  this  throw  try  typeof
    var  void  while  with


    2-3）保留字
    保留字在某种意思上是为将来的关键字而保留的单词
    因此保留字不能被用作变量名或函数名
    如： abstract boolean byte char class debugger enum 等
    

    2-4）原始值和引用值
    在 ECMAScript 中，变量可以存在两种类型的值，即原始值和引用值
    原始值：存储在栈（stack）中的简单数据段
    也就是说，它们的值直接存储在变量访问的位置

    引用值
    存储在堆（heap）中的对象
    即存储在变量处的值是一个指针（point），指向存储对象的内存处


    2-5）原始类型
    ECMAScript 有 5 种原始类型（primitive type）
    即 Undefined、Null、Boolean、Number 和 String
    typeof 运算符来判断一个值是否在某种类型的范围内及类型判断


    2-6）类型转换
    arrayObject.toString()
    <script type="text/javascript">
    var arr = new Array(3)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"
    document.write(arr.toString())
    </script>

    booleanObject.toString()
    <script type="text/javascript">
    var boo = new Boolean(true)
    document.write(boo.toString())
    </script>

    2-6-1）转换成数字
    ECMAScript 提供了两种把非数字的原始值转换成数字的方法
    即 parseInt() 和 parseFloat()
    var iNum1 = parseInt("12345red");	//返回 12345
    var iNum1 = parseInt("0xA");	    //返回 10
    var iNum1 = parseInt("56.9");	    //返回 56
    var iNum1 = parseInt("red");	    //返回 NaN
    var iNum1 = parseInt("AF", 16);	    //返回 175


    2-6-2）强制类型转换
    ECMAScript 中可用的 3 种强制类型转换如下：
        Boolean(value) - 把给定的值转换成 Boolean 型
        Number(value) -  把给定的值转换成数字（可以是整数或浮点数）
        String(value) -  把给定的值转换成字符串

    var b1 = Boolean(50);		//true - 非零数字
    var b1 = Boolean(null);		//false - null      
    var s1 = String(null);	    //"null"
    var oNull = null;
    var s2 = oNull.toString();	//会引发错误


    2-7）引用类型
    引用类型通常叫做类（class）

    2-7-1）Object 对象具有下列属性：
        constructor
        对创建对象的函数的引用（指针）对于Object对象，该指针指向原始 Object() 函数

        Prototype
        对该对象的对象原型的引用。对于所有的对象，它默认返回 Object 对象的一个实例

    2-7-2）Object 对象还具有几个方法：
        hasOwnProperty(property)
        判断对象是否有某个特定的属性，必须用字符串指定该属性
        （例如，o.hasOwnProperty("name")）

        IsPrototypeOf(object)
        判断该对象是否为另一个对象的原型
        PropertyIsEnumerable
        判断给定的属性是否可以用 for...in 语句进行枚举

        ToString()
        返回对象的原始字符串表示。对于 Object 对象，ECMA-262 没有定义这个值
        所以不同的 ECMAScript 实现具有不同的值

        ValueOf()
        返回最适合该对象的原始值，对于许多对象，该方法返回的值都与 ToString() 的返回值相同

    2-7-3）Boolean 对象
    var oBooleanObject = new Boolean(true);

    2-7-4）Number 对象
    var oNumberObject = new Number(68);

    Number 对象处理数值的专用方法
        toFixed() 方法返回是具有指定位数小数的数字的字符串表示
        var oNumberObject = new Number(68);
        alert(oNumberObject.toFixed(2));    //输出 "68.00"，2位小数

        toExponential()返回的是用科学计数法表示的数字的字符串形式
        alert(oNumberObject.toExponential(1));  //输出 "6.8e+1"

        toPrecision() 方法根据最有意义的形式来返回数字的预定形式或指数形式
        它有一个参数，即用于表示数的数字总数（不包括指数）
        alert(oNumberObject.toPrecision(1));  //输出 "7e+1"
        alert(oNumberObject.toPrecision(2));  //输出 "68"
        alert(oNumberObject.toPrecision(3));  //输出 "68.0"


    2-7-5）String 对象
    var oStringObject = new String("hello world");
    alert(oStringObject.valueOf() == oStringObject.toString());	
    //输出 "true"


    2-7-6）length 属性
    var oStringObject = new String("hello world");
    alert(oStringObject.length);	//输出 "11"


    2-7-7）charAt() 和 charCodeAt() 方法
    访问的都是字符串中的单个字符，两个方法都有一个参数，即要操作的字符的位置
    var oStringObject = new String("hello world");
    alert(oStringObject.charAt(1));	    //输出 "e"
    alert(oStringObject.charCodeAt(1));	//输出 "101"


    2-7-8）concat() 方法
    把一个或多个字符串连接到 String 对象的原始值上，
    该方法返回的是 String 原始值，保持原始的 String 对象不变
    var oStringObject = new String("hello ");
    var sResult = oStringObject.concat("world");
    // var sResult = oStringObject + "world";
    alert(sResult);		    //输出 "hello world"
    alert(oStringObject);	//输出 "hello "


    2-7-9）indexOf() 和 lastIndexOf() 方法
    返回的都是指定的子串在另一个字符串中的位置，如果没有找不到子串，则返回 -1
    前者从字符串的开头（位置 0）开始检索
    lastIndexOf() 方法则是从字符串的结尾开始检索
    var oStringObject = new String("hello world!");
    alert(oStringObject.indexOf("o"));		// 输出 "4"
    alert(oStringObject.lastIndexOf("o"));	// 输出 "7"


    2-7-10）localeCompare() 方法
    对字符串进行排序
    var oStringObject = new String("yellow");
    alert(oStringObject.localeCompare("brick"));		//输出 "1"
    alert(oStringObject.localeCompare("yellow"));		//输出 "0"
    alert(oStringObject.localeCompare("zoo"));		    //输出 "-1

    // 采用以下结构，可以确保这段代码在所有实现中都能正确运行
    var oStringObject1 = new String("yellow");
    var oStringObject2 = new String("brick");
    var iResult = oStringObject1.localeCompare(oStringObject2);
    if(iResult < 0) {
    alert(oStringObject1 + " comes before " + oStringObject2);
    } else if (iResult > 0) {
    alert(oStringObject1 + " comes after " + oStringObject2);
    } else {
    alert("The two strings are equal");
    }


    2-7-11）slice() 和 substring()
    两种方法从子串创建字符串值，都接受一个或两个参数
    第一个参数是要获取的子串的起始位置
    第二个参数（如果使用的话）是要获取子串终止前的位置
    var oStringObject = new String("hello world");
    alert(oStringObject.slice("3"));		    //输出 "lo world"
    alert(oStringObject.substring("3"));		//输出 "lo world"
    alert(oStringObject.slice("3", "7"));		//输出 "lo w"
    alert(oStringObject.substring("3", "7"));	//输出 "lo w"

    var oStringObject = new String("hello world");
    // 对于字符串 "hello world"，slice("-3") 将被转换成 slice("8")
    // 而 substring("-3") 将被转换成 substring("0")

    alert(oStringObject.slice("-3"));		    //输出 "rld"
    alert(oStringObject.substring("-3"));	    //输出 "hello world"
    alert(oStringObject.slice("3, -4"));		//输出 "lo w"
    alert(oStringObject.substring("3, -4"));	//输出 "hel"


    2-7-12）toLowerCase()、toLocaleLowerCase()
    toUpperCase()、toLocaleUpperCase()
    4 种方法用于执行大小写转换
    var oStringObject = new String("Hello World");
    alert(oStringObject.toLocaleUpperCase());	//输出 "HELLO WORLD"
    alert(oStringObject.toUpperCase());		    //输出 "HELLO WORLD"
    alert(oStringObject.toLocaleLowerCase());	//输出 "hello world"
    alert(oStringObject.toLowerCase());		    //输出 "hello world"
    String 对象的所有属性和方法都可应用于 String 原始值上，因为它们是伪对象


    2-7-13）instanceof 运算符
    instanceof 运算符与 typeof 运算符相似，用于识别正在处理的对象的类型
    不同的是，instanceof 方法要求开发者明确地确认对象为某特定类型
    var oStringObject = new String("hello world");
    alert(oStringObject instanceof String);	    //输出 "true"


3. ECMAScript 运算符
    3-1）一元运算符
    只有一个参数，即要操作的对象或值

    3-1-1）delete
    delete 运算符删除对以前定义的对象属性或方法的引用
        var o = new Object;
        o.name = "David";
        alert(o.name);	//输出 "David"
        delete o.name;
        alert(o.name);	//输出 "undefined"

    注：delete 运算符不能删除开发者未定义的属性和方法

    3-1-2）void
    void 运算符对任何值返回 undefined，该运算符通常用于避免输出不应该输出的值
        <a href="javascript:window.open('about:blank')">Click me</a>
        // 使用void() 不会显示在浏览器窗口
        <a href="javascript:void(window.open('about:blank'))">Click me</a>

    3-1-3）前增量/前减量运算符
        var iNum = 10;
        ++iNum;

        var iNum1 = 2;
        var iNum2 = 20;
        var iNum3 = --iNum1 + ++iNum2;	//等于 "22"
        var iNum4 = iNum1 + iNum2;		//等于 "22"

    3-1-4）后增量/后减量运算符
        var iNum1 = 2;
        var iNum2 = 20;
        var iNum3 = iNum1-- + iNum2++;	//等于 "22"
        var iNum4 = iNum1 + iNum2;		//等于 "22"

    3-1-5）一元加法和一元减法
    一元加法本质上对数字无任何影响
        var iNum = 20;
        iNum = +iNum;
        alert(iNum);	    //输出 "20"

        var sNum = "20";
        alert(typeof sNum);	//输出 "string"
        var iNum = +sNum;
        alert(typeof iNum);	//输出 "number"

    一元减法就是对数值求负
        var iNum = 20;
        iNum = -iNum;
        alert(iNum);	    //输出 "-20"

        var sNum = "20";
        alert(typeof sNum);	//输出 "string"
        var iNum = -sNum;
        alert(iNum);		//输出 "-20"
        alert(typeof iNum);	//输出 "number"


    3-2）位运算符
    位运算符是在数字底层（即表示数字的 32 个数位）进行操作的

    3-3）Boolean 运算符
    Boolean 运算符非常重要，它使得程序语言得以正常运行
    Boolean 运算符有三种：NOT、AND 和 OR

    3-3-1）逻辑 NOT 运算符
    逻辑 NOT 运算符与 C 和 Java 中的逻辑 NOT 运算符相同，都由感叹号（!）表示
        var bFound = false;
        var i = 0;
        while (!bFound){
            if (aValue[i] == vSerachValues) {
                bFound = true;
            }else{
                i++;
            }
        }

    3-3-2）逻辑 AND 运算符
    逻辑 AND 运算符用双和号（&&）表示，全true 则true
        var bTrue = true;
        var bResult = (bTrue && bUnknown);	//第一行发生错误
        alert(bResult);			            //后面这一行不会执行

        var bFalse = false;
        var bResult = (bFalse && bUnknown);
        alert(bResult);			            //输出 "false"


    3-3-3）逻辑 OR 运算符
    逻辑 OR 运算符与 Java 中的相同，都由双竖线（||）表示

        var bFalse = false;
        var bResult = (bFalse || bUnknown);	//第一行发生错误
        alert(bResult);			            //不会执行这一行


    3-4）乘性运算符
    ECMAScript 的乘性运算符与 Java、C、Perl 等于语言中的同类运算符的运算方式相似，且具有一些自动转换功能
    3-4-1）乘法运算符
    乘法运算符由星号（*）表示，用于两数相乘
    var iResult = 1 * 2

    3-4-2）除法运算符
    除法运算符由斜杠（/）表示，用第二个运算数除第一个运算数
    var iResult = 88 /11;

    3-4-3）取模运算符
    除法（余数）运算符由百分号（%）表示
    var iResult = 22%5;     //等于 2

    3-5）加性运算符
    在 ECMAScript 中，加性运算符有大量的特殊行为
    3-5-1）加法运算符
        var iResult = 1 + 2

        var result = 5 + 5;	    //两个数字
        alert(result);		    //输出 "10"
        var result2 = 5 + "5";	//一个数字和一个字符串
        alert(result);		    //输出 "55"

    3-5-2）减法运算符
    与加法运算符一样，在处理特殊值时，减法运算符也有一些特殊行为
    某个运算数是 NaN，那么结果为 NaN
    Infinity 减 Infinity，结果为 NaN
    Infinity 减 -Infinity，结果为 Infinity
    -Infinity 减 -Infinity，结果为 NaN
    -Infinity 减 Infinity，结果为 -Infinity


    3-6）关系运算符
    关系运算符执行的是比较运算。每个关系运算符都返回一个布尔值
    3-6-1）字母顺序比较
    var bResult = "Blue" < "alpha";
    alert(bResult);	            //大写字母顺序在前输出 true

    var bResult = "Blue".toLowerCase() < "alpha".toLowerCase();
    alert(bResult);	            //输出 false

    3-6-2）比较数字和字符串
    var bResult = "25" < "3";
    alert(bResult);	            //输出 "true"

    var bResult = "25" < 3;
    alert(bResult);	            //输出 "false"


    3-7）等性运算符
    ECMAScript 提供了两套等性运算符：
    等号和非等号用于处理原始值，全等号和非全等号用于处理对象

    3-8）条件运算符
    variable = boolean_expression ? true_value : false_value;
    var iMax = (iNum1 > iNum2) ? iNum1 : iNum2;

    3-9）赋值运算符
    赋值运算符由等号（=）实现，只是把等号右边的值赋予等号左边的变量
    var iNum = 10;
    iNum += 10；

    3-10）逗号运算符
    用逗号运算符可以在一条语句中执行多个运算
    var iNum1 = 1, iNum = 2, iNum3 = 3;


4. ECMAScript 语句
    4-1）if 语句
        if (condition) statement1 else statement2
        if (i > 30) 
        {
        alert("大于 30");
        } else if (i < 0) 
        {
        alert("小于 0");
        } else {
        alert("在 0 到 30 之间");
        }

    4-2）迭代语句
    迭代语句又叫循环语句，声明一组要反复执行的命令，直到满足某些条件为止
        4-2-1）do-while 语句
        后测试循环，即退出条件在执行循环内部的代码之后计算
        var i = 0;
        do {i += 2;} while (i < 10);

        4-2-2）while 语句
        前测试循环，这意味着退出条件是在执行循环内部的代码之前计算
        var i = 0;
        while (i < 10) {
        i += 2;
        }

        4-2-3）for 语句
        前测试循环，而且在进入循环之前，能够初始化变量，并定义循环后要执行的代码
        iCount = 6;
        for (var i = 0; i < iCount; i++) {
        alert(i);
        }

        4-2-4）for-in 语句
        for 语句是严格的迭代语句，用于枚举对象的属性
        for (i in rangge(6)){
            alert(i);
        }

    4-3）标签语句
    给语句加标签，以便以后调用
    start : i = 5;
    标签 start 可以被之后的 break 或 continue 语句引用


    4-4）break 和 continue 语句
    break 语句可以立即退出循环，阻止再次反复执行任何代码
    continue 语句只是退出当前循环，根据控制表达式还允许继续进行下一次循环
        var iNum = 0;
        for (var i=1; i<10; i++) {
        if (i % 5 == 0) {
            break;
        }
        iNum++;
        }
        alert(iNum);	//输出 "4",执行循环次数

        // continue 语句
        var iNum = 0;
        for (var i=1; i<10; i++) {
        if (i % 5 == 0) {
            continue;
        }
        iNum++;
        }
        alert(iNum);	//输出 "8"


        // 与有标签的语句一起使用，返回代码中的特定位置
        var iNum = 0;
        outermost:
        for (var i=0; i<10; i++) {
            for (var j=0; j<10; j++) {
                if (i == 5 && j == 5) {
                break outermost;
             // continue outermost; // 输出95，减少5次迭代
            }
            iNum++;
            }
        }
        alert(iNum);	    //输出 "55", 正常要循环100次


    4-5）with 语句
    用于设置代码在特定对象中的作用域
    var sMessage = "hello";
    with(sMessage) {
    alert(toUpperCase());	//输出 "HELLO"
    }

    with 语句是运行缓慢的代码块，尤其是在已设置了属性值时，
    大多数情况下，如果可能，最好避免使用它


    4-6）switch 语句
    switch 语句为表达式提供一系列的情况（case）
    if (i == 20)
        alert("20");
    else if (i == 30)
        alert("30");
    else if (i == 40)
        alert("40");
    else
        alert("other");

    // 使用switch
    switch (i){
        case 20: alert("20");
            break;
        case 30: alert("30");
            break;
        case 40: alert("40");
            break
        default: alert("other");
        }

    switch 语句可以用于字符串，而且能用不是常量的值说明情况



5. ECMAScript 函数
    函数是一组可以随时随地运行的语句，是 ECMAScript 的核心
    由关键字 function、函数名、一组参数，以及置于括号中的待执行代码组成
    语法：
    function functionName(arg0, arg1, ... argN) {
        statements
        }
    调用：
    functionName("xxx", "Hello ECMAScript")
    函数返回值：
    return 语句

    function sayHi(sMessage) {
    if (sMessage == "bye") {
        return;     // 无参return 语句，真正返回的值是 undefined
    }
    alert(sMessage);
    }


    5-1）arguments 对象
    5-1-1）特殊arguments 对象
    在函数代码中，使用特殊对象arguments，开发者无需明确指出参数名，就能访问它
        function sayHi() {
        if (arguments[0] == "bye") {
            return;
        }
        alert(arguments[0]);
        }

    5-1-2）检测参数个数
    引用属性 arguments.length
        function howManyArgs() {
            alert(arguments.length);
        }

        howManyArgs("string", 45);    // 2个参数
        howManyArgs();                // 0
        howManyArgs(12);              // 1

    5-1-2）模拟函数重载
    用 arguments 对象判断传递给函数的参数个数，即可模拟函数重载
        function doAdd() {
            if(arguments.length == 1) {
                alert(arguments[0] + 5);
            } else if(arguments.length == 2) {
                alert(arguments[0] + arguments[1]);
            }
        }

        doAdd(10);	                // 输出 "15"
        doAdd(40, 20);	            // 输出 "60"


    5-2）Function 对象（类）
    ECMAScript 的函数实际上是功能完整的对象
    函数定义两种方式：
    // 关键字 function
    function sayHi(sName, sMessage) {
        alert("Hello " + sName + sMessage);
        }

    // 赋值变量，new Function()
    var sayHi 
    = 
    new Function("sName", "sMessage", "alert(\"Hello \" + sName + sMessage);");

    注：如果函数名只是指向函数的变量，那么可以把函数作为参数传递给另一个函数

    Function 对象的方法
    Function 对象也有与所有对象共享的 valueOf() 方法和 toString() 方法
    这两个方法返回的都是函数的源代码，在调试时尤其有用
    <html>
    <body>
    <script type="text/javascript">

    function doAdd(iNum) {
        alert(iNum + 10);
    }

    document.write(doAdd.toString()); 
    // 输出doAdd 函数的文本 function doAdd(iNum) { alert(iNum + 10); }

    </script> 
    </body>
    </html>


    5-3） 闭包（closure）
    闭包，指的是词法表示包括不被计算的变量的函数，也就是说，函数可以使用函数之外定义的变量
    var sMessage = "hello world";

    function sayHelloWorld() {
        alert(sMessage);
    }

    sayHelloWorld();       // 使用外部变量，输出 hello world




6. ECMAScript 对象
    面向对象技术
    对象： 基于代码的名词表示，（属性的无序集合）
    类：   每个对象都由类定义，类不仅要定义对象的接口（interface）（开发者访问的属性和方法），还要定义对象的内部工作（使属性和方法发挥作用的代码）
    实例： 程序使用类创建对象时，生成的对象叫作类的实例（instance）

    面向对象语言特点：
    封装 - 把相关的信息（无论数据或方法）存储在对象中的能力
    聚集 - 把一个对象存储在另一个对象内的能力
    继承 - 由另一个类（或多个类）得来类的属性和方法的能力
    多态 - 编写能以多种方法运行的函数或方法的能力

    对象的构成
    对象由特性（attribute）构成，特性可以是原始值，也可以是引用值
    如果特性存放的是函数，它将被看作对象的方法（method）
    否则该特性被看作对象的属性（property）
    6-1）对象应用
    对象的创建和销毁都在 JavaScript 执行过程中发生
    理解这种范式的含义对理解整个语言至关重要

    6-1-1）声明和实例化
    var oObject = new Object();
    var oStringObject = new String(); // 注：无参数可省略()

    6-1-2）对象引用
    在 ECMAScript 中，不能访问对象的物理表示，只能访问对象的引用
    每次创建对象，存储在变量中的都是该对象的引用，而不是对象本身

    6-1-3）对象废除
    ECMAScript 拥有无用存储单元收集程序，不必专门销毁对象来释放内存
    把对象的所有引用都设置为 null，可以强制性地废除对象
        var oObject = new Object;
        // do something with the object here
        oObject = null;
        
    6-1-4）早绑定和晚绑定
    所谓绑定（binding），即把对象的接口与对象实例结合在一起的方法
    早绑定（early binding）是指在实例化对象之前定义它的属性和方法
    ECMAScript 不是强类型语言，所以不支持早绑定

    晚绑定（late binding）指的是编译器或解释程序在运行前，不知道对象的类型。使用晚绑定，无需检查对象的类型，只需检查对象是否支持属性和方法即可
    ECMAScript 中的所有变量都采用晚绑定方法，这样就允许执行大量的对象操作，而无任何惩罚

    6-2）对象类型
    一般来说，可以创建并使用的对象有三种：本地对象、内置对象和宿主对象
    本地对象
    本地对象就是 ECMA-262 定义的类（引用类型）它们包括
    Object Function Array String Boolean Number Date等

    内置对象
    ECMA-262 只定义了两个内置对象，即 Global 和 Math （它们也是本地对象，根据定义，每个内置对象都是本地对象）

    宿主对象
    所有非本地对象都是宿主对象，即由 ECMAScript 实现的宿主环境提供的对象
    

    6-3）对象作用域
    作用域指的是变量的适用范围（公用、私有和受保护作用域）
    静态作用域
    静态作用域定义的属性和方法任何时候都能从同一位置访问
     java.net.URLEncoder 类，它的函数 encode() 就是静态方法
     ECMAScript 并没有静态作用域。不过，它可以给构造函数提供属性和方法
    <html>
    <body>
    <script type="text/javascript">
    function sayHello() {
        alert("hello");
        }

    sayHello.alternate = function() {
        alert("hi");
        }
    sayHello();                 // 输出 "hello"

    //alternate()是sayHello()公用作用域中的方法，而不是静态方法
    sayHello.alternate();       // 输出 "hi"

    </script>
    </body>
    </html>     

    关键字 this
    关键字 this 总是指向调用该方法的对象
    var oCar = new Object;
    oCar.color = "red";
    oCar.showColor = function() {
        alert(this.color);
        // 等价于 alert(oCar.color);
        };

    oCar.showColor();		    //输出 "red"

    应用场景：可在任何多个地方重用同一个函数


    6-4）定义类或对象
    使用预定义对象只是面向对象语言的能力的一部分
    它真正强大之处在于能够创建自己专用的类和对象
    创建对象或类的方法：
    6-4-1）工厂方式
    开发者创建并返回特定类型的对象的工厂函数
    function createCar(sColor,iDoors) {
        var oTempCar = new Object;
        //oTempCar.color = "blue";
        oTempCar.color = sColor;
        oTempCar.doors = iDoors;
        oTempCar.showColor = function() {
            alert(this.color);
            };
        return oTempCar;
        }

    var oCar1 = createCar("red",4);
    var oCar2 = createCar("blue",3);    // 两个car 属性一样

    6-4-2）在工厂函数外定义对象的方法
    从功能上讲，这样解决了重复创建函数对象的问题
    但是从语义上讲，该函数不太像是对象的方法
    function showColor() {
        alert(this.color);
        }

    function createCar(sColor,iDoors,iMpg) {
        var oTempCar = new Object;
        oTempCar.color = sColor;
        oTempCar.doors = iDoors;
        oTempCar.mpg = iMpg;
        oTempCar.showColor = showColor;
        return oTempCar;
        }

    var oCar1 = createCar("red",4,23);
    var oCar2 = createCar("blue",3,25);

    oCar1.showColor();		//输出 "red"
    oCar2.showColor();		//输出 "blue"

    6-4-3）构造函数方式
    创建构造函数就像创建工厂函数一样容易，第一步选择类名，即构造函数的名字
    function Car(sColor,iDoors,iMpg) {
    this.color = sColor;
    this.doors = iDoors;
    this.mpg = iMpg;
    this.showColor = function() {
        alert(this.color);
    };
    }
    
    // 使用this 关键字，函数内没有创建对象
    var oCar1 = new Car("red",4,23);
    var oCar2 = new Car("blue",3,25);


    6-4-5）原型方式
    该方式利用了对象的 prototype 属性，可以把它看成创建新对象所依赖的原型
    function Car() {
    }
    Car.prototype.color = "blue";
    Car.prototype.doors = 4;
    Car.prototype.mpg = 25;
    Car.prototype.showColor = function() {
        alert(this.color);
  
    };

    var oCar1 = new Car();
    var oCar2 = new Car();
    // alert(oCar1 instanceof Car);	//输出 "true"

    使用原型方式，不能通过给构造函数传递参数来初始化属性的值
    真正的问题出现在属性指向的是对象，而不是函数时。函数共享不会造成问题，但对象却很少被多个实例共享

    <html>
    <body>

    <script type="text/javascript">

    function Car() {
    }

    Car.prototype.color = "blue";
    Car.prototype.doors = 4;
    Car.prototype.mpg = 25;
    Car.prototype.drivers = new Array("Mike","John");
    Car.prototype.showColor = function() {
        document.write(this.color);
    };

    var oCar1 = new Car();
    var oCar2 = new Car();

    oCar1.drivers.push("Bill");

    document.write(oCar1.drivers);      //Mike,John,Bill
    document.write("<br />")
    document.write(oCar2.drivers);      //指向同一个数组 Mike,John,Bill

    </script>

    </body>
    </html>
    

    6-4-6）混合的构造函数/原型方式
    <html>
    <body>

    <script type="text/javascript">

    function Car(sColor,iDoors,iMpg) {
    this.color = sColor;
    this.doors = iDoors;
    this.mpg = iMpg;
    this.drivers = new Array("Mike","John");
    }

    Car.prototype.showColor = function() {
        document.write(this.color);
    };

    var oCar1 = new Car("red",4,23);
    var oCar2 = new Car("blue",3,25);

    oCar1.drivers.push("Bill");

    document.write(oCar1.drivers);      //输出 "Mike,John,Bill"
    document.write("<br />")
    document.write(oCar2.drivers);      //输出 "Mike,John"

    </script>

    </body>
    </html>   


    6-4-7）动态原型方法
    动态原型方法重写的 Car 类
    使用（_initialized）来判断是否已给原型赋予了任何方法
    function Car(sColor,iDoors,iMpg) {
    this.color = sColor;
    this.doors = iDoors;
    this.mpg = iMpg;
    this.drivers = new Array("Mike","John");
    
    if (typeof Car._initialized == "undefined") {
        Car.prototype.showColor = function() {
        alert(this.color);
        };
        
        Car._initialized = true;
        }
    }


    6-4-8）混合工厂方式
    目的是创建假构造函数，只返回另一种对象的新实例
    使用 new 运算符，使它看起来像真正的构造函数，除非万不得已，还是避免使用这种方式
    function Car() {
    var oTempCar = new Object;
    oTempCar.color = "blue";
    oTempCar.doors = 4;
    oTempCar.mpg = 25;
    oTempCar.showColor = function() {
        alert(this.color);
    };

    return oTempCar;
    }


    6-4-9）字符串连接的性能
    var str = "hello ";
    str += "world";

    这种操作非常消耗资源
    解决方法是用 Array 对象存储字符串，然后用 join() 方法，创建最后的字符串
    var arr = new Array();
    arr[0] = "hello";
    arr[1] = "JS";
    var str = arr.join("");

    进阶：用 StringBuffer 类打包该功能
    function StringBuffer(){
        this._strings_ =new Array();
    }
    StringBuffer.prototype.append = function(str){
        this._strings_.push(str);
    };

    StringBuffer.protottype.toString = function(){
        return this._sytings_.join("");
    };


    // 使用 StringBuffer 对象连接一组字符串
    <html>
    <body>
    <script type="text/javascript">

    function StringBuffer () {
    this._strings_ = new Array();
    }

    StringBuffer.prototype.append = function(str) {
        this._strings_.push(str);
    };

    StringBuffer.prototype.toString = function() {
        return this._strings_.join("");
    };

    var buffer = new StringBuffer ();
    buffer.append("hello ");
    buffer.append("world");
    var result = buffer.toString();

    document.write(buffer);               // hello world
    </script>
    </body>
    </html>


    测试 StringBuffer 对象和传统的字符串连接方法的性能
    <html>
    <body>

    <script type="text/javascript">

    function StringBuffer () {
        this._strings_ = new Array();
    }

    StringBuffer.prototype.append = function(str) {
        this._strings_.push(str);
    };

    StringBuffer.prototype.toString = function() {
        return this._strings_.join("");
    };

    var d1 = new Date();
    var str = "";
    for (var i=0; i < 10000; i++) {
        str += "text";
    }
    var d2 = new Date();

    document.write("Concatenation with plus: "
    + (d2.getTime() - d1.getTime()) + " milliseconds");

    var buffer = new StringBuffer();
    d1 = new Date();
    for (var i=0; i < 10000; i++) {
        buffer.append("text");
    }
    var result = buffer.toString();
    d2 = new Date();

    document.write("<br />Concatenation with StringBuffer: "
    + (d2.getTime() - d1.getTime()) + " milliseconds");


    /*Concatenation with plus: 5 milliseconds
    Concatenation with StringBuffer: 6 milliseconds*/

    </script>

    </body>
    </html>   


    6-5）修改对象
    prototype 属性不仅可以定义构造函数的属性和方法，还可以为本地对象添加属性和方法
    6-5-1）创建新方法
    Number.prototype.toHexString = function() {
        return this.toString(16);
        };

    var iNum = 15;
    alert(iNum.toHexString());		    // 输出 "F"

    6-5-2）重命名已有方法
    给 Array 类添加两个方法 enqueue() 和 dequeue()
    只让它们反复调用已有的 push() 和 shift() 方法即可
    Array.prototype.enqueue = function(vItem) {
        this.push(vItem);
        };

    Array.prototype.dequeue = function() {
        return this.shift();
        };


    6-5-3）添加与已有方法无关的方法
    假设要判断某个项在数组中的位置，没有本地方法可以做这种事情
    Array.prototype.indexOf = function (vItem) {
        for (var i=0; i<this.length; i++) {
            if (vItem == this[i]) {
                return i;
            }
        }
        return -1;
    }


    var aColors = new Array("red","green","blue");
    alert(aColors.indexOf("green"));            	//输出 "1"
    
    
    6-5-4）为本地对象添加新方法
    在 Object 对象的 prototype 属性上定义它
    添加一个用警告输出对象的当前值的方法
    Object.prototype.showValue = function () {
        alert(this.valueOf());
    };

    var str = "hello";
    var iNum = 25;

    //String 和 Number 对象都从 Object 对象继承了 showValue() 方法
    str.showValue();		    // 输出 "hello"
    iNum.showValue();		    // 输出 "25"


    6-5-5）重定义已有方法
    函数名只是指向函数的指针，因此可以轻松地指向其他函数
    <html>
    <body>
    <script type="text/javascript">

    Function.prototype.toString = function() {
    return "Function code hidden";
    }

    function sayHi() {
    alert("hi");
    }

    document.write(sayHi.toString());   // 输出 "Function code hidden"
    </script>
    </body>
    </html>


    //Function 的 toString() 方法通常输出的是函数的源代码
    覆盖该方法，可以返回另一个字符串,toString() 指向的原始函数
    将被无用存储单元回收程序回收,所以在覆盖原始方法前，比较安全的做法是存储它的指针

    <script type="text/javascript">
    // 把当前 toString() 方法的引用保存在属性 originalToString 中
    Function.prototype.originalToString = Function.prototype.toString;

    Function.prototype.toString = function() {
        if (this.originalToString().length > 100) {
            return "Function too long to display.";
            } else {
            return this.originalToString();
        }
    };

    function sayHi() {
        alert("hi");
    }

    document.write(sayHi.toString());  
    // 输出 function sayHi() { alert("hi"); }
    </script>


    6-5-6）极晚绑定（Very Late Binding）
    能够在对象实例化后再定义它的方法
    不建议使用极晚绑定方法，因为很难对其跟踪和记录



7. ECMAScript 继承
    7-1）继承机制的实现
    从继承的基类入手，所有开发者定义的类都可作为基类，出于安全原因，本地类和宿主类不能作为基类，这样可以防止公用访问编译过的浏览器级的代码，因为这些代码可以被用于恶意攻击

    选定基类后，就可以创建它的子类，创建的子类将继承超类的所有属性和方法，包括构造函数及方法的实现


    7-2）继承的方式
    7-2-1）对象冒充
    原理:构造函数使用 this 关键字给所有属性和方法赋值（即采用类声明的构造函数方式）使 ClassA 构造函数成为 ClassB 的方法，然后调用它
    <html>
    <head>
    <title>Example</title>
    </head>
    <body>
    <script type="text/javascript">
    function ClassA(sColor) {
        this.color = sColor;
        this.sayColor = function () {
            alert(this.color);
        };
    }

    // ClassB 可以实现继承机制
    function ClassB(sColor, sName) {
        this.newMethod = ClassA;
        this.newMethod(sColor);
        delete this.newMethod;
        
        //所有新属性和新方法都必须在删除了新方法的代码行后定义。否则，可能会覆盖超类的相关属性和方法
        this.name = sName;
        this.sayName = function () {
            alert(this.name);
        };    
    }

    // 测试
    var objA = new ClassA("blue");
    var objB = new ClassB("red", "John");
    objA.sayColor();
    objB.sayColor();
    objB.sayName();
    </script>
    </body>
    </html>


    7-2-2）对象冒充可以实现多重继承   
    function ClassZ() {
        this.newMethod = ClassX;
        this.newMethod();
        delete this.newMethod;

        this.newMethod = ClassY;
        this.newMethod();
        delete this.newMethod;
    }   

    这里存在一个弊端，如果存在两个类 ClassX 和 ClassY 具有同名的属性或方法，ClassY 具有高优先级

    ECMAScript 的第三版为 Function 对象加入了两个方法，即 call() 和 apply()
   
   
    7-2-3）call() 方法
    call() 方法是与经典的对象冒充方法最相似的方法,它的第一个参数用作 this 的对象,其他参数都直接传递给函数自身

    function sayColor(sPrefix,sSuffix) {
        alert(sPrefix + this.color + sSuffix);
    };

    var obj = new Object();
    obj.color = "blue";

    sayColor.call(obj, "The color is ", "a very nice color indeed.");

    要与继承机制的对象冒充方法一起使用该方法，只需将前三行的赋值、调用和删除代码替换即可
   
    function ClassB(sColor, sName) {
        //this.newMethod = ClassA;
        //this.newMethod(color);
        //delete this.newMethod;
        ClassA.call(this, sColor);

        this.name = sName;
        this.sayName = function () {
            alert(this.name);
        };
    }



    7-2-4）apply() 方法
    apply() 方法有两个参数，用作 this 的对象和要传递给函数的参数的数组

    <script type="text/javascript">
    function sayColor(sPrefix,sSuffix) {
        alert(sPrefix + this.color + sSuffix);
    };

    var obj = new Object();
    obj.color = "blue";

    sayColor.apply(obj, new Array("The color is ", "a very nice color indeed."));

    function ClassB(sColor, sName) {
        //this.newMethod = ClassA;
        //this.newMethod(color);
        //delete this.newMethod;
        ClassA.apply(this, new Array(sColor));

        this.name = sName;
        this.sayName = function () {
            alert(this.name);
        };
    }
    </script>

    // 只有超类中的参数顺序与子类中的参数顺序完全一致时才可以传递参数对象。如果不是，就必须创建一个单独的数组，按照正确的顺序放置参数。此外，还可使用 call() 方法


    7-2-5）原型链（prototype chaining）
    prototype 对象是个模板，要实例化的对象都以这个模板为基础
    prototype 对象的任何属性和方法都被传递给那个类的所有实例
    原型链利用这种功能来实现继承机制
    function ClassA() {
    }
    ClassA.prototype.color = "blue";
    ClassA.prototype.sayColor = function () {
        alert(this.color);
    };

    
    // 为 ClassB 类添加 name 属性和 sayName() 方法
    function ClassB() {
    }

    ClassB.prototype = new ClassA();

    ClassB.prototype.name = "";
    ClassB.prototype.sayName = function () {
        alert(this.name);
    };

    测试
    var objA = new ClassA();
    var objB = new ClassB();
    objA.color = "blue";
    objB.color = "red";
    objB.name = "John";
    objA.sayColor();
    objB.sayColor();
    objB.sayName();

    var objB = new ClassB();
    alert(objB instanceof ClassA);	    //输出 "true"
    alert(objB instanceof ClassB);	    //输出 "true"

    原型链的弊端是不支持多重继承,原型链会用另一类型的对象重写类的 prototype 属性


    7-2-6）混合方式
    对象冒充的主要问题是必须使用构造函数方式，这不是最好的选择
    不过如果使用原型链，就无法使用带参数的构造函数
    <html>
    <head>
    <title>Example</title>
    </head>
    <body>
    <script type="text/javascript">
    function ClassA(sColor) {
        this.color = sColor;
    }

    ClassA.prototype.sayColor = function () {
        alert(this.color);
    };

    function ClassB(sColor, sName) {
        // 用对象冒充继承 ClassA 类的 sColor 属性
        ClassA.call(this, sColor);
        this.name = sName;
    }

    // 用原型链继承 ClassA 类的方法
    ClassB.prototype = new ClassA();

    ClassB.prototype.sayName = function () {
        alert(this.name);
    };

    // 测试
    var objA = new ClassA("blue");
    var objB = new ClassB("red", "John");
    objA.sayColor();
    objB.sayColor();
    objB.sayName();

    </script>
    
    </body>
    </html>



