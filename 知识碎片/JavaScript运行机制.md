JavaScript解释性语言，边编译，边执行。
JavaScript是由浏览器中嵌入的V8引擎来解释。
JavaSctipt解释以后，CPU来执行。执行后渲染至页面。

##### JavaScript引擎
- **V8**(Google)，用C++编写，开放源代码，由Google丹麦开发，是Google Chrome的一部分，也用于Nodejs
- JavaScriptCore(Apple)
- Rhino(Mozilla)
- SpiderMonkey(Mozilla)

###### V8引擎
script text -- parser --> AST -- Ignition --> Byte code -- execution --> 执行后会feedback反馈回去，反作用于解释器，比如对于多次执行的代码进行缓存

