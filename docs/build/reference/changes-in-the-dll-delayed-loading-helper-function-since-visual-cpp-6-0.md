---
title: Visual C++ 6.0 이후 DLL 지연 로드 도우미 함수의 변경 내용
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
ms.openlocfilehash: 536729e27c89d068957ea451355957e4a35348ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320603"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 이후 DLL 지연 로드 도우미 함수의 변경 내용

컴퓨터에 여러 버전의 Visual C++가 있거나 자체 도우미 기능을 정의한 경우 DLL 지연 된 로드 도우미 기능의 변경 사항에 의해 영향을 받을 수 있습니다. 다음은 그 예입니다.

- **__delayLoadHelper** 이제 **__delayLoadHelper2**

- **__pfnDliNotifyHook** 이제 **__pfnDliNotifyHook2**

- **__pfnDliFailureHook** 이제 **__pfnDliFailureHook2**

- **__FUnloadDelayLoadedDLL** 이제 **__FUnloadDelayLoadedDLL2**

> [!NOTE]
> 기본 도우미 함수를 사용하는 경우 이러한 변경 내용은 영향을 주지 않습니다. 링커를 호출하는 방법에 대해서는 변경 사항이 없습니다.

## <a name="multiple-versions-of-visual-c"></a>여러 버전의 Visual C++

컴퓨터에 여러 버전의 Visual C++가 있는 경우 링커가 delayimp.lib과 일치하는지 확인합니다. 불일치가 있는 경우 링커 오류가 `___delayLoadHelper2@8` 보고되거나 `___delayLoadHelper@8` 확인되지 않은 외부 기호로 표시됩니다. 전자는 이전 delayimp.lib와 새 링커를 의미하고, 후자는 새로운 delayimp.lib와 이전 링커를 의미한다.

해결되지 않은 링커 오류가 발생하면 delayimp.lib에서 [dumpbin /linkermember](linkermember.md):1을 실행하여 도우미 함수를 포함하여 어떤 도우미 함수가 대신 정의되는지 확인합니다. 도우미 함수는 개체 파일에 정의할 수도 있습니다. [덤프빈 / 기호를](symbols.md) 실행하고 `delayLoadHelper(2)`찾습니다.

Visual C++ 6.0 링커가 있는 경우 다음을 수행하십시오.

- 지연 로드 도우미의 .lib 또는 .obj 파일에 덤프빈을 실행하여 **__delayLoadHelper2**정의하는지 여부를 결정합니다. 그렇지 않으면 링크가 실패합니다.

- 지연 로드 도우미의 .lib 또는 .obj 파일에서 **__delayLoadHelper** 정의합니다.

## <a name="user-defined-helper-function"></a>사용자 정의 도우미 기능

사용자 고유의 도우미 함수를 정의하고 현재 버전의 Visual C++를 사용하는 경우 다음을 수행합니다.

- 도우미 함수의 이름을 **__delayLoadHelper2.**

- 지연 설명자(delayimp.h의 ImgDelayDescr)의 포인터가 절대 주소(VA)에서 상대 주소(RV)로 변경되어 32비트 및 64비트 프로그램에서 예상대로 작동하므로 이러한 포인터를 다시 포인터로 변환해야 합니다. delayhlp.cpp에서 발견되는 PFromRva라는 새로운 기능이 도입되었습니다. 설명자의 각 필드에서 이 함수를 사용하여 32비트 또는 64비트 포인터로 다시 변환할 수 있습니다. 기본 지연 로드 도우미 함수는 예제로 사용할 수 있는 좋은 템플릿으로 계속 됩니다.

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>지연 로드DLL에 대한 모든 가져오기 로드

링커는 지연 로드되도록 지정한 DLL의 모든 가져오기를 로드할 수 있습니다. 자세한 내용은 [지연 로드DLL에 대한 모든 가져오기 로드를](loading-all-imports-for-a-delay-loaded-dll.md) 참조하십시오.

## <a name="see-also"></a>참고 항목

[도우미 함수 이해](understanding-the-helper-function.md)
