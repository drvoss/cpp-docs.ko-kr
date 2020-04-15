---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: a30840aa0556a7324ba24c0f2aaec57dea88d082
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367859"
---
# <a name="noreturn"></a>noreturn

**마이크로소프트 특정**

이 **__declspec** 특성은 함수가 반환되지 않음을 컴파일러에 알려줍니다. 결과적으로 컴파일러는 **__declspec(noreturn)** 함수를 호출한 다음 코드에 연결할 수 없다는 것을 알고 있습니다.

컴파일러가 값을 반환하지 않는 제어 경로를 가진 함수를 발견할 경우 경고(C4715) 또는 오류 메시지(C2202)가 생성됩니다. 반환되지 않는 함수로 인해 제어 경로에 도달할 수 없는 경우 **__declspec(noreturn)를** 사용하여 이 경고 또는 오류를 방지할 수 있습니다.

> [!NOTE]
> 반환할 것으로 예상되는 함수에 **__declspec(noreturn)를** 추가하면 정의되지 않은 동작이 발생할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서 **else** 절에는 return 문이 포함되어 있지 않습니다.  `fatal` **__declspec(noreturn)로** 선언하는 것은 오류 또는 경고 메시지를 방지합니다.

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
