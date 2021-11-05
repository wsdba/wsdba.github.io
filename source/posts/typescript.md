```
title: typescript学习笔记
date: 2021.10.28 11.20
tags: JavaScript Typescript
description: 百尺竿头，更进一步
```

# 五分钟入门
### 1.安装typescript
npm install -g typescript
### 2.构建你的第一个TypeScript文件
```javascript
function greeter(person) {
    return "Hello, " + person;
}

let user = "Jane User";

document.body.innerHTML = greeter(user);
```

### 3.编译代码
tsc greeter.ts

---
# 基础类型
### 1.布尔值
let isDone: boolean = false;
### 2.数字类型
```javascript
let decLiteral: number = 6;  
let hexLiteral: number = 0xf00d;  
let binaryLiteral: number = 0b1010;  
let octalLiteral: number = 0o744;  
```

### 3.字符串
```javascript
let name: string = "bob";

name = "smith";
```
你还可以使用模版字符串，它可以定义多行文本和内嵌表达式。 这种字符串是被反引号包围（ `），并且以${ expr }这种形式嵌入表达式
```javascript
let name: string = `Gene`;

let age: number = 37;

let sentence: string = `Hello, my name is ${ name }.

I'll be ${ age + 1 } years old next month.`;
```
这与下面定义sentence的方式效果相同：
```javascript
let sentence: string = "Hello, my name is " + name + ".\n\n" +
    "I'll be " + (age + 1) + " years old next month.";
  ```  
### 4.数组
```javascript
let list: number[] = [1, 2, 3];  
let list: Array<number> = [1, 2, 3];
  ```  
### 5.元组 Tuple
元组类型允许表示一个已知元素数量和类型的数组，各元素的类型不必相同。 比如，你可以定义一对值分别为 string和number类型的元组。
```javascript
let x: [string, number]; 

x = ['hello', 10]; // OK

x = [10, 'hello']; // Error
  ```  
当访问一个已知索引的元素，会得到正确的类型：  
```javascript
console.log(x[0].substr(1)); // OK  
console.log(x[1].substr(1)); // Error, 'number' does not have 'substr' 
  ```  
当访问一个越界的元素，会使用联合类型替代：  
```javascript
x[3] = 'world'; // OK, 字符串可以赋值给(string | number)类型  
console.log(x[5].toString()); // OK, 'string' 和 'number' 都有 toString  
x[6] = true; // Error, 布尔不是(string | number)类型
  ```  
  
### 6.枚举
enum类型是对JavaScript标准数据类型的一个补充  
```javascript
enum Color {Red, Green, Blue}  
let c: Color = Color.Green;
  ```  
  
### 7.Any
```javascript
let notSure: any = 4;  
notSure = "maybe a string instead";  
notSure = false;
  ```  
### 8.Void
### 9.Null 和 Undefined
### 10.Never
永不存在的值的类型。 例如， never类型是那些总是会抛出异常或根本就不会有返回值的函数表达式或箭头函数表达式的返回值类型

### 11.Object

### 12.let

---

### <注意>
- 1.TypeScript提供了静态的代码分析，它可以分析代码结构和提供的类型注解。
- 2.++在TypeScript里，++只在两个类型内部的结构兼容那么这两个类型就是兼容的++。 ==这就允许我们在实现接口时候只要保证包含了接口要求的结构就可以，而不必明确地使用 implements语句。==++

- 3.TypeScript支持JavaScript的新特性，比如支持基于类的面向对象编程。

- 4.在构造函数的参数上使用public等同于创建了同名的成员变量



测试图片
