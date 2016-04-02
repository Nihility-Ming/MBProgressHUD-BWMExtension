# MBProgressHUD+BWMExtension

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE.md) 
[![forks](https://img.shields.io/github/forks/Nihility-Ming/MBProgressHUD-BWMExtension.svg)](#)
[![stars](https://img.shields.io/github/stars/Nihility-Ming/MBProgressHUD-BWMExtension.svg)](#) [![CocoaPods](https://img.shields.io/badge/CocoaPods-Support-green.svg)](#usage)
[![Release](https://img.shields.io/badge/release-1.0.1-orange.svg)](#)

Nihility-Ming to MBProgressHUD extension, easy to use.

---

## MBProgressHUD+BWMExtension.h

```Objective-C
/**
 *  @brief  Nihility-Ming对MBProgressHUD的扩展，方便使用。
 */
@interface MBProgressHUD (BWMExtension)

extern NSString * const kBWMMBProgressHUDMsgLoading;
extern NSString * const kBWMMBProgressHUDMsgLoadError;
extern NSString * const kBWMMBProgressHUDMsgLoadSuccessful;
extern NSString * const kBWMMBProgressHUDMsgNoMoreData;
extern NSTimeInterval kBWMMBProgressHUDHideTimeInterval;

typedef NS_ENUM(NSUInteger, BWMMBProgressHUDMsgType) {
    BWMMBProgressHUDMsgTypeSuccessful,
    BWMMBProgressHUDMsgTypeError,
    BWMMBProgressHUDMsgTypeWarning,
    BWMMBProgressHUDMsgTypeInfo
};

/**
 *  @brief  添加一个带菊花的HUD
 *
 *  @param view  目标view
 *  @param title 标题
 *
 *  @return MBProgressHUD
 */
+ (MBProgressHUD *)bwm_showHUDAddedTo:(UIView *)view title:(NSString *)title;
/** 添加一个带菊花的HUD */
+ (MBProgressHUD *)bwm_showHUDAddedTo:(UIView *)view
                                title:(NSString *)title
                             animated:(BOOL)animated;

/**
 *  @brief  隐藏指定的HUD
 *
 *  @param afterSecond 多少秒后
 */
- (void)bwm_hideAfter:(NSTimeInterval)afterSecond;
/** 隐藏指定的HUD */
- (void)bwm_hideWithTitle:(NSString *)title
                hideAfter:(NSTimeInterval)afterSecond;
/** 隐藏指定的HUD */
- (void)bwm_hideWithTitle:(NSString *)title
                hideAfter:(NSTimeInterval)afterSecond
                  msgType:(BWMMBProgressHUDMsgType)msgType;

/**
 *  @brief  显示一个自定的HUD
 *
 *  @param title       标题
 *  @param view        目标view
 *  @param afterSecond 持续时间
 *
 *  @return MBProgressHUD
 */
+ (MBProgressHUD *)bwm_showTitle:(NSString *)title
                      toView:(UIView *)view
                   hideAfter:(NSTimeInterval)afterSecond;
/** 显示一个自定的HUD */
+ (MBProgressHUD *)bwm_showTitle:(NSString *)title
                      toView:(UIView *)view
                   hideAfter:(NSTimeInterval)afterSecond
                     msgType:(BWMMBProgressHUDMsgType)msgType;

/**
 *  @brief  显示一个渐进式的HUD
 *
 *  @param view 目标view
 *
 *  @return MBProgressHUD
 */
+ (MBProgressHUD *)bwm_showDeterminateHUDTo:(UIView *)view;

/** 配置本扩展的默认参数 */
+ (void)bwm_setHideTimeInterval:(NSTimeInterval)second fontSize:(CGFloat)fontSize opacity:(CGFloat)opacity;

@end

```

## Screenshots

<table align="center">
    <tr>
        <td><img src="ScreenShots/01.png" /></td>
        <td><img src="ScreenShots/02.png" /></td>
    </tr>
    <tr>
        <td><img src="ScreenShots/03.png" /></td>
        <td><img src="ScreenShots/04.png" /></td>
    </tr>
    <tr>
        <td><img src="ScreenShots/05.png" /></td>
        <td><img src="ScreenShots/06.png" /></td>
    </tr>
</table>

## CocoaPods

The recommended approach for installating `MBProgressHUD+BWMExtension` is via the [CocoaPods](http://cocoapods.org/) package manager, as it provides flexible dependency management and dead simple installation.
For best results, it is recommended that you install via CocoaPods >= **0.35.0** using Git >= **2.3.2** installed via Homebrew.

Install CocoaPods if not already available:

``` bash
$ [sudo] gem install cocoapods
$ pod setup
```

Change to the directory of your Xcode project:

``` bash
$ cd /path/to/MyProject
$ touch Podfile
$ edit Podfile
```

Edit your Podfile and add:

``` bash
platform :ios, '7.0'
pod 'MBProgressHUD+BWMExtension', '~> 1.0.0'
```

Install into your Xcode project:

``` bash
$ pod install
```

Open your project in Xcode from the .xcworkspace file (not the usual project file)

``` bash
$ open MyProject.xcworkspace
```

Please note that if your installation fails, it may be because you are installing with a version of Git lower than CocoaPods is expecting. Please ensure that you are running Git >= **2.3.2** by executing `git --version`. You can get a full picture of the installation details by executing `pod install --verbose`.

### Manual Install

All you need to do is drop `Example/MBProgressHUD+BWMExtension` files into your project, and add `#include "MBProgressHUD+BWMExtension.h"` to the top of classes that will use it.

### Versions

#### 1.0.1

Fixed bug of missing image files.

#### 1.0.0

Build.

## Usage

```Ruby
pod 'MBProgressHUD+BWMExtension'
```

or

All you need to do is drop `Example/MBProgressHUD+BWMExtension` files into your project, and add `#include "MBProgressHUD+BWMExtension.h"` to the top of classes that will use it.

## License

`MBProgressHUD+BWMExtension` is available under the MIT license. 
