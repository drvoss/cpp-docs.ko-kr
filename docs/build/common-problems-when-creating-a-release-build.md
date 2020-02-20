---
title: 릴리스 빌드를 만들 때의 일반적인 문제
ms.date: 11/04/2016
helpviewer_keywords:
- unexpected code generation
- debugging [MFC], release builds
- release builds, troubleshooting
- stray pointers
- debug builds, difference from release builds
- MFC [C++], release builds
- heap layout problems
- pointers, stray
- release builds, building applications
- debug memory allocator
- optimization [C++], compiler
- projects [C++], debug configuration
- troubleshooting release builds
- memory [C++], overwrites
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
ms.openlocfilehash: 5372fe4e96c444d454c277394dd811cfac14d1f6
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220903"
---
# <a name="common-problems-when-creating-a-release-build"></a>릴리스 빌드를 만들 때의 일반적인 문제

개발하는 동안 일반적으로 프로젝트의 디버그 빌드를 빌드하고 테스트합니다. 다음 릴리스 빌드에 대한 응용 프로그램을 작성하는 경우 액세스 위반이 발생할 수 있습니다.

아래 목록은 디버그 및 릴리스(비디버그) 빌드 간의 주요 차이점을 보여 줍니다. 다른 차이점도 있지만, 다음은 디버그 빌드에서 작동할 때 릴리스 빌드에서 응용 프로그램이 실패하는 주요 차이점입니다.

- [힙 레이아웃](#_core_heap_layout)

- [컴파일](#_core_compilation)

- [포인터 지원](#_core_pointer_support)

- [최적화](#_core_optimizations)

디버그 빌드에서 릴리스 빌드 오류를 포착하는 방법에 대한 정보는 [/GZ(디버그 빌드에서 릴리스 빌드 오류 포착)](reference/gz-enable-stack-frame-run-time-error-checking.md) 컴파일러 옵션을 참조합니다.

##  <a name="_core_heap_layout"></a> 힙 레이아웃

힙 레이아웃은 응용 프로그램이 디버그에서는 작동하지만 릴리스에서는 그렇지 않은 명백한 문제의 약 90%의 원인을 차지합니다.

디버그할 프로젝트를 빌드할 때 디버그 메모리 할당자를 사용합니다. 이는 모든 메모리 할당에 guard 바이트가 배치되어 있음을 의미합니다. 이 보호 바이트는 메모리 덮어쓰기를 감지합니다. 릴리스와 디버그 버전 간에 힙 레이아웃이 다르기 때문에 메모리 덮어쓰기는 디버그 빌드에서 문제를 일으키지 않지만 릴리스 빌드에서는 치명적인 영향을 줄 수 있습니다.

자세한 내용은 [메모리 덮어쓰기 확인](checking-for-memory-overwrites.md)과 [디버그 빌드를 사용하여 메모리 덮어쓰기 검사](using-the-debug-build-to-check-for-memory-overwrite.md)를 참조합니다.

##  <a name="_core_compilation"></a> 컴파일

릴리스를 빌드할 때 많은 MFC 매크로와 대부분의 MFC 구현이 변경됩니다. 특히 ASSERT 매크로는 릴리스 빌드에 포함되지 않으므로 ASSERT에 포함된 코드는 실행되지 않습니다. 자세한 내용은 [ASSERT 문 검사](using-verify-instead-of-assert.md)를 참조하세요.

릴리스 빌드에서 속도 향상을 위해 일부 기능이 인라인되었습니다. 최적화는 일반적으로 릴리스 빌드에서 켜집니다. 메모리 할당자도 다른 것을 사용합니다.

##  <a name="_core_pointer_support"></a> 포인터 지원

디버깅 정보가 없으면 응용 프로그램에서 패딩이 제거됩니다. 릴리스 빌드에서 스트레이 포인터는 디버그 정보를 가리키는 대신 초기화되지 않은 메모리를 가리킬 가능성이 더 높습니다.

##  <a name="_core_optimizations"></a> 최적화

특정 코드 세그먼트 성격에 따라 최적화 컴파일러가 예기치 않은 코드를 생성할 수 있습니다. 이는 릴리스 빌드 문제 중 가장 가능성이 낮은 원인이지만 가끔 발생합니다. 해결 방법은 [코드 최적화](optimizing-your-code.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[릴리스 빌드](release-builds.md)<br/>
[릴리스 빌드 문제 해결](fixing-release-build-problems.md)
