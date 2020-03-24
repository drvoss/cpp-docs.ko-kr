---
title: 컴파일러 경고(수준 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: b75b6bee88d0b72e77b32e58ae2f4634a9c30fa0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187000"
---
# <a name="compiler-warning-level-1-c4377"></a>컴파일러 경고(수준 1) C4377

네이티브 형식은 기본적으로 private입니다. -d1PrivateNativeTypes는 사용 되지 않습니다.

이전 릴리스에서는 어셈블리의 네이티브 형식이 기본적으로 public이 고 문서화 되지 않은 내부 컴파일러 옵션 ( **/d1PrivateNativeTypes**)을 사용 하 여 전용으로 설정 했습니다.

모든 형식, 네이티브 및 CLR은 이제 기본적으로 어셈블리에서 private 이므로 **/d1PrivateNativeTypes** 가 더 이상 필요 하지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4377를 생성 합니다.

```cpp
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```
