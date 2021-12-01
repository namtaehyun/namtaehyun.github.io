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

~~Android 앱을 플레이 스토어에 배포할때 추가한 서명이 있는데, 해당 서명으로 인하여 로컬 개발환경에서 실행이 되지 않는 문제라고 함.~~

> (**2021.12.01 추가**)  
> 해당 내용을 주석하면 해결되는게 맞지만, 근본적인 원인은 keystoreProperties를 못찾아서 발생한 문제 였음.  
> 에러 내용을 조금 더 자세히보면 특정 line이 적혀 있는데, 해당 라인이 keystoreProperties였음.  
> 정의 부분을 찾아보니 key.properties 파일을 찾는데, 해당 파일이 없어서 발생한 문제 였음.

## 해결방안

> (**2021.12.01 추가**)  
> Github에 push 할때 key.properties가 빠져 있어서 발생한 문제.  
> 해당 파일을 다른 개발자에게 받도록 하자!

---

~~개발 시 아래 내용을 <b>주석</b>하고, 배포 시 아래 내용을 <b>주석 해제</b>한다.
file: /android/app/build.gradle
아래 내용 주석 처리~~

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

[https://github.com/transistorsoft/flutter_background_geolocation/issues/18#issuecomment-448714500](https://github.com/transistorsoft/flutter_background_geolocation/issues/18#issuecomment-448714500){: target="\_blank"}
