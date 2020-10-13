title: React Native
speaker: Salman Lee
plugins:
    - echarts
prismTheme: tomorrow

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# React Native {.text-landing.text-shadow}

By Salman Lee {.text-intro}

- [RN 官方网站](https://reactnative.dev/)

- [RN 中文网](https://www.reactnative.cn/)

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# 概览 {.text-landing.text-shadow}

- **简介**
- **安装**
- **常用组件**
- **样式**
- **实现原理**
- **调试**
- **路由**
- **自定义原生组件**

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# 简介 {.text-landing.text-shadow}

 用React一套代码开发Android/IOS App

```
//代码长这样

import React, { Component } from 'react';
import { Text, View , Image } from 'react-native';

class WhyReactNativeIsSoGreat extends Component {
  render() {
    return (
      <View>
       <Image
          source={{uri: 'https://i.chzbgr.com/full/7345954048/h7E2C65F9/'}}
          style={{width: 320, height:180}}
        />
        <Text>
          基本上就是用原生组件比如'View'和'Text'
          来代替web组件'div'和'span'。
        </Text>
      </View>
    );
  }
}
```

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# 安装 {.text-landing.text-shadow}

## 简易沙盒环境

中文网译注：沙盒环境大量依赖于国外网络环境，也不能直接安装第三方原生组件。不建议国内用户使用。
自己注：所谓沙盒环境是指使用 [expo](https://expo.io/learn) 脚手架搭建项目，expo搭建项目时候可分两种workflow(Managed workflow / Bare workflow),
前者完全沙盒，不能安装三方原生组件只能用expo提供的，但是可以托管给expo服务器打包应用，热更新等；后者可以使用三方原生组件，但是不能托管打包，热更新等。
所以Managed workflow 才是那种不支持安装第三方原生组件的情况。

`npm install -g expo-cli`

`expo init AwesomeProject`


简要介绍下 [expo](https://expo.io/learn) ：（仅仅基于Managed workflow，因为Bare workflow没有做过不敢瞎说）

- 优点：让前端人员完全不接触原生代码甚至是xcode对项目的配置，提供了一些基本的原生组件可以直接使用，如：相机，app根目录访问等；还能托管打包应用，热更新等。
- 缺点：社区上的三方原生组件不能用，自己写的更别提了，能用expo提供的，也还够用，但是经常有各种bug，你只能放置它等待官方大神解决；不能触碰原生代码或配置文件这点其实很难受，有很多东西做不到，比如：应用名的国际化。

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# 安装 {.text-landing.text-shadow}

## 完整原生环境

### Mac 环境下 Android 与 IOS 共同需要

Node、Watchman

推荐使用 [homebrew](https://brew.sh/) 安装

```
brew install node
brew install watchman
```

Node版本要>=12

[Watchman](https://facebook.github.io/watchman/):则是由 Facebook 提供的监视文件系统变更的工具

### Mac + IOS

Xcode 和 CocoaPods

Xcode:mac app store 下载

[CocoaPods](https://cocoapods.org/):是用 Ruby 编写的包管理器。从 0.60 版本开始 react native 的 iOS 版本需要使用 CocoaPods 来管理依赖。

`sudo gem install cocoapods`
or
`brew install cocoapods`

### Mac + Android

JDK 和 Android Studio

[JDK](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html):官网下载或者homebrew搜索，要求jdk8也就是jdk1.8

[Android Studio](https://developer.android.com/studio/index.html):官网下载或者homebrew搜索,安装有些繁琐直接上链接 [安装](https://reactnative.cn/docs/getting-started#1-%E5%AE%89%E8%A3%85-android-studio)

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# 常用组件

- [View](https://reactnative.cn/docs/view):视图组件

- [Text](https://www.reactnative.cn/docs/text):文本组件

- [Image](https://www.reactnative.cn/docs/image):图片组件

- [TextInput](https://www.reactnative.cn/docs/textinput):文本输入组件

- [ScrollView](https://www.reactnative.cn/docs/scrollview):滚动视图组件

- [Button](https://www.reactnative.cn/docs/button):按钮组件

- [FlatList](https://www.reactnative.cn/docs/flatlist):列表组件

```
import React, { Component } from "react";
import { View, Text } from "react-native";

class App extends Component {
  render() {
    return (
      <View
        style={{
          flexDirection: "row",
          height: 100,
          padding: 20
        }}
      >
        <View style={{ backgroundColor: "blue", flex: 0.3 }} />
        <View style={{ backgroundColor: "red", flex: 0.5 }} />
        <Text>Hello World!</Text>
      </View>
    );
  }
}

export default App;
```

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# 样式

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# 实现原理

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# 调试

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# 路由

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# 自定义原生组件

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">
