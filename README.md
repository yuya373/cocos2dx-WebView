# DEPRECATED
This WebView merged into cocos2d-x3.3!

# Require
* cocos2d-x ver3.0(or greater
* android-10(or greater

# How to setup
## iOS
* Add `cocos2dx-WebView/common` and `cocos2dx-WebView/ios` to your project.

## Android
```sh
cd /path/to/cocos2dx-WebView/android/java
android update project -p . -t [android API level]
android update project -p . -l /path/to/cocos2d/cocos/platform/android/java
cd /path/to/proj.android
android update project -p . -l /path/to/cocos2dx-WebView/android/java
open /path/to/proj.android/jni/Android.mk
```

```diff
+LOCAL_WHOLE_STATIC_LIBRARIES += cocos_webview_plugin_static
+$(call import-module,../libs/cocos2dx-WebView/android)
```

# How to use.
```cpp
auto webView = cocos2d::plugin::WebView::create();
webView->setContentSize(cocos2d::Director::getInstance()->getVisibleSize());
webView->setPosition(cocos2d::Director::getInstance()->getVisibleSize() / 2);
webView->loadUrl("http://www.google.co.jp");
this->addChild(webView);

// if set js scheme. call `onJsCallback` when load `hoge-scheme://foo`.
webView->setJavascriptInterfaceScheme("hoge-scheme");
```
