# handson_meteor_j-hack_20160130

## Summary
This repository has a product by hands-on [「［JavaScriptだけでできる！］ゆる〜くMeteorでiOSアプリをハンズオン！」](http://meteor-tokyo.connpass.com/event/25255/).
This product seem to be same as Meteor tutorial sample product, but this product has app icon, splash icon and app setting file.
It's mean that can be ready to release for App store.

## Resource
[Meteor iOSアプリ開発入門](https://www.gitbook.com/book/j-hack/meteor-ios-app-getting-started/details)

## That failed
### 1.Occur a error when build on real device

error log
```
While running Cordova app for platform iOS with options --emulator:
   Error: Command failed:
   /Users/hoge/meteor/meteor-ios-app-example/app/.meteor/local/cordova-build/platforms/ios/cordova/run
   --emulator
   2016-01-30 14:20:01.431 xcodebuild[91677:8473340] [MT] PluginLoading:
   Required plug-in compatibility UUID XXXXXXXXXXXXXXXXXXXXXXXXXXX for
   plug-in at path '~/Library/Application
   Support/Developer/Shared/Xcode/Plug-ins/RealmPlugin.xcplugin' not present in
   DVTPlugInCompatibilityUUIDs
   ** BUILD FAILED **
   The following build commands failed:
   Check dependencies
   (1 failure)
   Error code 65 for command: xcodebuild with args:
   -xcconfig,/Users/n/meteor/meteor-ios-app-example/app/.meteor/local/cordova-build/platforms/ios/cordova/build-debug.xcconfig,
   -project,Todo.xcodeproj,ARCHS=i386,-target,Todo,-configuration,Debug,-sdk,iphonesimulator,build,VALID_ARCHS=i386,
   CONFIGURATION_BUILD_DIR=/Users/hoge/meteor/meteor-ios-app-example/app/.meteor/local/cordova-build/platforms/ios/build/emulator,
   SHARED_PRECOMPS_DIR=/Users/hoge/meteor/meteor-ios-app-example/app/.meteor/local/cordova-build/platforms/ios/build/sharedpch
   at ChildProcess.exitCallback (/tools/utils/processes.js:137:23)
   at ChildProcess.emit (events.js:98:17)
   at Process.ChildProcess._handle.onexit (child_process.js:820:12)
ExitWithCode:1
```
#### the cause
Due to Remain cache for build setting.

#### How to resolve
Remove following directory and rebuild.
```
#$APPROOT/.meteor/local/cordova-build
rm -rf .meteor/local/cordova-build
```

### 2.occure error when make product Archive

error log
```
Code Sign error: No matching provisioning profiles found: No provisioning profiles with a valid signing identity 
(i.e. certificate and private key pair) matching the bundle identifier “xxxxxxxxxxxxxxxxxxx” were found.
```

#### The cause 
Due to not match bundle identifier and provisioning profile info.

#### How to resolve

match bundle identifier and provisioning profile.

for example…

![hoge](https://github.com/mktktmr/handson_meteor_j-hack_20160130/wiki/images/matching_identifier.jpg)







