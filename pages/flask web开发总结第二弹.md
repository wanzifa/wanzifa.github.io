title: "flask web开发总结第二弹"
date: 2015-11-30 13:54:43


Flask web 开发学习总结第二弹


---
　　终于把第二遍读下来了，感觉流畅了很多，许多之前不确定的都变成了确定的东西。
　　之前房祖名分享了一篇context机制的文章，虽然有些现在还不太能理解，但是还是很有帮助的，印象深刻的一段：
　　从一个 Flask App 读入配置并启动开始，就进入了 App Context，在其中我们可以访问配置文件、打开资源文件、通过路由规则反向构造 URL。当一个请求进入开始被处理时，就进入了 Request Context，在其中我们可以访问请求携带的信息，比如 HTTP Method、表单域等。
　　这一段解决了我对请求上下文和应用上下文建立时间的问题。
　　对于蓝本的理解，我觉得蓝本主要的目的就是模块化，使程序更有条理、更好管理。想了又想，还是觉得书上从app.route修饰器的使用顺序角度来解释蓝本的存在意义没有很强的说服力，有点避重就轻。
　　current_user全局变量是被Flask-Login设定的，是User类的一个实例，可以从request中得到。
　　记录最近见到的几个重要函数：
　　



 -

 functools.partial 通过包装手法，允许我们 "重新定义" 函数签名

用一些默认参数包装一个可调用对象,返回结果是可调用对象，并且可以像原始对象一样对待

 - staticmethod可以在类里面定义函数的时候，避免传入self实例，定义一个看起来相对独立的函数。
 - property一方面可以把方法变成属性，一方面可以利用setter和getter来限制值的获取，所以一般property装饰器后面会跟另外的两个函数（不过也有不跟的情况）
 -   利用classmethod装饰器可以写一个在类中运行而不在实例中运行的方法。
 （今天就先写到这里，下次如果有新发现的函数，再补充。functools是一个很好的模块。）
