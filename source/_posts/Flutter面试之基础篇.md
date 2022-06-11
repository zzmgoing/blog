---
title: Flutter面试之基础篇
abbrlink: e8e5428c
date: 2022-06-03 20:43:33
tags: flutter
categories: Flutter
---

{% timeline Flutter版本更新记录,blue %}
<!-- timeline 2020-05-13 -->
[Flutter3 更新详解(支持macOS、Linux、曲面屏、游戏开发支持等)](https://flutter.cn/posts/whats-new-in-flutter-3)
<!-- endtimeline -->
{% endtimeline %}

# Flutter简介
[初识Flutter(Flutter框架结构)](https://book.flutterchina.club/chapter1/flutter_intro.html#_1-2-1-flutter-%E7%AE%80%E4%BB%8B)

# LocalKey、GlobalKey的作用和区别
GlobalKey可以主动获取以及主动改变子控件的状态。

# Widget、Element、RenderObject三者之间的关系
Widget不是真正渲染UI的对象，它只是Element的一个配置描述，去告知Element应该如何去渲染，Widget和Element之间是一对多的关系。RenderObject才是实际渲染的对象，Element持有RenderObject和Widget。
大致总结三者的关系是：配置文件Widget生成了Element，而后创建RenderObject关联到Element的内部renderObject对象上，最后Flutter通过RenderObject数据来布局和绘制。

# Flutter和原生的通信方式
1.BasicMessageChannel: 支持数据双向传递，有返回值，可用于传递字符串和半结构化的信息。
2.MethodChannel: 支持数据双向传递，有返回值，用于传递方法调用（method invocation）。
3.EventChannel: 仅支持数据单向传递，无返回值，用于数据流（event streams）的通信。

# StatefulWidget的生命周期


# StatelessWidget和StatefulWidget的区别
StatelessWidget: 不会发生状态改变的Widget，一旦创建就不关心任何变化，在下次构建之前都不会改变。它们除了依赖于自身的配置信息（在父节点构建时提供）外不再依赖于任何其他信息。
StatefulWidget: 在生命周期内，该类 Widget 所持有的数据可能会发生变化，这样的数据被称为 State，这些拥有动态内部数据的 Widget 被称为 StatefulWidget。
StatefulWidget 由两部分组成，在初始化时必须要在 createState()时初始化一个与之相关的 State 对象。

# setState刷新原理
调用一个Widget的setState()方法，它会将当前Widget及其所有子Widget都标记为重新刷新的状态，等待下一个Vsync刷新信号到来时重新刷新所有这些标记为刷新状态的控件，也就是调用他们的build方法。
局部刷新的话可以给子部件Widget添加一个GlobalKey，完成跟Element的绑定，拿到子部件Widget的State来进行刷新。

# Future中遍历数据量大的集合会造成卡顿吗


<br>

{% note 'fab fa-internet-explorer' %}
[Flutter的两种编译模式](https://blog.csdn.net/u010960265/article/details/81361711)
[Flutter实现动态化更新-技术预研](https://zhuanlan.zhihu.com/p/439251771)
[Flutter面试题-基础篇](https://www.jianshu.com/p/5fe4007a6070)
[https://www.jianshu.com/p/657732a2f333](https://www.jianshu.com/p/657732a2f333)
{% endnote %}