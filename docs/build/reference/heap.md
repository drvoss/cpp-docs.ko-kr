---
title: /HEAP
description: MSVC 링커 또는 EDITBIN/HEAP 옵션은 총 힙 크기를 설정 하 고 선택적으로 추가 힙 블록의 크기를 설정 합니다.
ms.date: 07/07/2020
f1_keywords:
- /heap
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
ms.openlocfilehash: 7976ae2927ca731c83fa42e87da182fee4df3d7c
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127830"
---
# `/HEAP`

힙 크기를 바이트 단위로 설정합니다. 이 옵션은 실행 파일에만 적용됩니다.

## <a name="syntax"></a>구문

> **`/HEAP:`**_`reserve`_\[**`,`**_`commit`_]

## <a name="remarks"></a>설명

*`reserve`* 인수는 가상 메모리의 총 초기 힙 할당을 지정 합니다. **`/HEAP`** 링커 또는 [EDITBIN](editbin-reference.md) 옵션은 지정 된 값을 4 바이트의 가장 가까운 배수로 반올림 합니다. 기본적으로 힙 크기는 1MB입니다.

선택적 *`commit`* 인수는 운영 체제에서 해석할 수 있습니다. Windows 운영 체제에서는 할당할 실제 메모리의 초기 크기를 지정 합니다. 또한 힙이 확장 될 때 할당할 메모리 양을 지정 합니다. 커밋된 가상 메모리를 설정 하면 페이징 파일에 공간이 예약 됩니다. 높은 *`commit`* 값을 사용 하면 응용 프로그램에 더 많은 힙 공간이 필요할 때 시스템에서 메모리를 할당할 수 있을 뿐만 아니라 메모리 요구 사항과 앱 시작 기간을 늘릴 수도 있습니다. *`commit`* 값은 값 보다 작거나 같아야 합니다 *`reserve`* . 기본값은 4kb입니다.

*`reserve`* 및 값을 *`commit`* 10 진수, C 언어 16 진수 또는 8 진수 표기법으로 지정 합니다. 예를 들어 값 1MB는 10진수의 경우 1048576, 16진수의 경우 0x100000, 8진수의 경우 04000000으로 지정할 수 있습니다. 기본값은 옵션과 동일 **`/HEAP:1048576,4096`** 합니다.

### <a name="example"></a>예제

이 예제 링크 명령은 힙 예약이 2mb 인 실행 파일 *main.exe* 를 만듭니다. 초기 힙 및 이후 힙 확장은 64 KB 블록으로 제공 됩니다.

**`link /heap:0x200000,0x10000 main.obj`**

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 정보는 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **구성 속성**  >  **링커**  >  **시스템** 속성 페이지를 선택 합니다.

1. **힙 예약 크기** 및 **힙 커밋 크기** 속성을 설정한 다음 **확인** 또는 **적용** 을 선택 하 여 변경 내용을 저장 합니다.

## <a name="see-also"></a>참고 항목

[EDITBIN 옵션](editbin-options.md)\
[MSVC 링커 옵션](linker-options.md)
