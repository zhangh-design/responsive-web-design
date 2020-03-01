## 01 媒体查询 1

我们来单独说一说媒体查询，媒体查询早在`CSS2`就有了，下面这两句话就是典型的媒体查询：

1. 

```
<link rel="stylesheet" type="text/css" href="site.css" media="screen" />
```

2. 

```
<link rel="stylesheet" type="text/css" href="print.css" media="print" />
```

那时候的媒体查询呢比较初级也比较简单，其实主要就是用来区分一下我们是`屏幕显示`或者是`打印`，其中的`media`这两句代码大家都非常的熟悉。

#### CSS3 媒体查询

在`CSS3`中媒体查询被进一步增强，它包含了很多：

- <font color=#A52A2A size=2>媒体类型</font>
- <font color=#A52A2A size=2>函数</font>

允许我们在样式表中更精确的匹配一些显示规则。

这样一句就是一句典型的媒体查询：

```
@media all and (min-width: 800px) and (orientation: landscape){
    ...
}
```

前面开头呢用 `@media` 代表这样一句话是媒体查询，`all`呢是媒体类型，这样一段括号内省略号省略一些样式，这样一段样式呢应用于所有的媒体类型，当然我们也可以使用：

- <font color=#A52A2A size=2>screen</font>
- <font color=#A52A2A size=2>print</font>

也就是屏幕和打印的媒体类型，媒体类型是可选的，也就是说这个`all`你也可以不写（如果不写的话默认就是 `all`就是全部）。

**注意：**

如果使用`not`或者`only`之类的操作符这个媒体类型就必须得写（`not`或者`only`这些操作符等会我们会讲到）。


#### 表达式 and 、or 、not 、only、,

接下来就是一堆表达式。

```
@media all and (min-width: 800px) and (orientation: landscape){
    ...
}
```

我们看`and`后面连接了一个括号内的表达式，然后在`and`呢在连接了一堆表达式，我们先不去管这个表达式里边的内容代表什么样的含义。

我们先看这个`and`，`and`大家都知道它是一个逻辑的操作符，在媒体查询中呢我们可以用：

- not
- and 
- only

之类的逻辑操作的一个查询符来去连接（这个`and`就起到连接的作用）。

其实媒体查询就是这样一段媒体表达式，它就是对这些操作符它所连接的这些表达式进行一个统一的计算，计算完呢返回一个`Boolean`布尔值也就是`真`或者`假`，如果这样一句话呢一整句媒体查询它代表着`真`我们接下来在省略号内的样式呢就会被应用，如果这样一句表达式代表的`假`我们省略号内的样式就不会被应用，所以这是一段逻辑操作的一个连接。

当然我们的`and`呢也可以不光是`and`、`not`、`only`，我们也可以用`,`逗号。

`,`逗号代表什么意思呢？

用`,`逗号分隔呢，其实效果等同于`or`：

```
@media not screen and (color), print and (color)
```

等同于


```
@media not screen and (color) or print and (color)
```

那`and`和`or`这两种大家都比较清楚了，是两种逻辑的操作符：

- and 与
- or 或

与和或都很好的理解，一个全部都要比配，一个是任意条件匹配一个就可以了。

#### not

那么`not`是什么意思呢？

`not`的话一般应用于整个的媒体查询，代表`非`。

也就是后面的这些媒体查询的一个否定，如果后面这些媒体查询它不成立那么加上
`not`否定就代表成立：

```
@media not all and (monochrome){
    ...
}
```

大家要注意`not`后面跟的这样一段是圆括号括起来的其中这样来写等价于在`not`后面的这一段话中加上了圆括号：

```
@media not (all and (monochrome)){
    ...
}
```

但是如果中间出现逗号`,`来分割的话，也就是刚才我们说的`，`逗号等价于`or`：


```
@media not screen and (color), print and (color)
```

等价于

```
@media not screen and (color) or print and (color)
```

等价于

```
@media (not (screen and (color))), print and (color)
```

**注意：**

那么 `not`后面这样一段话`(screen and (color))`就只管到逗号这样一个位置，也就是说你加了`not`它有效的范围只是到`,`逗号的位置，如果`,`逗号后面呢还想要使用`not`就接着增加`not`来写。

#### only

介绍完前面三个逻辑操作符（`not`、`and`、`or`），那最后一个`only`这个关键值会复杂一些。

`only`是什么意思呢？

那英文大家都知道`仅仅，只有`的意思，它主要是<font color="#dd0000">防止老旧的浏览器不支持带媒体属性的查询而应用到给定的样式</font>。

怎么来理解呢，我们来看这样两个例子：

```
media="only screen and (min-width:401px) and (max-width:600px)"
旧浏览器解析：media="only"


media="screen and (min-width:401px) and (max-width:600px)"
旧浏览器解析：media="screen"
```

第一个例子有`only`而这二个例子没有，其实它们的含义都是一样的，就是仅仅是在屏幕显示中然后呢包含这两个条件如果达到的话就应用这样一个样式，但是在比较老的浏览器中如果这个浏览器不支持媒体查询，它会在第一个空格处把后面的文字都给忽略掉，只会解释到第一个单词`only`，也就是在老浏览器中第一个例子会解释为`media="only"`，而下面这句话呢会解释成`media="screen"`，所以第一段样式老浏览器是不会应用的因为没有一个叫`only`的这样一个设备，所以老浏览器会忽略掉，而第二个例子呢如果如果被老浏览器解析成了`media="screen"`也就不管你后面的媒体查询怎么样来写对于老的浏览器来说都会应用这样一段样式，因为它已经把后面的逻辑表达式给忽略掉了它永远为真。

所以我们要注意：

一般来说当我们只对某个设备设置媒体查询的话最好要带上`only`，除非你确定你根本不需要兼容老的浏览器。

#### CSS3媒体属性简介

`CSS3`呢提供了很多的媒体属性，用来让我们精确的应用和匹配规则。

这里简单介绍一下主要的媒体属性：

- width：视口宽度
- height: 视口高度
- device-width: 渲染表面的宽度，就是设备屏幕的宽度。
- device-height: 渲染表面的高度，就是设备屏幕的高度。
- orientation: 检查设备处于横向还是纵向。
- aspect-ratio: 基于视口宽度和高度的宽高比（width/height 如：16/9、4/3）。
- device-aspect-ratio: 渲染表面的宽度，就是设备屏幕的宽度。
- color: 每种颜色的位数 bits 如：min-color: 16位，8位。
- resolution: 检测屏幕或者打印机的分辨率（如：min-resolution: 300dpi）。


当然呢还有很多其它的一些属性大家可以去查阅官方的文档，最主要呢我们最常用的就是下面这四个媒体属性：


- width：视口宽度
- height: 视口高度
- device-width: 渲染表面的宽度，就是设备屏幕的宽度。
- device-height: 渲染表面的高度，就是设备屏幕的高度。

（以上属性都可以添加 `min-` 或 `max-`前缀）

当然对于上面的属性我们可以添加前缀，而且经常性我们使用的都是添加前缀后的
这样一些媒体属性，比如我们可以添加`min-`最小或者`max-`最大这样一个前缀。
