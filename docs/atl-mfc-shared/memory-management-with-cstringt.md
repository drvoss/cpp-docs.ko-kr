---
title: CStringT를 사용한 메모리 관리
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
ms.openlocfilehash: bf1f99b92761c84d59b6f7bfb9aef67d7e097893
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222032"
---
# <a name="memory-management-with-cstringt"></a>CStringT를 사용한 메모리 관리

[CStringT](../atl-mfc-shared/reference/cstringt-class.md) 클래스는 가변 길이 문자열을 조작 하는 데 사용 되는 템플릿 클래스입니다. 이러한 문자열을 저장할 메모리는 각 인스턴스와 연결 된 문자열 관리자 개체를 통해 할당 및 해제 됩니다 `CStringT` . MFC 및 ATL은 `CStringT` `CString` `CStringA` 다른 문자 형식의 문자열을 조작 하는, 및 이라는의 기본 인스턴스화를 제공 `CStringW` 합니다. 이러한 문자 형식은 각각 TCHAR.H, 및 형식입니다 **`char`** **`wchar_t`** . 이러한 기본 문자열 형식은 프로세스 힙 (ATL) 또는 CRT 힙 (MFC)에서 메모리를 할당 하는 문자열 관리자를 사용 합니다. 일반적인 응용 프로그램의 경우이 메모리 할당 스키마로 충분 합니다. 그러나 문자열이 나 다중 스레드 코드를 집중적으로 사용 하는 코드의 경우 기본 메모리 관리자가 최적으로 수행 되지 않을 수 있습니다. 이 항목에서는의 기본 메모리 관리 동작을 재정의 하 여 현재 `CStringT` 작업에 대해 특별히 최적화 된 할당자를 만드는 방법에 대해 설명 합니다.

- [사용자 지정 문자열 관리자 구현 (기본 방법)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [힙 경합 방지](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [사용자 지정 문자열 관리자 구현 (고급 메서드)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: 사용자 지정 문자열 관리자의 예](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>참고 항목

[CustomString 샘플](../overview/visual-cpp-samples.md)
