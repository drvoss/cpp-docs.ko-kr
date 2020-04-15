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
ms.openlocfilehash: 9bd1cafe40417872d42f2e9e1427e5f2eccad7a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328862"
---
# <a name="common-problems-when-creating-a-release-build"></a>릴리스 빌드를 만들 때의 일반적인 문제

개발 하는 동안 일반적으로 빌드 하 고 프로젝트의 디버그 빌드를 테스트 합니다. 그런 다음 릴리스 빌드에 대 한 응용 프로그램을 빌드 하는 경우 액세스 위반을 얻을 수 있습니다.

아래 목록은 디버그와 릴리스(nondebug) 빌드 간의 주요 차이점을 보여 주며 있습니다. 다른 차이점이 있지만 디버그 빌드에서 작동할 때 릴리스 빌드에서 응용 프로그램이 실패하는 주요 차이점이 있습니다.

- [힙 레이아웃](#_core_heap_layout)

- [컴파일](#_core_compilation)

- [포인터 지원](#_core_pointer_support)

- [최적화](#_core_optimizations)

디버그 빌드에서 릴리스 빌드 오류를 catch하는 방법에 대한 자세한 내용은 [/GZ(디버그 빌드에서 릴리스-빌드 오류 Catch)](reference/gz-enable-stack-frame-run-time-error-checking.md) 컴파일러 옵션을 참조하십시오.

## <a name="heap-layout"></a><a name="_core_heap_layout"></a>힙 레이아웃

응용 프로그램이 디버그에서 작동하지만 릴리스되지 않을 때 힙 레이아웃은 명백한 문제의 약 90%가 원인입니다.

디버그에 대한 프로젝트를 빌드할 때 디버그 메모리 할당을 사용하고 있습니다. 즉, 모든 메모리 할당에는 가드 바이트가 배치됩니다. 이러한 가드 바이트는 메모리 덮어쓰기를 검색합니다. 힙 레이아웃은 릴리스 버전과 디버그 버전 간에 다르기 때문에 메모리 덮어쓰기로 인해 디버그 빌드에 문제가 발생하지 않을 수 있지만 릴리스 빌드에 치명적인 영향을 미칠 수 있습니다.

자세한 내용은 [메모리 덮어쓰기 확인을](checking-for-memory-overwrites.md) 참조하고 [디버그 빌드를 사용하여 메모리 덮어쓰기를 확인합니다.](using-the-debug-build-to-check-for-memory-overwrite.md)

## <a name="compilation"></a><a name="_core_compilation"></a>컴파일

대부분의 MFC 매크로와 릴리스용으로 빌드할 때 MFC 구현의 대부분이 변경됩니다. 특히 ASSERT 매크로는 릴리스 빌드에서 아무 것도 평가하지 않으므로 ASSERT에 있는 코드는 실행되지 않습니다. 자세한 내용은 [ASSERT 문 검사를](using-verify-instead-of-assert.md)참조하십시오.

일부 함수는 릴리스 빌드의 속도 향상을 위해 인라인되어 있습니다. 최적화는 일반적으로 릴리스 빌드에서 켜지다. 다른 메모리 할당자도 사용 중입니다.

## <a name="pointer-support"></a><a name="_core_pointer_support"></a>포인터 지원

디버깅 정보가 부족하면 응용 프로그램에서 패딩이 제거됩니다. 릴리스 빌드에서 길 잃은 포인터는 정보를 디버깅하는 대신 초기화되지 않은 메모리를 가리킬 가능성이 큽습니다.

## <a name="optimizations"></a><a name="_core_optimizations"></a>최적화

특정 코드 세그먼트의 특성에 따라 최적화 컴파일러는 예기치 않은 코드를 생성할 수 있습니다. 이것은 릴리스 빌드 문제의 가장 가능성이 낮은 원인이지만 경우에 따라 발생합니다. 해결 방법은 [코드 최적화](optimizing-your-code.md)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[릴리스 빌드](release-builds.md)<br/>
[릴리스 빌드 문제 해결](fixing-release-build-problems.md)
