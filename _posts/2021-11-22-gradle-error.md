---
title: "[Flutter] Cannot resolve symbol for properties and Gradle exception"
description: Flutter Cannot resolve symbol for properties and Gradle exception
categories:
  - flutter
tags:
  - flutter, gradle
---

## 내용

android/app/build.gradle
GradleException에 빨간색 줄이 떠있음

## 해결방안

GradleException을 FileNotFoundException으로 수정  
GradleException이 Android API 29 or 30에서 지원하지 않는것 같음

- GradleException -> FileNotFoundException

## 자세히 보기

[https://github.com/flutter/flutter/issues/29608#issuecomment-548649907](https://github.com/flutter/flutter/issues/29608#issuecomment-548649907){: target="_blank"}
