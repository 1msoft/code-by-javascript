*简单来说javascript代码的执行机制是单线程下的异步执行*

*不管javascript语言多么优秀，改变不了它的出生：脚本语言。 所以不要用它来替代c和java这样的语言，但是java本来就干着不适合的工作。*

*典型的应用场景是：请求--响应， 比如UI操作的，web请求的处理，实时消息的处理。响应响应代码的执行控制在毫秒级。*

## 一、engine 机制
### 有两种callback
### event loop
### time and tick
### job queue

## 二、语法

### promise

### yield

### async/await


## 三、如何组织你的程序

### 用户主程序

用户主程序是程序的入口，完成以下功能

+ loader
+ initialize
+ register event listener
+ message dispatch
+ state contol

### 分解处理过程

通过主程序或框架，把处理过程进行了第一层级的分解， 一般情况下对于event或message的handler只需要简单的响应函数就可以完成大部分功能， 但对于需要连续处理的情况则需要将处理过程分成若干个step， 同步或异步执行。

### 区分同步代码和异步代码

把异步代码用promise、generator和async封装起来，表明该处理过程在以后才会执行完成。

### 各种上下文，规划好heap


*简单函数有最简单的上下文，对象方法有事先声明的上下文， 闭包、Generator，Promise有隐含的上下文， 还可以动态绑定或修改函数的上下文。*
 
