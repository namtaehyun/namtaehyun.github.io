---
title: "[Flutter] 앱 종료하는 방법"
description: Flutter App 종료하는 방법
categories:
  - flutter
tags:
  - Flutter
---

## 방법

```dart
SystemChannels.platform.invokeMethod('SystemNavigator.pop');
```

## 참고

[https://stackoverflow.com/questions/45109557/flutter-how-to-programmatically-exit-the-app?answertab=votes#tab-top](https://stackoverflow.com/questions/45109557/flutter-how-to-programmatically-exit-the-app?answertab=votes#tab-top){: target="\_blank"}
