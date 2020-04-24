---
title: 링커 도구 오류 LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: d85693cec11ef53a6bbbb60d8ced716d2a0bb131
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754340"
---
# <a name="linker-tools-error-lnk1179"></a>링커 도구 오류 LNK1179

유효하지 않거나 손상된 파일: COMDAT '파일 이름' 복제

개체 모듈에는 이름이 같은 두 개 이상의 COMDA가 포함되어 있습니다.

이 오류는 외부 이름의 길이를 제한하는 [/H](../../build/reference/h-restrict-length-of-external-names.md)및 COMDAT에서 함수를 패키지하는 [/Gy를](../../build/reference/gy-enable-function-level-linking.md)사용하여 발생할 수 있습니다.

## <a name="example"></a>예제

다음 코드에서는 `function1` 처음 `function2` 8자에서 동일합니다. **/Gy** 및 **/H8로** 컴파일할 때 링크 오류가 발생합니다.

```cpp
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```
