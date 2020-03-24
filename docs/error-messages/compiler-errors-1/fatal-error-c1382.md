---
title: 심각한 오류 C1382
ms.date: 11/04/2016
f1_keywords:
- C1382
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
ms.openlocfilehash: 6ed70a81c4ae2028d09b694f325f83454e99a587
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203101"
---
# <a name="fatal-error-c1382"></a>심각한 오류 C1382

' obj '가 생성 되었으므로 ' file ' PCH 파일이 다시 작성 되었습니다. 이 개체를 다시 빌드하세요.

[/Ltcg](../../build/reference/ltcg-link-time-code-generation.md)를 사용 하는 경우 컴파일러에서이 파일을 가리키는 CIL .obj 보다 최신 .pch 파일을 발견 했습니다. CIL .obj 파일의 정보가 만료 되었습니다. 개체를 다시 빌드합니다.

C1382를 사용 하 여 컴파일하는 경우에도 발생할 수 있으며, 여러 소스 코드 **파일을 컴파일러**에 전달할 수도 있습니다.  이 문제를 해결 하려면 여러 소스 코드 파일을 컴파일러에 전달할 때 **/yc** 를 사용 하지 마십시오.  자세한 내용은 [/yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md)를 참조 하세요.
