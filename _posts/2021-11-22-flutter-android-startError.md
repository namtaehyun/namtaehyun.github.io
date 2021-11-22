---
title: "[Flutter] Android hat went wrong: A problem occurred evaluating project ':app'. > path may not be null or empty string. path='null'"
description: Flutter Android hat went wrong A problem occurred evaluating project ':app'. > path may not be null or empty string. path='null'
categories:
  - flutter
tags:
  - Flutter, Android
---

## 에러 메시지

What went wrong: A problem occurred evaluating project ':app'. > path may not be null or empty string. path='null'

## 원인

Android 앱을 플레이 스토어에 배포할때 추가한 서명이 있는데, 해당 서명으로 인하여 로컬 개발환경에서 실행이 되지 않는 문제라고 함.

## 해결방안

개발 시 아래 내용을 <b>주석</b>하고, 배포 시 아래 내용을 <b>주석 해제</b>한다.
file: /android/app/build.gradle
아래 내용 주석 처리

```json
/*
    signingConfigs {
        release {
            keyAlias keystoreProperties['keyAlias']
            keyPassword keystoreProperties['keyPassword']
            storeFile file(keystoreProperties['storeFile'])
            storePassword keystoreProperties['storePassword']
        }
    }
    buildTypes {
        release {
            // TODO: Add your own signing config for the release build.
            // Signing with the debug keys for now, so `flutter run --release` works.
            signingConfig signingConfigs.release
        }
       */
```

## 참고

[https://github.com/transistorsoft/flutter_background_geolocation/issues/18#issuecomment-448714500](https://github.com/transistorsoft/flutter_background_geolocation/issues/18#issuecomment-448714500){: target="_blank"}
