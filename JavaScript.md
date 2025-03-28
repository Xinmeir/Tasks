
# JavaScript 数据类型详解（附完整示例）

## 一、基本数据类型（Primitive Types）

### 1. 字符串（String）
#### 定义
表示文本数据，用单引号('')、双引号("")或反引号(``)包裹

#### 特性
- 不可变性：每次操作都会生成新字符串
- 支持Unicode字符
- 模板字符串支持插值表达式

#### 示例
```javascript
let str1 = 'Hello';                     // 单引号
let str2 = "World";                     // 双引号
let str3 = `当前温度：${25}℃`;          // 模板字符串
let str4 = "中文测试\u00A9";            // Unicode字符
let str5 = "Line1\nLine2";              // 转义字符

// 常用方法
console.log(str1.length);               // 5
console.log(str1.concat(' ', str2));    // Hello World
console.log(str2.slice(1, 3));          // or
console.log(str3.includes("温度"));      // true
```

---

### 2. 数字（Number）
#### 定义
表示整数和浮点数，采用IEEE 754双精度格式

#### 特性
- 所有数字均为64位浮点数
- 特殊值：Infinity、-Infinity、NaN
- 精度问题：0.1 + 0.2 ≠ 0.3

#### 示例
```javascript
let num1 = 42;                          // 整数
let num2 = 3.1415;                      // 浮点数
let num3 = 5e3;                         // 科学计数法 → 5000
let num4 = 0xFF;                        // 十六进制 → 255
let num5 = 1/0;                         // Infinity
let num6 = Number('abc');               // NaN

// 常用方法
console.log(num2.toFixed(2));           // 3.14
console.log(Number.isInteger(num1));    // true
console.log(Number.MAX_SAFE_INTEGER);   // 9007199254740991
console.log(0.1 + 0.2);                 // 0.30000000000000004
```

---

### 3. 布尔（Boolean）
#### 定义
表示逻辑真假的两种状态：true/false

#### 特性
- 自动类型转换规则：
  - false值：0, "", null, undefined, NaN, false
  - true值：其他所有值

#### 示例
```javascript
let bool1 = true;
let bool2 = false;

// 自动转换示例
console.log(Boolean(''));               // false
console.log(Boolean(0));                // false
console.log(Boolean({}));               // true
console.log(!!undefined);               // false

// 逻辑运算
console.log(true && 'Hello');           // Hello（短路返回）
console.log(false || 'Default');        // Default
```

---

### 4. Null
#### 定义
表示"空"的**特殊对象类型**（typeof返回object）

#### 特性
- 必须显式赋值：let a = null;
- 表示故意设置的空值
- 历史遗留：typeof null → 'object'

#### 示例
```javascript
let emptyVar = null;
console.log(typeof emptyVar);           // object
console.log(null == undefined);         // true（宽松相等）
console.log(null === undefined);        // false（严格相等）
```

---

### 5. Undefined
#### 定义
表示变量已声明但未初始化

#### 特性
- 默认初始值：未赋值的变量
- 函数无return时返回undefined
- 访问对象不存在的属性

#### 示例
```javascript
let uninitialized;
function test() {}
let obj = {};

console.log(uninitialized);             // undefined
console.log(test());                    // undefined
console.log(obj.nonExist);              // undefined
console.log(void 0);                    // 显式生成undefined
```

---

## 二、引用数据类型（Reference Types）

### 6. 对象（Object）
#### 定义
键值对的集合，使用{}或new Object()创建

#### 特性
- 属性名可以是字符串或Symbol
- 原型继承机制
- 引用传递特性

#### 示例
```javascript
// 创建对象
let person = {
  name: 'Alice',
  age: 25,
  'full name': 'Alice Smith',           // 特殊属性名
  sayHi() { console.log('Hello!') }     // 方法定义
};

// 操作属性
console.log(person.name);               // Alice
person.age = 26;                        // 修改属性
person.country = 'USA';                 // 添加属性
delete person.age;                      // 删除属性

// 特殊特性
let obj1 = { a: 1 };
let obj2 = obj1;                        // 引用复制
obj2.a = 2;
console.log(obj1.a);                    // 2
```

---


### 7. 数组（Array）
#### 定义
有序数据集合，本质是特殊对象（typeof返回object）

#### 特性
- 索引从0开始
- 动态长度
- 支持稀疏数组
- 原型包含丰富方法

#### 示例
```javascript
// 创建数组
let arr1 = [1, 2, 3];                   // 字面量
let arr2 = new Array(5);                // 长度5的空数组
let arr3 = Array.from('hello');         // ['h','e','l','l','o']

// 常用操作
arr1.push(4);                           // [1,2,3,4]
arr1.pop();                             // [1,2,3]
arr1.forEach(n => console.log(n*2));    // 2,4,6

// 高级方法
let doubled = arr1.map(n => n*2);       // [2,4,6]
let sum = arr1.reduce((a,b) => a+b);    // 6
let matrix = [[1,2], [3,4]];           // 多维数组
```

---

## 三、特殊注意事项

### 类型检测方法
```javascript
typeof "str"        // "string"
typeof 42           // "number"
typeof true         // "boolean"
typeof undefined    // "undefined"
typeof null         // "object"（历史遗留问题）
typeof {}           // "object"
typeof []           // "object"
Array.isArray([])   // true（推荐数组检测方法）
```

### 类型转换规则
| 原始值         | 转换为数字 | 转换为字符串      | 转换为布尔值 |
|----------------|------------|-------------------|--------------|
| ""             | 0          | ""                | false        |
| "123"          | 123        | "123"             | true         |
| "12.3"         | 12.3       | "12.3"   