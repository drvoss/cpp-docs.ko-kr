---
title: 심각한 오류 C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: b8630a26d14c68a5f1abe45bb0b8d0141d0dedbb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204193"
---
# <a name="fatal-error-c1081"></a>심각한 오류 C1081

' symbol ': 파일 이름이 너무 깁니다.

파일 경로 이름의 길이가 `_MAX_PATH`을 초과 합니다 (STDLIB.H에서 260 자로 정의 됨). 파일의 이름을 줄입니다.

짧은 파일 이름으로 CL.EXE를 호출 하는 경우 컴파일러에서 전체 경로 이름을 생성 해야 할 수 있습니다. 예를 들어 `cl -c myfile.cpp` 하면 컴파일러가를 생성할 수 있습니다.

```
D:\<very-long-directory-path>\myfile.cpp
```
