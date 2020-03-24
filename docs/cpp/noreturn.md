---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: f37ce13e27f9b141eab928b88102813a5b6d65f8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177887"
---
# <a name="noreturn"></a>noreturn

**Microsoft 전용**

이 **__declspec** 특성은 함수가 반환 하지 않음을 컴파일러에 알립니다. 결과적으로 컴파일러는 **__declspec (noreturn)** 함수를 호출 하는 코드를 연결할 수 없다는 것을 알고 있습니다.

컴파일러가 값을 반환하지 않는 제어 경로를 가진 함수를 발견할 경우 경고(C4715) 또는 오류 메시지(C2202)가 생성됩니다. 반환 되지 않는 함수로 인해 제어 경로에 연결할 수 없는 경우에는 **__declspec (noreturn)** 를 사용 하 여이 경고 또는 오류를 방지할 수 있습니다.

> [!NOTE]
>  반환 될 것으로 예상 되는 함수에 **__declspec (noreturn)** 을 추가 하면 정의 되지 않은 동작이 발생할 수 있습니다.

## <a name="example"></a>예제

다음 샘플의 **else** 절에는 return 문이 포함 되어 있지 않습니다.  `fatal`를 **__declspec (noreturn)** 로 선언 하면 오류 또는 경고 메시지가 방지 됩니다.

```cpp
// noreturn2.cpp
__declspec(noreturn) extern void fatal () {}

int main() {
   if(1)
     return 1;
   else if(0)
     return 0;
   else
     fatal();
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)
