---
layout: post
title: ReactNative
date: 2017-08-03
categories:
  - blog
description: 
image: http://pic.jj20.com/up/allimg/711/0H213105959/130H2105959-3.jpg
image-sm: http://images.china.cn/attachement/jpg/site1000/20140718/74de2b6d888a1532e0614d.jpg
---
##React Native


- React Native着力于提高多平台开发的开发效率 —— 仅需学习一次，编写任何平台。(Learn once, write anywhere)

- Facebook已经在多项产品中使用了React Native，并且将持续地投入建设React Native。

React Native 是Facebook的一个开源框架，React Native使你能够在Javascript和React的基础上获得完全一致的开发体验，构建世界一流的原生APP。官方的标语为“ Learn once, write anywhere”，仅需学习一次，编写任何平台。是目前App混合式开发的主要技术之一。

######原生组件
使用React Native，你可以使用标准的平台组件，例如iOS的UITabBar或安卓的Drawer。 这使你的app获得平台一致的视觉效果和体验，并且获得最佳的性能和流畅性。 使用对应的React component，就可以轻松地把这些原生组件整合到你的React Native应用中， 例如TabBarIOS和DrawerLayoutAndroid。

######异步执行
在Javascript代码和原生平台之间的所有操作都是异步执行的，并且原生模块还可以根据需要创建新的线程。这意味着你可以在主线程解码图片，然后在后台将它保存到磁盘，或者在不阻塞UI的情况下计算文字大小和界面布局等等。所以React Native开发的app天然具备流畅和反应灵敏的优势。Javascript和原生代码之间的通讯是完全可序列化的，这使得我们可以借助Chrome开发者工具去调试应用，而不论应用运行在模拟器还是真机上。

######触摸事件处理
React Native实现了一个强大的触摸事件处理系统，可以在复杂的View层次关系下正确地处理触摸事件。同时还提供了高度封装的组件如TouchableHighlight等，可以直接嵌入到ScrollView或者其它的元素中，无需额外配置。

######弹性盒(Flexbox)和样式
控制view的布局应当简单易行，这就是为什么React Native从web中借鉴了Flexbox模型。Flexbox让大多数常见的UI布局构建变得简单（譬如带有外衬margin和内衬padding，且堆叠在一起的多个矩形）。React Native还支持多种常见的web样式，例如fontWeight等。抽象样式表提供了一个高性能的机制来声明所有的样式和布局，并且可以直接应用到你的组件中。

######兼容通用标准
React Native致力于改进视图代码的编写方式。除此之外，我们还吸纳了web生态系统中的通用标准，并在必要的时候为这些API提供兼容层。如此一来，npm上的许多库就可以在React Native中直接使用。这样的兼容层有XMLHttpRequest, window.requestAnimationFrame, navigator.geolocation等。我们还在努力增加更多的API，并且十分欢迎开源社区进行贡献。

######扩展性
使用React Native，无需编写一行原生代码即可创造一款不错的app。尽管如此，使用自定义的原生视图和模块来扩展React Native也非常容易 —— 这意味着你现有的所有工作都可以被复用，你喜欢的各种原生库都可以被导入。

######入门
React Native看起来很像React，只不过其基础组件是原生组件而非web组件。要理解React Native应用的基本结构，首先需要了解一些基本的React的概念，比如JSX语法、组件、state状态以及props属性。
```
import React, { Component } from 'react';
import { AppRegistry, Text } from 'react-native';

class HelloWorldApp extends Component {
  render() {
    return (
      <Text>Hello world!</Text>
    );
  }
}

// 注意，这里用引号括起来的'HelloWorldApp'必须和你init创建的项目名一致
AppRegistry.registerComponent('HelloWorldApp', () => HelloWorldApp);
```
初看这段代码，可能觉得并不像JavaScript——没错，这是“未来”的JavaScript.

首先你需要了解ES2015 （也叫作ES6）——这是一套对JavaScript的语法改进的官方标准。但是这套标准目前还没有在所有的浏览器上完整实现，所以目前而言web开发中还很少使用。React Native内置了对ES2015标准的支持，你可以放心使用而无需担心兼容性问题。上面的示例代码中的import、from、class、extends、以及() =>箭头函数等新语法都是ES2015中的特性。

[学习地址](http://reactnative.cn/docs/0.42/getting-started.html)

##Weex

- 一次编写，多端运行。
Weex 提供强大的跨平台能力，可以使用相同的 API 开发 Web，Android 和 iOS 应用。 同时，我们对接口了丰富的扩展能力。 这样，当您需要扩展原生组件或模块时，这将非常方便。

与 Web App、HTML5 App 或 hybrid App 不同，您可以使用 Weex 构建一个真正的原生应用。更贴心的是你的代码只需使用 HTML、CSS、JavaScript 可以构建原生应用，上手非常简单。但实际上，应用的底层是 Objective-C 或 Java， 同时，Weex 提供很多 native 组件或模块供开发人员使用。

#####整体架构

Weex 表面上是一个客户端技术，但实际上它串联起了从本地开发环境到云端部署和分发的整个链路。开发者首先可以在本地像撰写 web 页面一样撰写一个 app 的页面，然后编译成一段 JavaScript 代码，形成 Weex 的一个 JS bundle；在云端，开发者可以把生成的 JS bundle 部署上去，然后通过网络请求或预下发的方式传递到用户的移动应用客户端；在移动应用客户端里，WeexSDK 会准备好一个 JavaScript 引擎，并且在用户打开一个 Weex 页面时执行相应的 JS bundle，并在执行过程中产生各种命令发送到 native 端进行的界面渲染或数据存储、网络通信、调用设备功能、用户交互响应等移动应用的场景实践；同时，如果用户没有安装移动应用，他仍然可以在浏览器里打开一个相同的 web 页面，这个页面是使用相同的页面源代码，通过浏览器里的 JavaScript 引擎运行起来的。

![952288D6-E103-4094-A12F-9B01FAA6610A.png](http://upload-images.jianshu.io/upload_images/1840079-8d1651cdeab7f44e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


#####云端部署和分发
Weex 的 JS bundle 可以作为 web 开发中的一段静态资源进行部署和下发。几乎可以复用 HTML5 所有的工程体系和最佳实践。比如在本地开发环境通过部署工具将 JS bundle 部署到 CDN、通过 CMS 或搭建平台把业务数据和模块化的前端组件自动化拼接生成 JS bundle、通过服务端 JS bundle 的流量和日志统计页面的访问情况、通过 AppCache 或类似的方式对 JS bundle 在客户端进行缓存或预加载以降低网络通信的成本等。

#####客户端 JavaScript 引擎
Weex 的 iOS 和 Android 客户端中都会运行一个 JavaScript 引擎，来执行 JS bundle，同时向各端的渲染层发送规范化的指令，调度客户端的渲染和其它各种能力。我们在 iOS 下选择了 JavaScriptCore 内核，而在 Android 下选择了 UC 提供的 v8 内核。无论是从性能还是稳定性方面都提供了强有力的保障。

为了让整个移动应用的资源利用得更好，我们在客户端提供的 JavaScript 引擎是单例的，即所有 JS bundle 公用一个 JavaScript 内核实例，同时对每个 JS bundle 在运行时进行了上下文的隔离，使得每个 JS bundle 都能够高效安全的工作。我们还把 Vue 2.0 这样的 JS Framework 做了预置，开发者不必把 JS Framework 打包在每个 JS bundle 里，从而大大减少了 JS bundle 的体积，也就进一步保障了页面打开的速度。

#####客户端渲染层
Weex 目前提供了 iOS 和 Android 两个客户端的 native 渲染层。每个端都基于 DOM 模型设计并实现了标准的界面渲染接口供 JavaScript 引擎调用。并且结合 web 标准和 native 的特点和优势实现了一套统一的组件和模块。Weex 在性能方面的表现也是非常优异的，尤其是界面首屏加载时间、native 下长列表的资源开销和复用情况、CPU、内存、帧率 等关键指标。当然，尽管 Weex 官方已经提供了一组开发者最常用的组件和模块，但面对丰富多样的移动应用研发需求，团队也难免会力不从心，为此我们提供了灵活自由的横向扩展能力，开发者可以根据自身的情况定制属于自己的客户端组件和模块，进一步丰富 Weex 在客户端上的能力。

#####浏览器渲染
Weex 除了提供 iOS 和 Android 的客户端渲染层之外，还基于 Vue 2.0 对官方的所有组件和模块进行了封装，开发者可以基于 Vue 2.0 用同一套源代码构建出在浏览器中相同效果的页面。并且同样可以横向扩展。

#####扩展

[Weex 和 Web 平台的差异](https://weex.incubator.apache.org/cn/references/platform-difference.html)
[如何使用 iOS](https://weex.incubator.apache.org/cn/references/ios-apis.html)
[如何使用 Android](https://weex.incubator.apache.org/cn/references/android-apis.html)
[如何使用 HTML5](https://weex.incubator.apache.org/cn/references/html5-apis.html)

[学习地址](https://weex.incubator.apache.org/cn/)

## React Native  对比 Weex 


对比 | React Native | Weex
---|---|---
社区支持| React Native社区则比较活跃，可以参考的项目和资料也比较丰富 | Weex开源较晚，互联网上相关资料还比较少，社区规模较小
App数量| [33 (不知名应用居多)](http://reactnative.cn/cases.html) | [8（阿里系应用淘宝、天猫等）](https://weex.incubator.apache.org/cn/)
开发环境| brew install node | brew install node
初始化工具| npm install -g yarn react-native-cli | npm install -g weex-toolkit@beta
环境| brew install node | brew install node
组件| 34组件相对较多 |16 更轻量级
学习成本| javascript,React.js,ES6，ReactNative  | javascript,Vue.js,ES6，Weex
debug工具| [Nuclide](https://nuclide.io) | [Devtools](https://weex.incubator.apache.org/cn/guide/intro/devtools.html) 实现了Chrome Debugging Protocol
Hello World| 必须安装环境 | 无需安装环境 支持线上预览[dotwe](http://dotwe.org/vue)、App效果预览
平台| Android、iOS | [Android、iOS、H5](https://weex.incubator.apache.org/cn/guide/intro/write-once.html)



下面附上一张性能对比图

![r&w.png](http://upload-images.jianshu.io/upload_images/1840079-0720d2dbbcfc1c1c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

