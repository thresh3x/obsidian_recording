#### 1语义标签
header，nav，section，aside，artical，footer
1. 有利于SEO（search engine optimization），有助于网页爬虫爬取更多信息，因为爬虫是依赖于标签来确定上下文和各个关键字的权重。
2. 方便其他设备的解析（屏幕阅读器，移动设备）
3. 增加代码可读性，遵循规范，减少差异化

#### 2增强型表单
###### 新的form表单类型
1. 邮箱验证 input type="email"
2. 数值输入 type=“number” max="" min =""
3. 文件导入 input type="file" mulitiple，form enctype=“multipart/form-data”
4. 图片按钮 input type=“image”
5. 颜色选择 type=“color”
6. 日期选择 type=“date”
7. 搜索框 type=“search”
8. 手机号输入框（主要用于移动端，pc端没什么效果）type=“tel”
9. 网址输入框 type=“url”
###### 新的表单属性
1. placehoder 在输入框提示占位符
2. required
3. autofocus
4. autocomplete 默认是on，email默认是off。功能是提示写过的信息，一定要和name一起用
5. min和max

#### 3视频和音频
###### video 
	支持ogg，MP4，webm。 可以嵌套多个video标签，用于表现一个播放源的多种播放方式，第一个视频格式不支持会轮到下一个标签。
- 方法：play(), pause(), load()
- 属性：width, height, controls(boolean)
###### audio
	支持格式ogg，Wav，mp3。可以嵌套多个video标签。
- 属性：autoplay，controls，loop，muted，poster

#### 4canvas绘图
js使用dom获取对象，使用方法getContext("2d")获取上下文，创建context对象，获取2d绘制环境。
通过js脚本控制绘制。

#### 5svg绘图
使用xml描述2d图形的语言。xml功能是传输和储存数据。
svg比起canvas不容易失帧，更稳定。

#### 6地理位置
navigator.geolocation.getCurrentPosition() 
return latitude, longitude, altitude, heading, speed

#### 7拖放API
一个元素默认是拖拽属性是draggable="false"
监听被拖放对象dragstart事件记录拖拽对象引用。默认是不能把元素放置到其他元素中，所以需要在其他元素添加事件监听dragover里面preventDefault，监听drop删除原来拖拽对象，在新的元素中加入拖拽对象引用。

#### 8Web Worker
web worker是运行在后台的JS。
为js创建多线程环境。js在主线程中执行，new一个子线程在后台执行。worker完成任务返回到主线程，子线程代码不会造成主线程的阻塞。有的如Safari，IE浏览器不支持。
w = new Worker("worker134.js")
w.onmessage = function(message) {}
w.postmessage('134')
w.terminate()
Web Worker可分为专用线程Dedicated Worker 和共享线程Shared Worker。
专用线程Dedicated Worker 只能从创建它的脚本中访问，而共享线程Shared Worker可以被多个脚本访问。
**Web Worker有五个限制**
	1. 同源限制，分配给worker线程的脚本必须与主线程的脚本文件同源
	2. DOM限制，worker只能读取navigator对象和location对象，无法使用window，document，parent对象。因为worker所在的全局对象和主线程不同。
	3. 通信联系，主线程和子线程无法直接通信，因为它们不在同一个环境。只能使用postMessage和onMessage，并且在数据传输时候，Worker使用的是拷贝的方法。
	4. 脚本限制，worker线程不能执行alert()和confirm()方法，但可以使用XMLHttpRequest发送AJAX请求。
	5. 文件限制，worker线程不能读取本地文件，加载脚本必须来源于网络。
**Worker中书写**
worker执行上下文名称是self。
加载其他文件importScript(‘13.js’, '127.js')

#### 9Web Storage
HTML4中用cookie，在用户端保存数据，但内存只有4kb，操作复杂，发送数据时一同发送。
Web Storage一般有5Mb，
1. localStorage
2. sessionStorage
相同点
1. 数据都保存在客户端
2. 同源
3. 操作方法相同
不同点
1. 生命周期不同。localStorage是永久保存，除非用户手动清除。sessionStorage是临时保存，关闭浏览器即数据消失。
2. 作用域不同。localStorage信息可以在相同浏览器中同源的不同也买你