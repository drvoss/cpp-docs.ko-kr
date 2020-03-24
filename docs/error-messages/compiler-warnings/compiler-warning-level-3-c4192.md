---
title: 컴파일러 경고 (수준 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 38b346e0a90729bda431b9cb578a03806be1ea4c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198980"
---
# <a name="compiler-warning-level-3-c4192"></a>컴파일러 경고 (수준 3) C4192

' library ' 형식 라이브러리를 가져오는 동안 ' 이름 '을 자동으로 제외 합니다.

`#import` 라이브러리에는 Win32 시스템 헤더에도 정의 된 항목인 *이름이*있습니다. 형식 라이브러리의 제한 사항으로 인해 **IUnknown** 또는 GUID와 같은 이름이 형식 라이브러리에 정의 되는 경우가 많으므로 시스템 헤더의 정의가 중복 됩니다. `#import`는 이러한 항목을 검색 하 고 .tlh 및 .ttl 헤더 파일에 포함 하는 것을 거부 합니다.

이 동작을 재정의 하려면 `#import` 특성 [no_auto_exclude](../../preprocessor/no-auto-exclude.md) 를 사용 하 고 [()을 포함](../../preprocessor/include-parens.md)합니다.
