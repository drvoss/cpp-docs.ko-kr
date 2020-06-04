---
title: 링커 도구 오류 LNK2022
ms.date: 11/04/2016
f1_keywords:
- LNK2022
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
ms.openlocfilehash: d30dad6f8ad146ff467eb4eaf32b21dd6950d25f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194644"
---
# <a name="linker-tools-error-lnk2022"></a>링커 도구 오류 LNK2022

> 메타 데이터 작업이 실패 했습니다 (*HRESULT*). *error_message*

메타 데이터를 병합 하는 동안 링커가 오류를 발견 했습니다. 메타 데이터 오류를 성공적으로 연결 하려면 해결 해야 합니다.

이 문제를 진단 하는 한 가지 방법은 개체 파일에 대해 **ildasm.exe** 를 실행 하 여 `error_message`에 나열 된 토큰이 있는 형식을 찾고 차이점을 확인 하는 것입니다.  메타 데이터에서 이름이 같은 두 개의 다른 형식이 유효 하지 않습니다 .이는 단순한 LayoutType 특성이 다른 경우에도 마찬가지입니다.

LNK2022에 대 한 한 가지 이유는 동일한 이름을 가진 여러 compilands에 형식 (예: 구조체)이 있지만 충돌 하는 정의가 있고 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)을 사용 하 여 컴파일하는 경우입니다.  이 경우 형식에 모든 compilands의 동일한 정의가 있는지 확인 합니다.  형식 이름은 `error_message`에 나열 됩니다.

LNK2022의 다른 가능한 원인은 링커가 컴파일러에 지정 된 것과 다른 위치에서 메타 데이터 파일을 찾을 때 ( [#using](../../preprocessor/hash-using-directive-cpp.md) )입니다. 메타데이터 파일(.dll 또는 .netmodule)이 링커에 전달될 때에도 컴파일러에 전달되었을 때 있던 것과 동일한 위치에 있는지 확인합니다.

ATL 응용 프로그램을 빌드할 때 하나 이상의 compilands에 사용 되는 경우에는 모든에서 매크로 `_ATL_MIXED`를 사용 해야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 빈 형식을 정의 합니다.

```cpp
// LNK2022_a.cpp
// compile with: /clr /c
public ref class Test {};
```

## <a name="example"></a>예제

이 샘플에서는 이름이 같지만 정의가 다른 두 소스 코드 파일을 연결할 수 없음을 보여 줍니다.

다음 샘플에서는 LNK2022를 생성 합니다.

```cpp
// LNK2022_b.cpp
// compile with: LNK2022_a.cpp /clr /LD
// LNK2022 expected
public ref class Test {
   void func() {}
   int var;
};
```
