---
title: 할당
ms.date: 11/04/2016
f1_keywords:
- allocate_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocate
- allocate __declspec keyword
ms.assetid: 67828b31-de60-4c0e-b0a6-ef3aab22641d
ms.openlocfilehash: 0bf31423cd76c838cbeffa7458bbccb89592bf43
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227623"
---
# <a name="allocate"></a>할당

**Microsoft 전용**

**`allocate`** 선언 지정자는 데이터 항목이 할당 되는 데이터 세그먼트의 이름을 지정 합니다.

## <a name="syntax"></a>구문

> **`__declspec(allocate("`***segname* **`))`** *선언 자*

## <a name="remarks"></a>설명

*Segname* 이름은 다음 pragma 중 하나를 사용 하 여 선언 해야 합니다.

- [code_seg](../preprocessor/code-seg.md)

- [const_seg](../preprocessor/const-seg.md)

- [data_seg](../preprocessor/data-seg.md)

- [init_seg](../preprocessor/init-seg.md)

- [여기서](../preprocessor/section.md)

## <a name="example"></a>예제

```cpp
// allocate.cpp
#pragma section("mycode", read)
__declspec(allocate("mycode"))  int i = 0;

int main() {
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[`__declspec`](../cpp/declspec.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)
