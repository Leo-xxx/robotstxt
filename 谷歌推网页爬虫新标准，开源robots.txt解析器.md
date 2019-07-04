## 谷歌推网页爬虫新标准，开源robots.txt解析器

[量子位](javascript:void(0);) *昨天*

##### 鱼羊 发自 凹非寺  量子位 报道 | 公众号 QbitAI

对于接触过网络爬虫的人来说 robots.txt 绝不陌生，这一存放于网站根目录下的 ASCII 码文件标明了网站中哪些内容是可以抓取的，哪些内容又是禁止抓取的。

今年，robots.txt 就满 25 周岁了， 为了给这位互联网MVP庆祝生日，谷歌再度出手，开源 robots.txt 解析器，试图推助机器人排除协议（REP）正式成为互联网行业标准。

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtAOX9BxnpfSNUIOjP7PicSaTqKnIbgU0CYIb4C42IhoD3iaVJMpoN8icWlCDPQIDsUR7tEicq3VtSnlcA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



## 非标准的标准

机器人排除协议（Robots Exclusion Protocol）是荷兰软件工程师 Martijn Koster 在1994 提出的一项标准，其核心就是通过 robots.txt 这样一个简单的文本文件来控制爬虫机器人的行为。

REP 以其简单高效征服了互联网行业，有超过 5 亿个网站都在使用 robots.txt，可以说它已经成为了限制爬虫的事实标准，像 Googlebot 在抓取网页时就会浏览 robots.txt 来确保其不冒犯网站的特别声明。

然而，在为互联网行业服务了25年之后，REP 仍然只是一个非官方的标准。

这可带来了不少麻烦。

比如拼写错误。有很多人会忽视 robots.txt 规则中的冒号，而把 Disallow 拼成 Dis Allow 这种让爬虫抓瞎的情况也不是没有出现过。

此外，REP本身并没有涵盖所有的情况，比如出现服务器错误 500 时，爬虫是啥都可以抓还是啥也不能抓？

对于网站所有者来说，模糊的事实标准使得正确地书写规则变成了一件难事。这就够让人头疼的了，更别提并非所有的爬虫都尊重 robots.txt 这件事了。

## 来自谷歌的生日礼

REP 的尴尬，以搜索起家的谷歌看在眼里。于是在 REP 诞生25周年之际，谷歌大笔一挥，献上一份厚礼，宣布将与 REP 原作者 Martijn Koster、网站管理员和其他搜索引擎合作，向互联网工程任务组（IETF）提交规范化使用 REP 的草案，努力助其成为真正的官方标准！

为此，谷歌还开源了其用于抓取网络的工具之一—— **robots.txt 解析器**，来帮助开发人员构建自己的解析器，以期创建更多的通用格式，促进标准的完善。

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtAOX9BxnpfSNUIOjP7PicSaTibMTTAjuD9Lic3zTMyJAWEtx7LgQLl7Y2OFBCQRDmT5DGpzJRyJ8xiaXg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

此番开源的 C++ 库已存在20年之久，涵盖了谷歌生产历程中经历的许多有关 robots.txt 文件的案例。开源软件包中还包含了一个测试工具，可以帮助开发者们测试一些规则。

谷歌表示，他们希望帮助网站所有者和开发者们在互联网中创造出更多惊人的体验，而不是成天担心怎么去限制爬虫。

草案内容目前尚未全面公布，但大致会聚焦于以下几个方向：

- 任何基于 URI 的传输协议都可以使用 robots.txt。不局限于 HTTP，还包括 FTP 和 CoAP。
- 开发人员必须至少解析 robots.txt 的前 500 KiB。定义最大文件大小来确保打开文件不会花太长时间，以减轻服务器的压力。
- 新的最大缓存时间或缓存指令值为24小时，使网站所有者可以随时灵活地更新 robots.txt，并且爬虫不会使用 robots.txt 请求超载网站。
- 当先前可访问的 robots.txt 文件由于服务器故障而变得不可访问时，在长时间内不会对已知的不允许页面进行抓取。

## 网友评论

谷歌此番开源再次引起热议。

有网友表示，谷歌作为搜索行业的领军人物，大多数的搜索引擎都愿意紧随其后，他们愿做先锋统一行业标准是一件很有意义的事情。

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtAOX9BxnpfSNUIOjP7PicSaTOfb0Wx8auGhcsztM6WHAiclRHfL68hxib8DdmTGhNQHryTrFnfuLTmBg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

还有网友对谷歌愿意开源 robots.txt 解析器感到既兴奋又惊奇，谷歌将来还会开源与搜索相关的其他模块吗？想想都有点刺激呀。

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtAOX9BxnpfSNUIOjP7PicSaT1icpDhkxfUjnDsgamj5IHz6OktQT0IgDMzOG1r0HblQu6eSQLVyyFUg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

而 Martijn Koster 本人也说出了一些网友的心声：谷歌真是棒呆了！

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtAOX9BxnpfSNUIOjP7PicSaT39iaVibiawTaIqgn2TAicQoo0Vo4oIicgWk8J28NMoxiav2x2ibiaWkJMvEy6A/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

## 传送门

开源地址：https://github.com/google/robotstxt

— **完** —

**AI社群 | 与优秀的人交流**

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtCEFSVW5ubo08Zfv1qB5iaprbZUlsy5odkbQRwlnJ4gYccCB4iaR89q8zdvoc9CEDlR3ORTzdicyLI5g/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**小程序 | 全类别AI学习教程**

[![img](https://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtDpADEKp9rvicB48XgA8ueVdwNbXM1wibYx0ic2pYicwu3UCU5BM6fpDvbH8c4e9JV3uGvYaWAhvGiaTVQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)](https://mp.weixin.qq.com/s?__biz=MzIzNjc1NzUzMw==&mid=2247524518&idx=4&sn=beca010a44c2b1892332c85783207213&chksm=e8d0d7d4dfa75ec2cd51132f0502966b8785c6afa9978103791618c8c409fc01dcd804e51fa4&mpshare=1&scene=1&srcid=0704QKLNFwSTzEDNKfJ9wkGJ&key=55f99d04c6be589c7d97ba9ab7376cf35f2bae911b85a8a9bc40f9a31a32bdce19b78003bdedcef02d2eca8e4e4d037461ca8647c7ff51e5930114c1b3958527013f66c1e8f8b4e29443a238671ca042&ascene=1&uin=MjMzNDA2ODYyNQ%3D%3D&devicetype=Windows+10&version=62060833&lang=zh_CN&pass_ticket=tFNqUL0VfHxxY99IyVywfi5SR9hyyWsrjaXd5I2BiPMy%2BpgePcB11%2FXQntJivQur)

![img](https://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtA4cHOuHJibUghtT1ypRqwhcUTT9qxG7pXQasesKT5uUINHKEp2K2VYJS7dJrVxQicTqDkAYEoiahuSQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



**量子位** QbitAI · 头条号签约作者





վ'ᴗ' ի 追踪AI技术和产品新动态



喜欢就点「在看」吧 ! 











![img](https://mp.weixin.qq.com/mp/qrcode?scene=10000004&size=102&__biz=MzIzNjc1NzUzMw==&mid=2247524518&idx=4&sn=beca010a44c2b1892332c85783207213&send_time=)

微信扫一扫
关注该公众号