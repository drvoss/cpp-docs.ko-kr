---
title: Android 디버거 속성 (C++)
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 3ac896b384181e4e2b436368f39a343d35fe321a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79470276"
---
# <a name="android-debugger-properties"></a>Android 디버거 속성

| 속성 | Description | 선택 사항 |
|--|--|--|
| 디버거 형식 | 디버그할 코드 형식을 지정합니다. | **네이티브 전용**<br /><br />**Java 전용** |
| 디버그 대상 | 디버깅에 사용할 에뮬레이터 또는 디바이스를 지정합니다. 실행 중인 에뮬레이터가 없으면 ' AVD (Android 가상 장치) 관리자 '를 사용 하 여 장치를 시작 합니다. |
| 실행할 패키지 | 디버그할 *.apk*의 위치를 지정합니다. 이 옵션은 응용 프로그램을 디버그할 때 패키지 (APK)를 시작 합니다. |
| 시작 작업 | 애플리케이션을 시작하는 데 사용하는 Android 작업은 매니페스트에서 사용하는 것과 일치해야 합니다. [적용]을 눌러 *AndroidManifest.xml*에서 목록을 검색하고 동적으로 채웁니다. |
| 추가 기호 검색 경로 | 디버그 기호에 대한 추가 검색 경로입니다. |
| 추가 Java 원본 검색 경로 | Java 원본 파일에 대한 추가 검색 경로입니다. (디버거 형식이 Java 전용인 경우에만 적용됩니다.) |
