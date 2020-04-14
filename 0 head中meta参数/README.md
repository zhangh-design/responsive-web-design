## head中meta参数

先上一个 慕课网 的meta配置代码片段：

```
<meta charset="utf-8">
<title>慕课网-程序员的梦工厂</title>
<meta http-equiv="X-UA-Compatible" content="IE=edge, chrome=1">
<meta name="renderer" content="webkit" />
<meta name="mobile-agent" content="format=wml"; url="https://m.imooc.com/">
<link rel="alternate" media="only screen and (max-width: 640px)" href="https://m.imooc.com/">
<meta name="mobile-agent" content="format=xhtml"; url="https://m.imooc.com/">
<meta name="mobile-agent" content="format=html5"; url="https://m.imooc.com/">
<meta property="qc:admins" content="77103107776157736375" />
<meta property="wb:webmaster" content="c4f857219bfae3cb" />
<meta http-equiv="Access-Control-Allow-Origin" content="*" />
<meta http-equiv="Cache-Control" content="no-transform " />
<meta http-equiv="Cache-Control" content="no-siteapp" />
<link rel="dns-prefetch" href="//www.imooc.com" />
<link rel="dns-prefetch" href="//img.imooc.com" />
<link rel="dns-prefetch" href="//img.mukewang.com" />
<link rel="apple-touch-icon" sizes="76x76" href="/static/img/common/touch-icon-ipad.png">
<link rel="apple-touch-icon" sizes="120x120" href="/static/img/common/touch-icon-iphone-retina.png">
<link rel="apple-touch-icon" sizes="152x152" href="/static/img/common/touch-icon-ipad-retina.png">
<meta name="Keywords" content="" />
<meta name="Description" content="慕课网（IMOOC）是IT技能学习平台。慕课网(IMOOC)提供了丰富的移动端开发、php开发、web前端、android开发以及html5等视频教程资源公开课。并且富有交互性及趣味性，你还可以和朋友一起编程。" />
<meta name="360-site-verification" content="efec9ca9c0c2bf49b8f54f8ea4626ea8" />
<meta name="baidu-site-verification" content="f81e4a13096b3a7cab15fe1d39773a4e"/>
```

#### 我们来逐一分析下里面的 meta 标签的作用

规定 HTML 文档的字符编码

```
<meta charset="utf-8">
```

`IE=edge`告诉IE使用最新的引擎渲染网页（[这句代码可以改变360兼容模式下以何种版本的IE去渲染页面](https://www.cnblogs.com/nxl0908/p/7245837.html)）

chrome=1则可以激活Chrome Frame，这样写可以达到的效果是如果安装了GCF，则使用GCF来渲染页面，如果未安装GCF，则使用最高版本的IE内核进行渲染。（[谷歌内嵌浏览器框架GCF，这个插件可以让用户的IE浏览器外观不变，但用户在浏览网页时，实际上使用的是Google Chrome浏览器内核，而且支持IE6、7、8等多个版本的IE浏览器，谷歌这个墙角挖的真给力！](https://blog.csdn.net/ccfxue/article/details/70739646)）

```
<meta http-equiv="X-UA-Compatible" content="IE=edge, chrome=1">
```

[强制浏览器启用Chromium内核，为用户提供最好的使用体验。](https://blog.csdn.net/AiHuanhuan110/article/details/89090019)

通常和上一个属性一起结合使用，也就是最好两个都配置防止出现某一个不起作用。

```
<meta name="renderer" content="webkit"/>
```

[移动适配之网页Meta标注声明](https://www.yudouyudou.com/jiaochengheji/wangzhanjianshe/85.html)

[wml|xhtml|html5]——根据手机页的协议语言，选择其中的一种。

url=url——后者代表当前PC页所对应的手机页url

`https://m.imooc.com/`我们首先确定这是一个手机端的`url`地址不是pc网页端的`url`地址（pc端时`https://www.imooc.com/`）。

生效情况：标注Meta声明这一适配方案仅在百度移动搜索中生效，即只有当用户通过百度移动搜索访问站点时，适配才会生效;通过其他渠道则不生效

```
<meta name="mobile-agent" content="format=wml"; url="https://m.imooc.com/">
<meta name="mobile-agent" content="format=xhtml"; url="https://m.imooc.com/">
<meta name="mobile-agent" content="format=html5"; url="https://m.imooc.com/">
```

[移动站适配rel=alternate PC页和H5页适配标注](https://www.cnblogs.com/osfipin/p/5852037.html)

1.在pc版网页上，添加指向对应移动版网址的特殊链接rel="alternate"标记，这有助于百度发现网站的移动版网页所在的位置；

2.同时在移动版网页上，添加指向对应pc版网址的链接rel="canonical"标记。

```
<link rel="alternate" media="only screen and (max-width: 640px)" href="https://m.imooc.com/">
```

这个是让网站加入QQ登录接口，这段代码可放在<head></head>之间。
申请腾讯接口后，会得到这样的代码，加入接口之后，你的网站上面的注册登录功能，别人可以直接用QQ登录，省去注册的麻烦。

```
<meta property="qc:admins" content="77103107776157736375" />
```

微博登陆声明

```
<meta property="wb:webmaster" content="c4f857219bfae3cb" />
```



```
<meta http-equiv="Access-Control-Allow-Origin" content="*" />
```





