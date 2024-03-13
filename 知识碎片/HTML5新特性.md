#### 语义标签
header，nav，section，aside，artical，footer
1. 有利于SEO（search engine optimization），有助于网页爬虫爬取更多信息，因为爬虫是依赖于标签来确定上下文和各个关键字的权重。
2. 方便其他设备的解析（屏幕阅读器，移动设备）
3. 增加代码可读性，遵循规范，减少差异化

#### 增强型表单
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

#### 视频和音频
###### video 
	支持ogg，MP4，webm。 可以嵌套多个video标签，用于表现一个播放源的多种播放方式，第一个视频格式不支持会轮到下一个标签。
- 方法：play(), pause(), load()
- 属性：width, height, controls(boolean)
###### audio
	支持格式ogg，Wav，mp3。可以嵌套多个video标签。
- 属性：autoplay，controls，loop，muted，poster

