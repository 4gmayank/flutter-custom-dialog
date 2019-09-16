# ✨ flutter_custom_dialog

[![pub package](https://img.shields.io/pub/v/flutter_custom_dialog.svg)](https://pub.dev/packages/flutter_custom_dialog)

对全局弹窗的功能封装，用语义化的方式对弹窗内部的内容进行填充，目前提供的功能

1. 提供的语义化方法，填充弹窗内部的组件内容
2. 提供的设置弹窗背景色、前景色、位置、动画、点击外部消失等功能，具体看example

## 🎖 Installing

```yaml
dependencies:
  flutter_custom_dialog: ^1.0.0
```

## ⚡ Use Custom Dialog

**1、import**

```dart
import 'package:flutter_custom_dialog/flutter_custom_dialog.dart';
```

**2、road map**

> dialog demo

<table>
  <tr>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/png/1.png" width="150px">
      <br />
      divider
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/png/2.png" width="150px">
      <br />
      body
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/png/3.png" width="150px">
      <br />
      head&body
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/png/4.png" width="150px">
      <br />
      listTile
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/png/5.png" width="150px">
      <br />
      ListRadio
      <br />
      ✅
    </td>
  </tr>
</table>

> dialog gravity

<table>
  <tr>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/gif/1.gif" width="150px">
      <br />
      bottom
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/gif/2.gif" width="150px">
      <br />
      top
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/gif/3.gif" width="150px">
      <br />
      left
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/gif/4.gif" width="150px">
      <br />
      right
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/gif/5.gif" width="150px">
      <br />
      center
      <br />
      ✅
    </td>
  </tr>
</table>

> dialog animation

<table>
  <tr>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/gif/6.gif" width="150px">
      <br />
      scaleIn
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/gif/7.gif" width="150px">
      <br />
      fadeIn
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/gif/8.gif" width="150px">
      <br />
      rotateIn
      <br />
      ✅
    </td>
    <td align="center">
      <img src="https://github.com/YYFlutter/flutter-custom-dialog/raw/master/image/gif/9.gif" width="150px">
      <br />
      customIn
      <br />
      ✅
    </td>
  </tr>
</table>

**3、use**

> 功能属性的设置

属性的设置通过成员变量的方法去调用，具体详见下表

```dart
YYDialog YYAlertDialogWithDivider(BuildContext context) {
  return YYDialog().build(context)
    ..width = 220
    ..borderRadius = 4.0
    ..show();
}
```

支持的功能属性

property|description|default
--|--|--|
width|弹窗宽度|0
height|弹窗高度|自适应组件高度
duration|弹窗动画出现的时间|250毫秒
gravity|弹窗出现的位置|居中
barrierColor|弹窗外的背景色|30%黑色
backgroundColor|弹窗内的背景色|白色
borderRadius|弹窗圆角|0.0
constraints|弹窗约束|最小宽高不低于10%
animatedFunc|弹窗出现的动画|从中间出现
barrierDismissible|是否点击弹出外部消失|true

> 语义化组件

弹窗内部的组件内容提前通过语义化的函数封装好常用的组件，以便快速构建出弹窗，具体见下表

```dart
YYDialog YYAlertDialogWithDivider(BuildContext context) {
  return YYDialog().build(context)
    ..width = 220
    ..borderRadius = 4.0
    ..text(
      padding: EdgeInsets.all(25.0),
      alignment: Alignment.center,
      text: "确定要退出登录吗?",
      color: Colors.black,
      fontSize: 14.0,
      fontWeight: FontWeight.w500,
    )
    ..divider()
    ..doubleButton(
      padding: EdgeInsets.only(top: 10.0),
      gravity: Gravity.center,
      withDivider: true,
      text1: "取消",
      color1: Colors.redAccent,
      fontSize1: 14.0,
      fontWeight1: FontWeight.bold,
      onTap1: () {
        print("取消");
      },
      text2: "确定",
      color2: Colors.redAccent,
      fontSize2: 14.0,
      fontWeight2: FontWeight.bold,
      onTap2: () {
        print("确定");
      },
    )
    ..show();
}
```

支持的语义化组件

method|description
--|--|
text|文本控件
doubleButton|双按钮控件
listViewOfListTile|列表Tile组件
listViewOfRadioButton|列表按钮组件
divider|分割线组件
height|弹窗高度
widget|自定义语义化组件

由于组件提供只是辅助快速搭建UI，在实际项目开发中远远不能满足需求，所以提供了自定义语义化组件的插入

> 例如：text语义化组件

```dart
YYDialog text({padding, text, color, fontSize, alignment, fontWeight}) {
  return this.widget(
    Padding(
      padding: padding ?? EdgeInsets.all(0.0),
      child: Align(
        alignment: alignment ?? Alignment.centerLeft,
        child: Text(
          text ?? "",
          style: TextStyle(
            color: color ?? Colors.black,
            fontSize: fontSize ?? 14.0,
            fontWeight: fontWeight,
          ),
        ),
      ),
    ),
  );
}
```

## Bugs/Requests

* If your application has problems, please submit your code and effect to Issue.
* Pull request are also welcome.

## About

* QQ：510402535
* QQ群：798874340
* e-mail：xyj510402535@qq.com
* g-mail：xyj51042535@gmail.com
* Blog：http://blog.csdn.net/qq_30379689
* Github：https://github.com/AndroidHensen

## License

Apache License 2.0
