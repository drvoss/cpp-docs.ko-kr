---
title: 컴파일러 경고(수준 3) C4191
ms.date: 11/04/2016
f1_keywords:
- C4191
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
ms.openlocfilehash: 817e74d278aa3d91c65ffeb8ab9ac5844041446e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198967"
---
# <a name="compiler-warning-level-3-c4191"></a>컴파일러 경고(수준 3) C4191

'operator/operation': '식 형식'에서 '필요한 형식'으로의 변환이 안전하지 않습니다.

함수 포인터와 관련된 다음 몇 가지 작업이 안전하지 않은 것으로 간주됩니다.

- 여러 호출 규칙을 사용하는 함수 형식

- 여러 반환 규칙을 사용하는 함수 형식

- 여러 크기, 형식 범주 또는 분류를 사용하는 인수 또는 반환 형식

- 다양한 인수 목록 길이( `__cdecl`에서 짧은 목록이 varargs인 경우에도 긴 목록에서 짧은 목록으로 캐스트할 때만)

- 함수의 포인터에 대해 별칭이 지정 된 데이터에 대 한 포인터입니다 ( **void** <strong>\*</strong>제외).

- `reinterpret_cast`에 오류 또는 경고를 생성하는 다른 형식 차이

결과 포인터를 통해 이 함수를 호출하면 프로그램에서 충돌이 발생할 수 있습니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

다음 샘플에서는 C4191을 생성합니다.

```cpp
// C4191.cpp
// compile with: /W3 /clr
#pragma warning(default: 4191)

void __clrcall f1() { }
void __cdecl   f2() { }

typedef void (__clrcall * fnptr1)();
typedef void (__cdecl   * fnptr2)();

int main() {
   fnptr1 fp1 = static_cast<fnptr1>(&f1);
   fnptr2 fp2 = (fnptr2) &f2;

   fnptr1 fp3 = (fnptr1) &f2;   // C4191
   fnptr2 fp4 = (fnptr2) &f1;   // C4191
};
```
