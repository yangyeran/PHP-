# HTML

### 了解软件结构

* C/S结构(客户端client/服务器server)

  特点：

  1.  C/S软件通常需要特定的客户端来使用
  2. 可以通过任意协议来通信
  3. C/S软件的客户端有数据处理和存储的能力，可以把应用软件的计算机和数据分配在客户端和服务器端。        

* B/S结构(浏览器browser/服务器)

  特点：

  1. 不需要特定的客户端
  2. 和服务器通信使用HTTP协议
  3. 所有的数据都存在服务器上（数据相对安全）B/S

  优缺点：

  1. B/S结构相较于C/S结构用起来比较方便，不需要下载特定的客户端
  2. B/S维护、升级更方便。
  3. 成本低，不用开发特定的客户端
  4. 数据相对安全
  5. 应用服务器运行数据负荷较重

### HTTP协议

1. 超文本传输协议（Hyper Text Transfer Protcol）
2. 互联网上应用最广泛的一种网络协议
3. 设计HTTP协议的目的就是为了提供一种发布和接收HTML页面的方法
4. HTTP就是用于从服务器传输超文本到本地浏览器的传输协议

* HTTP协议的简单工作过程

  1. 浏览器首先通过网络访问服务器80端口和服务器建立连接
  2. 浏览器向服务器发送请求命令，并将自己的一些信息发送给浏览器，这些信息不会明确显示出来
     * 请求时HTTP协议可以通过多种方法进行请求的发送
     * GET方法：用来请求、访问已经被URL标识的资源（地址栏输入的内容默认使用GET方式传输）
  3. 服务器收到客户端发送的请求以后，服务器会回应客户端发送的请求
  4. 关闭客户端和服务器之间的联系

  返回的状态码：

  * 200 表示成功
  * 403 表示访问被拒绝
  * 404 页面没找到

* 常看到的协议

  1. https:// 安全套接的协议 （传输是加密的）
  2. ftp:// 文件传输协议
  3. file:/// 本地文件协议

### 一.HTML标签相关

#### 1.HTML标签

标签是HTML的最基本单位，也是最重要的组成部分，通常使用两个<>括号括起来的

- 标签有两种形式：

  1.成对标签（双标签）

  ```html
  <p>内容</p>
  ```

  2.不成对标签（单标签）

  ```html
  <hr />
  ```

#### 2.HTML大小写问题

- 标签不区分大小写，<body><BODY>意思一样。**HTML标签推荐小写**

#### 3.标签的属性

1.HTML属性一般都出现在HTML标签中，是HTML标签的一部分。

2.标签可以有属性，包含了额外的信息，属性的值一定要在双引号中。而且标签还可以存在多个属性。

3.一般属性由属性名和属性值成对出现：

4.语法：<标签名  属性名1=“属性值” 属性名2=“属性值”></标签名>

#### 4.HTML颜色值设置

1.浏览器支持颜色名称集合，颜色值是一个关键字或者一个RGB格式的数字，在网页中用的很多。

2.使用英文单词作为颜色值：

- red | green |blue | pink 粉色 |purple  紫色

3.六位的十六进制颜色值：R G B

- #00f  蓝色  #00  00  ff   与R G B 对应前两位表红，中间两位表绿，最后两位表蓝

#### 5.HTML注释

- 格式：

  ``` html
  <!--书写注释的内容-->
  ```

#### 6.HTML代码格式

- 任何回车或者空格在源代码中都不起作用，所以需要对其进行排版，一般是一个tab

#### 7.HTML实体字符

- ```html
  &lt;(小于号)  &gt;(大于号)
  ```

- ```html
  &nbsp;(空格)
  ```

- ```html
  &copy;(版权符号)
  ```

### 二.HTML的主体结构

```html
<!DOCTYPE html>
<html>
    <head></head> 
    <body></body>
</html>
```

1.最顶部声明<!DOCTYPE html>

- 声明是文档的第一部分，位于文档的最顶部。
- 该声明告诉浏览器所使用的HTML规范（H5的规范，所有浏览器都适用）

2.以<html>开始，以</html>结束，中间包含头部标签<head></head>及主体标签<body></body>

### *三.head标签中常用的标签

```html
<head lang="en">
    <!-- 
	lang是language的意思，lang="en"属性对页面声明主要语言，en表示英语，zh-cn表示中文。
	搜索引擎不会判断该站点是中文还是英文，他让搜索引擎知道你的站点是中文站，这些都是HTML规范，越规范，越容易被收录
	-->
    <title></title>设置网页标签
    <meta />是对页面的描述
    <meta charset="utf-8"/> 设置页面字符集 HTML5
    <!--http-equiv 告知浏览器的行为-->
    <meta http-equiv="content-type" content="text/html;charset=utf-8" /> HTML4设置页面字符集方式
    <meta http-equiv="refresh" content="3"/> 页面三秒刷新一次
    <!--refresh 刷新 , content 设置时间 -->
    <meta http-equiv="refresh" content="3;url=https://github.com/yangyeran" /> 告知浏览器3s跳转到设置的网址
    <!--三秒刷新后跳转到url指向的网址，注意设置时间的引号要一直引到所要跳转的网址最后-->
    
    <!--name 告知浏览器的内容-->
    <meta name="keywords" content="关键字，关键字，多个关键字使用英文状态下的逗号分隔" />  设置网站关键字
	<meta name="description" content="描述内容" />
    <!-- meta name="里面可以写其他的，可以查找"-->
    <link /> 定义两个文档之间连接的关系
    <link rel="icon" type="imge/png" href="./img/WechatIMG259.png"/>  设置网页标题图标
    <!--这里是个例子./img/WechatIMG259.png这个就是个路径-->
    <!--
		rel  = "表示文档与被连接文档之间的关系"
		type = "被连接文档的类型" (具体类型可以搜mime类型来查看)
		(type可省略,会自动识别)
		href = "被连接文档的地址"
	-->
    <link rel="stylesheet" type="test/css" href="./css.css"/> 加载css文件
    <style></style> 加载css样式
    <script></script> 加载js样式
    <!--阻止移动浏览器自动调整页面大小-->
    <meta name="viewport" content="initial-scale=2.0,width=device-width" />
    <!--
	name ="viewport" 说明此meta标签定义视口的属性
	initial-scale=2.0 意思是将页面放大两倍
	width = device -width 告诉浏览器页面的宽度的能与设备的宽度
	-->
    <meta name="viewport" content="width=device-width,maximun-scale=3,minmum-scale=0.5" />
    <!--允许用户将页面最大放大至设备宽度的3倍，最小缩小至设备宽度的一半-->
    <meta name="viewport" content="initial-scale=1.0,user-scalable=no" />
    <!--禁止用户缩放，可以在混合APP时，为了使html页面更逼真，使页面无法缩放。user-scalable=no 是禁止缩放-->
</head>
```

### 四.HTML常用标签

#### 1.文本与文本格式标签

```html
<p></p> 段落标签 <!--特点：与上行文本和下行文本之间间隔一行，重复会有高度的合并-->
<!--
	属性：alige 控制内容方向。取值:keft 默认居左、center 居中、right 居右
		 title 设置标题(很多标签都可以设置标题)
-->
<b></b> 加粗标签
<!--
	物理标签：b代表bold 加粗的意思 html语法
-->
<strong></strong> 强调某段文本，效果是加粗
<!--
	逻辑标记：强调的意思 xhtml语法
-->
<i></i> 定义斜体
<em></em> 强调某段文字 效果是斜体
<br/> 换行标签
<hr/> 水平线标签
<!-- 
	属性：align:水平对齐方式，默认是居中
	width：水平线的长度，百分比及像素都可以
	size:水平线的高度
	color:水平线的颜色
-->
<u></u> 下划线的标签
<del></del> 删除线的标签
<hn></hn>  <h1>~<h6> 定义标题标签，H1字体最大，H6字体最小
    <!--H族标签只有h1到h6标签-->
<bdo></bdo> 覆盖默认的文本方向。属性:dir=ltr/rtl ltr表示left to right从左到右 rtl表示right to left
<sub></sub> 定义下标文本
<sup></sup> 定义上标文本
```



#### 2.语义化标签

#### 3.列表标签

