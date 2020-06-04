---
title: 컴파일러 오류 C2567
ms.date: 11/04/2016
f1_keywords:
- C2567
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
ms.openlocfilehash: 921992c678c1de0b74f99f544173478ebe809b2c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177458"
---
# <a name="compiler-error-c2567"></a>컴파일러 오류 C2567

' file '에서 메타 데이터를 열 수 없습니다. 파일이 삭제 되었거나 이동 되었을 수 있습니다.

컴파일러 프런트 엔드 프로세스에서와 같이 소스에서 참조 된 메타 데이터 파일 (`#using`)이 컴파일러 백 엔드 프로세스에 의해 동일한 디렉터리에 없습니다. 자세한 내용은 [#using 지시문](../../preprocessor/hash-using-directive-cpp.md) 을 참조 하십시오.

한 컴퓨터에서 **/c** 를 사용 하 여 컴파일한 후 다른 컴퓨터에서 링크 타임 코드 생성을 시도 하는 경우 C2567 발생할 수 있습니다. 자세한 내용은 [/ltcg (링크 타임 코드 생성)](../../build/reference/ltcg-link-time-code-generation.md))를 참조 하세요.

또한 컴퓨터에 메모리가 더 이상 없음을 나타낼 수 있습니다.

이 오류를 해결 하려면 빌드 프로세스의 모든 단계에 대해 메타 데이터 파일이 동일한 디렉터리 위치에 있어야 합니다.
