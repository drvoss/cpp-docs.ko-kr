---
title: 컴파일러 한계
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: 9e61cae1638c87f03b6fa775552408961bde6859
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189582"
---
# <a name="compiler-limits"></a>컴파일러 한계

C++ 표준에서는 다양한 언어 구문에 대한 한도를 권장합니다. 다음은 Microsoft C++ 컴파일러에서 권장 된 한도를 구현 하지 않는 경우의 목록입니다. 첫 번째 숫자는 ISO C++ 11 표준 (INCITS/ISO/IEC 14882-2011 [2012], 부록 B)에서 설정 된 한도이 고 두 번째 숫자는 Microsoft C++ 컴파일러에서 구현 하는 제한입니다.

- 복합 문, 반복 제어 구조 및 선택 컨트롤 구조의 중첩 수준- C++ 표준: 256, Microsoft C++ 컴파일러: 중첩 된 문의 조합에 따라 다르지만 일반적으로 100과 110 사이에 있습니다.

- 단일 매크로 정의의 매개 변수 C++ -표준: 256, C++ Microsoft 컴파일러: 127.

- 단일 매크로 호출의 인수- C++ 표준: 256, Microsoft C++ 컴파일러 127.

- 문자열 리터럴 또는 와이드 문자열 리터럴의 문자 (연결 후)- C++ 표준: 65536, Microsoft C++ 컴파일러: 65535 단일 바이트 문자 (null 종결자 포함) 및 32767 더블 바이트 문자 (null 종결자 포함)를 포함 합니다.

- 단일 `struct-declaration-list`에서 중첩 된 클래스, 구조체 또는 공용 구조체 정의의 수준- C++ 표준: 256, Microsoft C++ 컴파일러: 16.

- 생성자 정의의 멤버 이니셜라이저- C++ 표준: 6144, Microsoft C++ 컴파일러: 최소 6144.

- 한 식별자의 범위 자격- C++ 표준: 256, Microsoft C++ 컴파일러: 127.

- 중첩 된 **extern** 사양 C++ -표준: 1024, C++ Microsoft 컴파일러: 9 (전역 범위에서 암시적 **extern** 사양을 계산 하지 않음, 전역 범위에서 암시적 **extern** 사양을 계산 하는 경우 10).

- 템플릿 선언의 템플릿 인수- C++ 표준: 1024, Microsoft C++ 컴파일러: 2046.

## <a name="see-also"></a>참고 항목

[비표준 동작](../cpp/nonstandard-behavior.md)
