---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: f0b5b17a6d64375f49a6d55021c72ba7119eb976
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213309"
---
# <a name="noreturn"></a>noreturn

**Microsoft 전용**

이 **`__declspec`** 특성은 함수가 반환 하지 않음을 컴파일러에 알립니다. 결과적으로 컴파일러는 함수 호출 후의 코드에 **`__declspec(noreturn)`** 접근할 수 없음을 알고 있습니다.

컴파일러가 값을 반환하지 않는 제어 경로를 가진 함수를 발견할 경우 경고(C4715) 또는 오류 메시지(C2202)가 생성됩니다. 반환 되지 않는 함수로 인해 제어 경로에 연결할 수 없는 경우를 사용 **`__declspec(noreturn)`** 하 여이 경고 또는 오류를 방지할 수 있습니다.

> [!NOTE]
> 반환 될 것으로 예상 되는 **`__declspec(noreturn)`** 함수에를 추가 하면 정의 되지 않은 동작이 발생할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서 절에는 **`else`** return 문이 포함 되어 있지 않습니다.  `fatal`로 선언 **`__declspec(noreturn)`** 하면 오류 또는 경고 메시지가 방지 됩니다.

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

## <a name="see-also"></a>참조

[__declspec](../cpp/declspec.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)
