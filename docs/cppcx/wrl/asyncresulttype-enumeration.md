---
title: AsyncResultType 열거형
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: b8a2a9ec803fba1be0012fcb58bf3b42e78f9071
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214164"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType 열거형

`GetResults()` 메서드에서 반환 하는 결과의 형식을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum AsyncResultType;
```

## <a name="members"></a>멤버

### <a name="values"></a>값

|이름|설명|
|----------|-----------------|
|`MultipleResults`|`Start` 상태와 `Close()`를 호출 하기 전에 점진적으로 표시 되는 여러 결과 집합입니다.|
|`SingleResult`|`Complete` 이벤트가 발생 한 후 표시 되는 단일 결과입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** async. h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)
