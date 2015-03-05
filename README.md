UMeng-Feedback-iOS
==================
这是一个[友盟用户反馈](http://www.umeng.com/component_feedback)组件SDK的非官方镜像。

官方集成指南请参照[http://dev.umeng.com/feedback/ios/integration](http://dev.umeng.com/feedback/ios/integration)。

## 使用CocoaPods安装
[CocoaPods](http://cocoapods.org) 是开发 OS X 和 iOS 应用程序的一个第三方库的依赖管理工具。利用 CocoaPods，可以自动化安装第三方库。

要使用友盟用户反馈组件SDK，推荐这样配置Podfile:

```ruby
# The front repo is prior if conflicted
# CocoaPods private repo
source 'https://github.com/jcccn/PodSpecs.git'
# CocoaPods master repo
source 'https://github.com/CocoaPods/Specs.git'

platform :ios,'7.0'

# ignore all warnings from all pods
inhibit_all_warnings!

pod 'UMFeedback'

```

也可以这样配置Podfile:

```ruby
# CocoaPods master repo
source 'https://github.com/CocoaPods/Specs.git'

platform :ios,'7.0'

# ignore all warnings from all pods
inhibit_all_warnings!

pod 'UMFeedback', :git => 'https://github.com/jcccn/UMeng-Feedback-iOS.git'

```

## 使用说明
在AppDelegate.m文件的 `- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions`方法中添加如下代码完成SDK的初始化：

```objective-c
[UMFeedback setAppKey:UmengAppKey];
```

在需要显示反馈界面的事件中调用如下代码来呼出反馈界面：

- 以导航窗口显示（前提是当前ViewController是导航窗口）：

```objective-c
[self.navigationController pushViewController:[UMFeedback feedbackViewController] animated:YES];
```

- 以模态窗口显示：

```objective-c
[self presentModalViewController:[UMFeedback feedbackModalViewController] animated:YES];
```


详细的功能使用，请参考[官方文档](http://dev.umeng.com/feedback/ios/integration)。
