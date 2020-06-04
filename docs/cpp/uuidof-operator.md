---
title: __uuidof 연산자
ms.date: 10/10/2018
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
- __uuidof
- _uuidof
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
ms.openlocfilehash: 09348d061fde4cb09eb6eb351f146404f355e184
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187793"
---
# <a name="__uuidof-operator"></a>__uuidof 연산자

**Microsoft 전용**

식에 연결된 GUID를 검색합니다.

## <a name="syntax"></a>구문

```
__uuidof (expression)
```

## <a name="remarks"></a>설명

*식은* 형식 이름, 포인터, 참조 또는 해당 형식의 배열, 이러한 형식에 대해 특수화 된 템플릿 또는 이러한 형식의 변수 일 수 있습니다. 컴파일러에서 인수를 사용하여 연결된 GUID를 찾을 수 있으면 해당 인수는 유효합니다.

이 내장 함수의 특수 한 경우는 **0** 또는 NULL이 인수로 제공 되는 경우입니다. 이 경우 **__uuidof** 는 0으로 구성 된 GUID를 반환 합니다.

이 키워드를 사용하여 연결된 GUID를 다음으로 추출합니다.

- [Uuid](../cpp/uuid-cpp.md) 확장 특성을 기준으로 하는 개체입니다.

- [Module](../windows/attributes/module-cpp.md) 특성을 사용 하 여 만든 라이브러리 블록입니다.

> [!NOTE]
> 디버그 빌드에서는 항상 개체를 동적으로 (런타임에) 초기화 **__uuidof** 합니다. 릴리스 빌드에서는 정적으로 (컴파일 시간에) 개체를 초기화할 수 **__uuidof** .

이전 버전과의 호환성을 위해 **_uuidof** 는 컴파일러 옵션 [/za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 이 지정 된 경우를 제외 하 고 **__uuidof** 의 동의어입니다.

## <a name="example"></a>예제

ole32.lib를 사용하여 컴파일된 다음 코드는 module 특성을 사용하여 만든 라이브러리 블록의 uuid를 표시합니다.

```cpp
// expre_uuidof.cpp
// compile with: ole32.lib
#include "stdio.h"
#include "windows.h"

[emitidl];
[module(name="MyLib")];
[export]
struct stuff {
   int i;
};

int main() {
   LPOLESTR lpolestr;
   StringFromCLSID(__uuidof(MyLib), &lpolestr);
   wprintf_s(L"%s", lpolestr);
   CoTaskMemFree(lpolestr);
}
```

## <a name="comments"></a>주석

라이브러리 이름이 범위에 더 이상 없는 경우에는 **__uuidof**대신 `__LIBID_`를 사용할 수 있습니다. 다음은 그 예입니다.

```cpp
StringFromCLSID(__LIBID_, &lpolestr);
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[키워드](../cpp/keywords-cpp.md)
