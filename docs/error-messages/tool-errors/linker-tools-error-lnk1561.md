---
title: 링커 도구 오류 LNK1561
ms.date: 11/04/2016
f1_keywords:
- LNK1561
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
ms.openlocfilehash: b397ef8e551f8cd6179392541e35183a5850454f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357745"
---
# <a name="linker-tools-error-lnk1561"></a>링커 도구 오류 LNK1561

진입점을 정의해야 합니다.

링커는 실행 파일을 호출할 초기 함수인 *진입점을*찾지 못했습니다. 기본적으로 링커는 콘솔 앱, `main` `wmain` Windows 앱또는 초기화가 `WinMain` `wWinMain` 필요한 DLL에 `DllMain` 대한 또는 함수를 찾습니다. [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 링커 옵션을 사용하여 다른 함수를 지정할 수 있습니다.

이 오류에는 다음과 같은 여러 가지 원인이 있을 수 있습니다.

- 링크할 파일 목록에 진입점을 정의하는 파일을 포함하지 않았을 수 있습니다. 진입점 함수가 포함된 파일이 앱에 연결되어 있는지 확인합니다.
- 잘못된 함수 서명을 사용하여 진입점을 정의했을 수 있습니다. 예를 들어 함수 이름에 대해 맞춤법이 잘못 되었거나 잘못된 대/소문자를 사용했거나 return 형식 또는 매개 변수 형식을 잘못 지정했을 수 있습니다.
- DLL을 빌드할 때 [/DLL](../../build/reference/dll-build-a-dll.md) 옵션을 지정하지 않았을 수 있습니다.
- [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 링커 옵션을 사용할 때 진입점 함수의 이름을 잘못 지정했을 수 있습니다.
- [LIB](../../build/reference/lib-reference.md) 도구를 사용하여 DLL을 빌드하는 경우 .def 파일을 지정했을 수 있습니다. 그렇다면 빌드에서 .def 파일을 제거합니다.

앱을 빌드할 때 링커는 코드를 시작하기 위해 호출할 진입점 함수를 찾습니다. 이 함수는 앱이 로드되고 런타임이 초기화된 후에 호출되는 함수입니다. 앱에 대한 진입점 함수를 제공해야 하거나 앱을 실행할 수 없습니다. 진입점은 DLL의 선택 사항입니다. 기본적으로 링커는 `int main(int, char**)`다음과 같은 여러 특정 이름과 서명 중 하나가 있는 진입점 함수를 찾습니다. /ENTRY 링커 옵션을 사용하여 다른 함수 이름을 진입점으로 지정할 수 있습니다.

## <a name="example"></a>예제

다음 샘플은 LNK1561을 생성합니다.

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```
