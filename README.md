#JavaScript Coding Style

## 編輯歷程

<table cellspacing="0" border="1">
   <thead>
     <tr>
	 <th>時間</th>
	 <th>版本</th>
     <th>說明</th>
     <th>編輯人</th>
    </tr>
   </thead>
   
   <tbody>
    <tr>
     <td>2013.11.25</td> 
     <td>1.11</td>
     <td>* 新增章節8:嚴格模式</td>
     <td>Hank Kuo</td>
    </tr>
    
    <tr>
     <td>2013.08.08</td> 
     <td>1.1</td>
     <td>
         * 1.7.5 新增物件屬性風格說明<br/> 
         * 1.7.6 新增陣列元素風格說明<br/> 
         * 增加4.3函式參數風格說明<br/>
     </td>
     <td>Hank Kuo</td>
    </tr>
    
    <tr>
     <td>2013.07.11</td> 
     <td>1.0</td>
     <td>
         * 1.3改為'建議' <br/> 
         * 增加1.6.3 全域變數說明 <br/> 
         * 1.7.2增加perseInt()使用規則說明<br/> 
         * 1.7.3增加簡易檢測變數與參數說明<br/>* 修改2.1多行注解規則<br/> 
         * 修改3.4 assign變數風格(=前後需空一格) <br/> 
         * 修改4.1變數宣告風格(每個變數都要有var) <br/> 
         * 新增4.1.1變數宣告位置說明<br/> * 4.2函式宣告新增匿名函式說明
     </td>
     <td>Hank Kuo</td>
    </tr>
    
    <tr>
     <td>2013.07.03</td> 
     <td>1.0 beta2</td>
     <td>
         * 文件改用markdown撰寫, 增加變數, 函式, 運算符, 錯誤處理, 類型檢測等風格
     </td>
     <td>Hank Kuo</td>
    </tr>
    
    <tr>
     <td>2012.12.06</td> 
     <td>1.0 beta1</td>
     <td>
         * 建立文件, 基本程式風格建立
     </td>
     <td>Mars Peng</td>
    </tr>
    
   </tbody>
</table>




## 章節
#### 1. 基本格式

* [1.1 縮排](#1_indent)
* [1.2 語句結尾](#1_end)
* [1.3 單行程式碼長度](#1_singleCode)
* [1.4 換行規則](#1_changeCol)
* [1.5 空行](#1_space)
* [1.6 命名](#1_name)
* [1.7 基本形態(Type)與物件(Object)](#1_type)

#### 2. 注解

* [2.1 單行注解](#2_single)
* [2.2 多行注解](#2_multi)
* [2.3 注解使用時機](#2_when)
* [2.4 注解聲明](#2_dsrp)

#### 3. 語句和條件判斷式

* [3.1 大括號](#3_brace)
* [3.2 switch](#3_switch)
* [3.3 with](#3_with)
* [3.4 for](#3_for)
* [3.5 for-in](#3_forin)

#### 4. 變數, 函式

* [4.1 變數宣告](#4_varDeclaration)
* [4.2 函式宣告](#4_funcDeclaration)
* [4.3 函式參數風格](#4_funcParams)
* [4.4 函式建構式, eval(), setTimeout()和setInterval()](#4_funcConstructor)
* [4.5 嚴格模式('use strict')](#4_strict)

#### 5. 運算符

* [5.1 賦値(=)](#5_assign)
* [5.2 相等操作符(===, !==)](#5_equal)
* [5.3 三元運算子(? :)](#5_triple)

#### 6. 錯誤處理
* [6.1 Error物件](#6_error)
* [6.2 throw](#6_throw)
* [6.3 try-catch](#6_trycatch)

#### 7. 類型檢測

* [7.1 檢測基本類型](#7_type)
* [7.2 檢測內建物件(Object, Array, Date, Error)與自定義物件](#7_object)
* [7.3 檢測函式](#7_func)
* [7.4 檢測陣列](#7_array)
* [7.5 檢測屬性](#7_attr)

#### 8. 嚴格模式(Strict Mode)

* [8.1 宣告嚴格模式](#8_declare)
* [8.2 嚴格模式下的限制](#8_rule)

#### 附錄A. 參考資料

* [附錄A.1 網路資源](#appendixA_web)
* [附錄A.2 書籍](#appendixA_book)


---

##1. 基本格式<a id="1"></a>

### 1.1  縮排<a id="1_indent"></a>
#####程式碼的縮排採用`四個空格字元`, 不可使用tab character

因為不同系統對於 tab character 的解釋不一致, 造成用不同編輯器打開文件看到的結果不一樣。


### 1.2 語句結尾<a id="1_end"></a>
#####程式碼的結尾`一定要加上分號(;)`
JavaScript有自動分號插入(Automatic Semicolon Insertion, ASI)機制, 即使省略分號大部份情形下也可以正常工作, 但是 ASI 的分號插入機制非常複雜, 因此一定要加上分號, 避免發生下列情形.

```
// 原始程式碼
function getData() {
	return
	{
		title: 'Hiiir JavaScript Coding Style',
		author: 'Mars, Hank'
	}
}

// 分析器會轉譯成
function getData() {
	return;
	{
		title: 'Hiiir JavaScript Coding Style',
		author: Mars, Hank'
	};
}

```
這樣會導致 getData() 回傳值為 undefined.

### 1.3 單行程式碼長度<a id="1_singleCode"></a>
##### 單行程式碼長度`建議不超過 80 個字元`

### 1.4 換行規則<a id="1_changeCol"></a>
##### 在運算符號後換行, 下一行第一個變數對齊上一行第一個變數<br>

```
callMyFunction(this, window, 'this is a string', 'another string', 123,
               myObject);

// ASI機制會在某些條件下在行結束的位置插入分號, 因此總是將一個運算符號置於行尾, 可避免ASI插入錯誤的分號
if (isYear && isDate && day == 30 && isOldYear && 
	isNoPlans) {
	
	doSomething();
}

var result = someValue + anotherValue + myValue + hisValue + herValue + 
             defaultValue;
```

### 1.5 空行<a id="1_space"></a>
##### 請在下列場景添加空行：
* 在每個條件判斷語句之前(if…else, for)添加空行
* 在方法(function)之間
* 在方法中的區域變數(local variable)和第一條語句之間
* 在多行或單行注解之前
* 在方法內的邏輯片段之間插入空行, 提高可讀性

```
function doSomething() {
    var myArr,
        anotherVal;
    
    if (myArr.length > 0) {
	
	    for (var i, len=myArr.length; i < len; i++) {
		
		    // 單行注解
	
		    /*
		     *多行注解
		     */
		
		    var logicSection = 10;
		    logicSection1 = logicSection + i;
		
		    logicSection2 = logicSection + i * 100;
	    }
    }
}

function doAnotherThing() {
	// doAnotherThing
}
```

### 1.6 命名<a id="1_name"></a>
#### 1.6.1 變數與函式
##### 變數
* 用`小駝峰命名法`(Camel Case)
* 命名前綴為`名詞`(Noun)

##### 函式
* 用`小駝峰命名法`(Camel Case)
* 命名前綴為`動詞`(Verb)

<br>
表1.6.1 函數命名前綴詞參考表

動詞 | 含義 | 
--- | ---
can | 函數回傳一個布林值  
has | 函數回傳一個布林值
is  | 函數回傳一個布林値
get | 函數回傳一個非布林値
set | 函數用來保存一個值

```
var myData = 10;

function getPlusVal(val) {
	return val + val;
}
```

#### 1.6.2 常數
* 用`大寫字母`和`底線`來命名
* 必須宣告於檔案開頭,並且注解標示

```
// const
var MAX_COUNT = 10;

if (count < MAX_COUNT) {
	doSomething();
}
```

#### 1.6.3 全域變數
* 用`小寫g`和`底線`開頭,後面採用一般變數命名方式(小駝峰法)
* 必須宣告於檔案開頭,並且注解標示

```
// global
var g_myVariable = 100;
```


#### 1.6.4 建構函式(Constructor)
##### 用`大駝峰命名法`(Pascal Case), 命名前綴為`名詞`(Noun) <br>
將函式跟建構函式用不同的命名方法,可以幫助我們快速定位問題,<br>
你會知道用`大駝峰命名法命名的函數前面一定會有 new 關鍵字`, 進而避免函式誤用的情況.

```
function Person(name) {
	this.name = name;
}

Person.prototype.sayName = function() {
	alert(this.name);
}

var me = new Person('Hank');
``` 

### 1.7 基本形態(Type)與物件(Object)<a id="1_type"></a>
#### 1.7.1 字串(String)
* 使用`單引號('')`括住字串
* 多行字串用`字串連接符號(+)`連結
* 禁止使用建構函式(Constructor)

```
var myString = 'This is my long string,' +
               'it is just a example.'  
               
// 不好的做法: 使用建構函式
var myString = new String('Hank');
			  
```

#### 1.7.2 數字(Number)
* 禁止使用`8進位`寫法
* 禁止使用建構函式(Constructor)
* 使用`parseInt()`將字串轉為整數時,一定要加上`基數`參數

```
// 好的寫法
var num = 10;

// 不好的寫法: 使用8進位寫法
var num = 010; 

// 不好的寫法: 使用建構函式
var num = new Number(10);

// 好的寫法,有加上基數參數,這行代表將字串'10'轉成10進位整數
var num = parseInt('10', 10);

// 不好的寫法,沒有加上基數參數
var num = parseInt('10');
```

##### 浮點數
* 不可沒有小數部分
* 不可沒有整數部分

```
// 整數
var count = 10;

// 浮點數
var price = 20.0;
var price = 20.00;

// 不好的做法: 使用建構函式
var price = new Number(20);

// 不好的做法: 浮點數沒有小數部分
var price = 20.;

// 不好的做法: 浮點數沒有整數部分
var price = .5;
```

#### 1.7.3 布林値(Boolean)
* 布林値`true`跟`false`所有字元`必須小寫`, 因為其他混合大小寫形式的 true 跟 false 都不是布林値
* 禁止使用建構函式(Constructor)

```
// 布林値
var isBool = true;

// 不好的做法: 布林値字元有大寫
var isBool = True;

// 不好的做法: 使用建構函式
var isBool = new Boolean(true);
```

#### 1.7.3 null

* null所有字元`必須小寫`, 因為其他混合大小寫形式的 null 都不是 null
* 判斷物件是否為null, 請用`嚴格相等(===)`與`嚴格不相等(!==)`符號

##### 請在下列場景`儘量使用` null:
* 當做一個未來可能成為物件的變數的初始值
* 當函式的期望參數是物件時, 可當作參數傳入
* 當函式的期望回傳值為物件時, 可當作回傳值傳出

##### 請在下列場景`儘量不要使用` null:
* 用 null 來檢測是否傳入了某個參數
* 用 null 來檢測變數

```
function doSomething(object) {
	...
}

// 好的寫法:當做一個未來可能成為物件的變數的初始值
var person = null;

// 好的寫法:當函式的期望參數是物件時, 可當作參數傳入
doSomething(null);

// 好的寫法:當函式的期望回傳值為物件時, 可當作回傳值傳出
function getPerson() {

	if (condition) {
		return new Person('hank');
	} 
	else {
		return null;
	}
}

// 不好的寫法: 用 null 來檢測是否傳入了某個參數
function doSomething(arg1, arg2) {

	if (arg2 !== null) {
		doSomething();
	}
}

// 不好的寫法: 用 null 來檢測未初始化的變數
var person;

if (person !== null) {
	doSomething();
}
```
#####簡易檢測變數與參數方法

* 直接用 `if` 判斷變數或參數
* 無論是 `null` 還是 `undefined`, 都會當作 false 處理
* 但是請注意,若變數的值為 `0`, 也會當作 false 處理

```
var person;
var personNull = null;
var personZero = 0;

if (person) { // false
	doSomething();
}

if (personNull) { // false
	doSomething();
}

if (personZero) {	// false
	doSomething();
}

```

#### 1.7.4 undefined
##### 在程式碼中`避免使用undefined`, 理由如下: 
* 因為 undefined 常常會跟 typeof 返回值 'undefined' 混淆.<br>
* 這樣可以確保只有在變數未宣告時 typeof 會回傳 "undefined"
* null == undefined // true, 但是這兩個值的用途大不相同


```
// 使用foo會有錯誤, 因為foo尚未聲明
var person;
alert(typeof person); // "undefined" 
alert(typeof foo);    // "undefined"

// 請用null作為可能成為物件的變數的初始值, 不要用undefined
var person = null;

// 不好的寫法
var person2 = undefined;

// null跟undefined的typeof回傳值不同, 這樣兩者就可以區分開了
alert(typeof person);  // "object"
alert(typeof person2); // "undefined"
```

#### 1.7.5 物件(Object)
* 用物件實字(`{}`)(object literals)建立 Object 物件
* 物件屬性在冒號(`:`)後需空一格

```
// 好的寫法: 物件實字寫法
var person = {
	name: 'hank',
	age: 28,
	skills: 'php, javascript'
};

// 不好的寫法: 物件屬性冒號後沒空一格
var person = {
	name:'hank',
	age:28,
};

// 不好的寫法: 使用Object()
var person = new Object();
person.name = 'hank';
person.age = '28';
person.skills = 'php, javascript';
```

#### 1.7.6 陣列(Array)
* 用陣列實字(`[]`)(array literals)建立Array物件
* 陣列各元素逗號後面需`空一格`


```
// 好的寫法: 使用陣列實字建立陣列
var colors = ['red', 'blue', 'yellow', 'green'];

// 不好的寫法: 使用Array()建立陣列
var colors = new Array('red', 'blue', 'yellow', 'green');

// 不好的寫法: 陣列各元素逗號後面沒空一格
var colors = ['red','blue','yellow','green'];

```

---

##2. 注解<a id="2"></a>
#### 2.1 單行注解<a id="2_single"></a>
##### 單行注解請依照下列規則:
* 獨佔一行的注解, 在注解之前要有`一個空行`, 並跟`下一行程式碼對齊`
* 在程式碼尾部的注解, 需和程式碼之間`空一格(space)`, 注解+程式碼`不得超過單行程式碼長度限制`

```
if (condition) {
	
	// 獨佔一行的注解, 在注解之前要有一個空行, 並跟下一行程式碼對齊
	doSomething();
}

if (condition) {
	doSomething(); // 在程式碼尾部的注解, 需和程式碼之間空一格(space)
}

```

#### 2.2 多行注解<a id="2_multi"></a>
##### 多行注解請依照下列規則:
* 多行注解之前要有`一個空行`, 星號之後要`空一格`, 並跟`下一行程式碼對齊`
* 程式碼尾部的注解, 不要用多行注解
* 可用來`注解掉大段程式碼`或用來寫`程式碼說明`

```
if (condition) {

	/*
	 * 多行注解之前要有一個空行,並跟下一行程式碼對齊,
	 * 程式碼尾部的注解,不要用多行注解
	 */
	doSomething();
	
	
/* 
 * 可用來`注解掉大段程式碼`, 
 * 或用來寫`程式碼說明`
 */
 
 /*
 if (condition) {
 	doSomething();
 }
 */

```

#### 2.3 注解使用時機<a id="2_when"></a>
* 當程式碼所提供的`信息不足以解釋其中的功能與含義`, 必須透過注解提供額外訊息時
* 當程式碼`難以理解`時
* 當程式碼可能被`誤認為是錯誤`時

```
// 改這個值, 系統就爆炸了(注解提供額外訊息)
var count = 10;

// 當程式碼難以理解時
/*
 * 當兩個時間差小於1小時, 就顯示差了分鐘,
 * 當兩個時間差小於1天, 就顯示差了幾小時,
 * 當兩個時間差小於1週, 就顯示差了幾天,
 * 如果這些條件都不成立, 就直接顯示日期
 */
if (diff < ONE_HOUR) {
  output = Math.floor(diff / ONE_MIN) + ' m';
} 
else if (diff < ONE_DAY) {
   output = Math.floor(diff / ONE_HOUR) + ' hr';
} 
else if (diff < ONE_WEEK) {
   output = Math.floor(diff / ONE_DAY) + ' day';
} 
else {
   output = dateSplit[0][0] + '-' + dateSplit[0][1] + '-' + dateSplit[0][2];
}

// 當程式碼可能被誤認為是錯誤時
while (element && (element = element[axis])) { // 這邊是賦値操作無誤
	
	if ((all || element[TAG_NAME]) && (!fn || fn(element)) {
		return element;
	}
}
```

#### 2.4 注解聲明<a id="2_dsrp"></a>
* TODO: 說明`程式碼尚未完成`, 並寫出下一步要做的事情
* HACK: 說明`程式碼用了非正規途徑解決某些問題`, 要寫出為何使用hack的原因,這也表明未來可能有更好的解決方法
* XXX: 說明`程式碼是有問題`的要儘快修復
* FIXME: 說明`程式碼是有問題`的要儘快修復, 重要性僅次於XXX
* REVIEW: 說明`程式碼如果要有任何的改動都需要進行評估與審核`

```
// TODO: 區域函式add尚未完成,請實作
var myToolKit = {
	add: function(val1, val2) {
	
	}
};

/*
 * HACK: 這邊有針對IE8做特別處理,不然會破版
 * 計劃等IE8淘汰過後移除該部分
 */
function myFunc() {
	// 程式碼
} 

// XXX: 這個函式根本是壞的!
function myFunc() {
	// 程式碼
}

// FIXME: 如果輸入null會回傳錯誤,請修復
function myFunc() {
	// 程式碼
}

// REVIEW: 我覺得應該有更好的做法
function myFunc() {
	// 程式碼
}
```

---

##3. 語句和條件判斷式<a id="3"></a>

#### 3.1 大括號<a id="3_brace"></a>
##### 以下條件判斷式一律使用大括號(`{}`)
* if…else
* for
* while
* do…while…
* try…catch…finally

##### 對齊方式與間隔:
* 將左大括號放置在語句中第一句程式碼的尾端
* 在左圓括號之前和右圓括號之後各空一格
* 第二個以後的條件判斷關鍵字開頭要放置在上一個右大括弧後空一格

```
if (codition) {
	doSomething();
} else if(condition) {
	doSomethingElse();
} else { 
	doSomethingElseElse();
}
```

#### 3.2 switch<a id="3_switch"></a>
* 每條 case 語句相對於 `switch `關鍵字縮排4個空格
* 第二條 case 語句開始,每條 case 語句前後各有`一個空行`
* 一般情況, case 末尾一定要`搭配 break 關鍵字,除非為連續執行 case(fall through)`
* 若特殊情況下,需要連續執行 case, 必須在在 case 之間加上注解`/* fall through */`
* ES2015, 如果 case 裡有變數, 請用大括弧避免變數污染
* 無論任何情況, 都`不要省略 default`
* 不要將已知情況寫至 default, 例如有3個狀態 a,b,c. 而 b,c 為同一個邏輯, `不要只寫 a case 而把 b,c 寫至 default`

```
switch (condition) {
	case 1:
		doSomething();
		break;
		
	case 2:
	case 3:
		doSomething();
		break;
		
	case 4:
		doSomething();
		/* fall through */
		
	case 5: {
		let myVar = 'hello';
		doSomething(myVar);
		break;
	}
		
	default:
		break;
}
```

#### 3.3 with<a id="3_with"></a>
##### 避免使用 `with` 關鍵字

#### 3.4 for<a id="3_for"></a>
* 宣告區若有多個變數, 每個變數`各自用 var 宣告並換行`
* 變數之間若是`賦値符號(=)或運算符號(<, >, ==, !=)`, 符號左右需空一格
* 在運算區塊`不要直接使用陣列 length 屬性`, 應該在宣告區將 length 儲存起來使用
* 避免使用 `continue` 關鍵字, 可用條件判斷式取代

```
var values = [1, 2, 3, 4, 5, 6, 7];
var	i;
var	len;
	
for (i = 0, len = values.length; i < len; i++) {
	
	if (i != 2) {
		doSomething(i);
	}
}

// 同等於

for (i = 0; len = values.length; i < len; i++) {
	
	if (i == 2) {
		continue;
	}
	doSomething(i);
}

```

#### 3.5 for-in<a id="3_forin"></a>
* 總是使用 `hasOwnProperty()` 來為 for-in 過濾出物件屬性, 除非想查找原型(protoype)屬性
* 若要查找原型(prototype)屬性, 必需要加上注解說明
* for-in 是用來遍歷物件屬性, 禁止使用 for-in 來遍歷陣列(Array)

```
var person = {
		name: 'hank',
		age: 28	
	},
	prop;

// 總是使用 `hasOwnProperty()` 來為 for-in 過濾出物件屬性, 除非想查找原型(protoype)屬性
for (prop in person) {
	
	if (person.hasOwnProperty(prop)) {
		alert('Property name is ' + prop);
		alert('Property value is ' + person[prop]);
	}
}

// 若要查找原型(prototype)屬性, 必需要加上注解說明
for (prop in person) { // 包含對prototype的遍歷
	alert('Property name is ' + prop);
	alert('Property value is ' + person[prop]);
}

// 禁止使用 for-in 來遍歷陣列(Array)
var values = [1, 2, 3, 4, 5];
var	i;
	
for (i in values) {
	doSomething(i);
} 

```

---

## 4. 變數, 函式<a id="4"></a>
#### 4.1 變數宣告<a id="4_varDeclaration"></a>
* 無論是全域變數或區域變數進行宣告, 變數名稱前面一定要加上 `var` 關鍵字
* 總是將變數宣告作為函式內的第一條語句
* 多個變數宣告時, 每個變數前面加上 `var` 關鍵字, 變數需對齊, 沒有初始值的變數要放在`變數語句的尾部`

```
var g_someValue = 100;

function doSomething() {
	var values = [1, 2, 3, 4, 5, 6, 7];
	var baseValue = 10;
	var result = value + value;
	var i;
	var len;
		
	for (i = 0, len = values.length; i < len; i++) {
		result += i;
	}
}
```

#### 4.1.1 變數宣告位置
* 變數必須宣告在使用它的`程式碼上方`
* 若有多個程式碼區塊使用到同一變數, 宣告在最前面程式碼區塊的上方

```
function doSomething() {

	// 變數可給程式碼區塊 1, 2, 3 使用
	var myVar1 = 1;
	var myVar2 = 2;
	var sum1;
	
	// 程式碼區塊 1
	sum1 = myVar1 + myVar2;
	
	
	// 變數可給程式碼區塊 2, 3 使用
	var myVar3 = 3;
	var myVar4 = 4;
	var sum2;

	// 程式碼區塊 2
	sum2 = myVar1 + myVar2 + myVar3;
	
	
	// 變數可給程式碼區塊 3 使用
	var myVar5 = 5;
	var myVar6 = 6;
	var sum3;
	
	// 程式碼區塊 3
	sum3 = myVar1 + myVar3 + myVar5 + myVar6;
}

```

#### 4.2 函式宣告<a id="4_funcDeclaration"></a>
* 函式名稱和左括號之間沒有空格, 函數右括號`(`與左大括號`{`要空一格
* 函式參數之間用`逗號加空一格`分開, 參數與函式左右括號之間`沒有空格`
* 立即函式要用一對原括號包裹起來
* 函式內部的`局部函式要緊接著變數宣告之後宣告`, 並且使用`函式表達式`
* 如果函式`不會重複使用`, 可使用`匿名函式`
* `函式宣告不可`在條件判斷語句中使用
* `函式表達式可以`在條件判斷語句中使用

```
// 函式宣告
function doSomething(arr, someVal, isFunc) {
	var value = 10,
	var	i;
	var	len;

	// 局部函式要緊接著變數宣告之後宣告, 並且使用函式表達式
	var doSomethingElse = function(obj) {
		
		// 程式碼邏輯
	}
	
	for (i = 0, len = arr.length; i < len; i++) {
		doSomethingElse(arr[i]);
	}
}

// 函式表達式
var doSomething = function(arr, someVal, isFunc) {
	// 程式碼邏輯	
}

// 立即函式宣告
var value = (function(value) {
	return inputValue + 10;
}(inputValue));

// 匿名函式
setTimeout(function() {
	doSomething();
}, 100);

// 匿名立即函式(宣告並立即執行)
(function(value) {
	doSomething();
}(inputValue));

// 不好的寫法: 函數名稱與左括號之間有空格
var myFunc = function() {
	doSomething();
}

// 不好的寫法: 不要在條件判斷語句中宣告函式
if (condition) {
	function doSomething() {
		alert('hello');
	}
} 
else {
	function doSomething() {
		alert('Yeh!');
	}
}
```

#### 4.3 函式參數風格<a id="4_funcParams"></a>
* callback function一律放在參數列的`最後面`
* 如果參數有`兩個以上callback function`, 請使用`函式表達式`,而避免直接使用匿名函式
* 若有大量參數需傳遞給函式, 或是參數數量可能會有多次變動, 請使用`物件`封裝參數

```
// 好的寫法: callback function 放在參數列的最後面
myFunc(val1, val2, function() {
	doSomething();
});

// 好的寫法: 參數有兩個以上callback function, 使用函式表達式
var callback1 = function() {
	doSomething1();
}
var callback2 = function() {
	doSomething2();
}
myFunc(val1, val2, callback1, callback2);

// 好的寫法: 若有大量參數需傳遞給函式, 或是參數數量可能會有多次變動, 使用物件封裝參數
var myFunc = function(profile) {
	alert(profile.name);
	alert(profile.gender);
	alert(profile.phone);
	alert(profile.age);
	alert(profile.job);
}

myFunc({
	name: 'hank',
	gender: 'male',
	phone: '0227119900'
	age: 28,
	job: engineer
});

// 不好的寫法: callback function 沒放在參數列的最後面
myFunc(function() {
	doSomething();
}, val1, val2);

// 不好的寫法: 參數有兩個以上 callback function, 使用匿名函式
myFunc(val1, val2, function() {
	doSomething1();
}, function() {
	doSomething2();
}); 

// 不好的寫法, 大量參數沒用物件封裝
var myFunc = function(name, gender, phone, age, job) {
	doSomething();
}

```


#### 4.4 函式建構式, eval(), setTimeout()和setInterval()<a id="4_funcConstructor"></a>
* `禁止使用 eval()`, 除了別無他法的情況下, eval() 容易產生 XSS 安全性問題 
* setInterval() 跟 setTimeout() 的內容`禁止使用字串, 要用函數`
* 禁止使用建構式(Constructor)


```
// 好的寫法
setInterval(function(){
	alert('Hello');
}, 500);

// 不好的寫法: 內容使用字串
setTimeout('alert("Hello");', 500);

// 不好的寫法: 使用建構式
var func = new Function('alert("Hello!");');
```

#### 4.5 嚴格模式('use strict')<a id="4_strict"></a>
* 不可將` 'use strict' 關鍵字用在全局作用域中`,以避免所有程式碼都用嚴格模式運作, 導致其他未照嚴格模式規範的程式碼發生錯誤

```
// 好的寫法
function doSomething() {
	'use strict'
	// 程式碼邏輯
}

// 好的寫法
(function() {
	'use strict'
	function doSomething() {
		// 程式碼邏輯
	}
	
	function doSomethingElse() {
		// 程式碼邏輯
	}
}());

// 不好的寫法 
'use strict'
function doSomething() {
	// 程式碼邏輯
}
```

---

##5. 運算符<a id="5"></a>
#### 5.1 賦値(=)<a id="5_assign"></a>
* 如果(=)右側是有比較語句的表達式, 要用圓括號()包裹

```
// 好的寫法
var flag = (i < count);

// 不好的寫法
var flag = i < count;
```

#### 5.2 相等操作符(===, !==, ==, !=)<a id="5_equal"></a>
* 檢測類型總是使用(`===`)與(`!==`),請參考[7.1](#7_type)
* 若無特別需要避免有隱含型別轉換的狀況,可用(`==`)和(`!=`);


```
var checkValue = 2;
var myValue = '2';

// 使用==或!=會自動將字串'2'轉為數字2
if (checkValue == myValue) { // true
	...
}

if (checkValue === myValue) { // false
	...
}
```

#### 5.3 三元運算子(? :)<a id="5_triple"></a>
* 僅用在`賦値操作`, 不可當作if使用
* (?)與(:)符號`左右需個空一格`

```
// 好的寫法
var value = condition ? value1 : value2;

// 不好的寫法
condition ? myFun1() : myFun2();
```

---

##6. 錯誤處理<a id="6"></a>
#### 6.1 Error物件<a id="6_error"></a>
##### 6.1.1 基本錯誤類型
1. Error: 基本錯誤物件
2. EvalError: `eval()發生錯誤`時拋出
3. RangeError: `數值超出範圍`時拋出(**經常發生**)
4. ReferenceError: `找不到物件`時拋出
5. SyntaxError: `語法錯誤的程式碼傳入eval()`時拋出
6. TypeError: `變數被賦値意外的類型或呼叫不存在的方法`時(**經常發生**)
7. URIError: encodeURI(), encodeURIComponent(), decodeURI() 或decodeURIComponent()等傳遞`非法格式`時拋出

```
new eval(); // EvalError,FireFox 4+和IE8會拋出TypeError

var items = Array(-100); // RangeError

var obj = myObj; // ReferenceError

eval('a ++ b'); // SyntaxError

var a = new '1234'; // TypeError
alert('name' in true); //TypeError
Function.prototype.toString.call('name') //TypeError

```

##### 6.1.2 客制化錯誤類型
```
function CustomError(message) {
	this.name = 'myCustomError';
	this.message = message;
}
CustomError.prototype = new Error();


function doSomething(obj) {
	
	if (obj === null) {
		throw new CustomError('Oops!');
	}
}

try {
	doSomething(null);
} 
catch(error) {
	alert(error.name + ' ' + error.message); // myCustomError Oops!
}

```

#### 6.2 throw<a id="6_throw"></a>

* `throw` 負責引發異常
* 總是使用 `Error` 物件或其子類別物件拋出錯誤

```
// 好的寫法
throw new Error('Something went wrong!');

// 不好的寫法
throw new 'Something went wrong!';
throw true;
throw 123;
throw new Date();
```

#### 6.3 try-catch<a id="6_trycatch"></a>
* `catch` 負責捕捉異常
* `catch` 區塊不要留空
* 可用 `finally` 區塊,無論程式碼有無錯誤發生,finally區塊內的程式碼總是會被執行
* 小心使用 `finally` 區塊,只要有 `finally` 區塊, try 跟 catch 區塊的` return 都會被忽略`

```
// 好的寫法
try {
	doSomething();
} 
catch(error) {
	handleError(ex);
}

// 好的寫法
try {
	// 程式碼
} 
catch(error) {
	// 捕捉錯誤
} 
finally {
	// 無論try區塊有無錯誤發生,finally區塊總是會被執行
}

// 不好的寫法: catch區塊留空
try {
	doSomething();
} 
catch(error) {

}

// try-catch, throw應用範例
function getLastElement(array) {
	
	if (array.length > 0) {
		return array[array.length - 1];
	} 
	else {
		throw new Error('Cannot not take the last element of an empty array.');
	}
}

try {
	getLastElement([]);
} 
catch(error) {
	alert(error.message);
}
```

---

## 7. 類型檢測<a id="7"></a>
#### 7.1 檢測基本類型<a id="7_type"></a>
* String, Number, Boolean, undefined用`typeof`關鍵字
* null用`===`和`!==`, `禁止使用typeof檢測null`, 因為會返回'object'
* typeof String 回傳 'string'
* typeof Number 回傳 'number'
* typeof Boolean 回傳 'boolean'
* typeof undefined 回傳 'undefined'

```
var myString = 'hello world!';
var	myNumber = 10;
var	myBoolean = true;
var	myNull = null;

// String	
if (typeof myString === 'string') {
	doSomething();
}

// Number
if (typeof myNumber === 'number') {
	doSomething();
}

// Boolean
if (typeof myBoolean === 'boolean' && myBoolean) {
	doSomething();
}

// undefined
if (typeof myUndefined === 'undefined') {
	doSomething();
}

// null
if (myNull === null) {
	doSomething();
}
```
#### 7.2 檢測內建物件(Object, Array, Date, Error)與自定義物件<a id="7_object"></a>

* 用 'instanceof' 關鍵字
* 'instanceof' 不僅會檢查物件的建構函式(Constuctor), 也會檢查該物件的原型(Prototype), 因此避免使用 `myObject instanceof Object` 來檢測物件是否屬於某個特定物件

```
var myDate = new Date();
var myError = new Error('help!');
var	myPerson = new Person('Hank');
	
function Person(name) {
	this.name = name;
}

// 好的做法
if (myDate instanceof Date) { // true
	doSomething();
}

// 好的做法
if (myError instanceof Error) { // true
	doSomething();
}

// 好的做法
if (myPerson instanceof Person) { // true
	doSomething();
}

// 不好的做法: 用 Object 檢測物件
if (myPerson instanceof Object) { // true

}
```

#### 7.3 檢測函式<a id="7_func"></a>

* 使用 `typeof` 關鍵字
* 注意,在 IE8 以下的瀏覽器,使用 `typeof` 檢測 DOM 的函式(例如 document.getElementById),會回傳 `object` 而不是 `function`, 因此要用 `in` 來檢測

```
function myFunc() {
	// 程式碼
}

if (typeof myFunc === 'function') { // true
	doSomething();
}

// IE8以下瀏覽器DOM函式檢測方法
if ('getElementById' in document) {
	doSomething();
}
```

#### 7.4 檢測陣列<a id="7_array"></a>

* 可用 Kangax 解決方案
* ECMAScript5 可用 Array.isArray()
* IE9+, Chrome, FireFox 4+, Safari 5+, Opera 10.5+ 都有 Array.isArray()

```
var myArr = [1, 2, 3, 4, 5];

// Kangax 解決方案
function isArray(value) {
	return Object.prototype.toString.call(value) === '[object Array]';
}

if (isArray[myArr]) {
	doSomething();
}
```

#### 7.5 檢測屬性<a id="7_attr"></a>

* 用 `in` 來檢測
* 如果只想檢查物件某個屬性是否存在(略過 prototype 屬性)，可使用 `hasOwnProperty()` 方法
* IE8 以下的 DOM 物件並非繼承自 Object, 因此不包含 hasOwnProperty()這個方法, 因此請使用 `in` 運算符

```
var person = {
	name: 'hank',
	age: 28
};

// 用 in 來檢測
if ('name' in person) {
	doSomething();
}

// 對於非 DOM 物件的屬性檢測方法
if (person.hasOwnProperty('name')) {
	doSomething();
}

// 如果不確定是否為 DOM 物件
if ('hasOwnProperty' in person && person.hasOwnProperty('name')) {
	doSomething();
}
```

## 8. 嚴格模式(Strict mode)<a id="8"></a>
#### 8.1 宣告嚴格模式<a id="8_declare"></a>

* 可以在檔案、程式或函式的開頭加上 `"use strict"`; 宣告 Strict 模式
* Strict 模式宣告的範圍取決於宣告本身的內容. 如果在全域內容中 (在函式範圍之外) 宣告, 則程式中的所有程式碼都會套用 Strict 模式； 如果是在函式宣告，則函式中的所有程式碼都會套用 Strict 模式

```
// 在'use strict'以下的所有程式碼都會套用 Strict 模式
'use strict';
function testFunction(){
    var testvar = 4;
    return testvar;
}

// ReferenceError: assignment to undeclared variable testvar
testvar = 5;
```

```
/* 
  只有 testFunction 內的程式碼才會套用 Strict 模式. 
  函式以外的變數宣告不會導致語法錯誤, 但是函式中的宣告則會.
*/
function testFunction(){
    'use strict';
    
    // ReferenceError: assignment to undeclared variable testvar
    testvar = 4;
    return testvar;
}
testvar = 5;

```

#### 8.2 嚴格模式下的限制<a id="8_rule"></a>
##### 8.2.1 變數
* 不可使用未宣告的變數

```
'use strict';

// ReferenceError: assignment to undeclared variable testvar
testvar = 4;
```

##### 8.2.2 唯讀屬性
* 不可將值寫入到唯讀屬性

```
'use strict';

var testObj = Object.defineProperties({}, {
    prop1: {
        value: 10,
        writable: false // by default
    },
    prop2: {
        get: function () {
        }
    }
});

// TypeError: "prop1" is read-only
testObj.prop1 = 20; 
testObj.prop2 = 30;
```

##### 8.2.3 物件無法擴充屬性
* 當物件設為無法擴充時, 為物件新增屬性會發生錯誤

```
'use strict';

var testObj = new Object();

Object.preventExtensions(testObj);

// TypeError: ({}) is not extensible
testObj.name = "Bob";
```

##### 8.2.4 delete
* 無法刪除宣告的變數(沒嚴格模式時, 也不會刪除, 但不會拋出錯誤)
* 無法刪除 configurable 設為 false 的屬性

```
var testvar = 15;
function testFunc() {};

// SyntaxError: applying the 'delete' operator to an unqualified name is deprecated
delete testvar;
delete testFunc;

Object.defineProperty(testObj, "testvar", {
    value: 10,
	configurable: false
});

// TypeError: property "testvar" is non-configurable and can't be deleted
delete testObj.testvar;
```

##### 8.2.5 重複屬性
* 不可多次定義同一屬性

```
'use strict';

// SyntaxError: property name prop1 appears more than once in object literal
var testObj = {
    prop1: 10,
    prop2: 15,
    prop1: 20
};
```

##### 8.2.6 重複函式參數名稱
* 在函式不可多次定義同一參數

```
'use strict';

// SyntaxError: duplicate formal argument param1
function testFunc(param1, param1) {
    return 1;
};
```

##### 8.2.7 保留未來使用的關鍵字
以下關鍵字皆不可當作變數宣告使用:

* implements
* interface
* let
* package
* private
* protected
* public
* static
* yield

```
'use strict';

// SyntaxError: implements is a reserved identifier
var implements = 10;

```

##### 8.2.8 八進位值
* 不可將八進位值指派給變數
* 不可使用八進位溢出字元(經測試沒用嚴格模式也會發生錯誤)

```
'use strict';

// SyntaxError: octal literals and octal escape sequences are deprecated
var testoctal = 010;

// SyntaxError: illegal character
var testescape = \010;
```

##### 8.2.9 this
* 如果this的值為 `null` 或 `undefined` ,就無法轉換成全域物件

```
'use strict';

function testFunc() {
    return this;
}
var testvar = testFunc();

alert(testvar); // undefined, 若非嚴格模式在瀏覽器執行則是[object Window])
```

##### 8.2.10 eval 不可當作變數名稱

```
'use strict';

// SyntaxError: redefining eval is deprecated
var eval = 10;
```

##### 8.2.11 不可使用在 eval 函式內宣告的變數

```
'use strict';

// ReferenceError: assignment to undeclared variable testvar
eval("var testvar = 10");
testvar = 15;
```

##### 8.2.12 不可在陳述式或區塊內宣告函式
* 在 Strict 模式中，函式宣告不可以巢狀在陳述式或區塊內部。 它們只可以出現在最上層或直接位於函式主體內。

```
'use strict';

var arr = [1, 2, 3, 4, 5];
var index = null;

for (index in arr) {

	// SyntaxError: in strict mode code, functions may be declared only at top level or 
	   immediately within another function
    function myFunc() {};
}
```

##### 8.2.13 arguments 不可當作變數名稱

```
'use strict';

// SyntaxError: redefining arguments is deprecated
var arguments = 10;
```

##### 8.2.14 不可使用 arguments.callee

```
'use strict';

function test(testInt) {
    
    if (testInt-- == 0) {
        return;
    }
    
    // TypeError: 'caller', 'callee', and 'arguments' properties may not be accessed on 
       strict mode functions or the arguments objects for calls to them
    arguments.callee(testInt--);
}
```

##### 8.2.15 不可使用 with


```
'use strict';

// SyntaxError: strict mode code may not contain 'with' statements
with (Math) {
    x = cos(3);
    y = tan(7);
}
```

---


## 附錄A. 參考資料<a id="appendixA"></a>
#### 附錄A.1 網路資源<a id="appendixA_web"></a>
1. [Crockford JavaScript Code Conventions](http://javascript.crockford.com/code.html)
2. [Google JavaScript Style Guide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)
3. [jQuery JavaScript Style Guide](http://contribute.jquery.org/style-guide/js/)

#### 附錄A.2 書籍<a id="appendixA_book"></a>
1. JavaScript Patterns, O'Reilly[原文版](http://shop.oreilly.com/product/9780596806767.do) [繁中版](http://www.books.com.tw/exep/prod/booksfile.php?item=0010538538)
2. Maintainable JavaScript, O'Reilly [原文版](http://shop.oreilly.com/product/0636920025245.do) [簡中版](http://product.dangdang.com/product.aspx?product_id=23200995)
3. Professional JavaScript for Web Developers(3rd Edition), Wrox [原文版](http://www.amazon.com/Professional-JavaScript-Developers-Nicholas-Zakas/dp/1118026691) [簡中版](http://product.dangdang.com/product.aspx?product_id=22628333)