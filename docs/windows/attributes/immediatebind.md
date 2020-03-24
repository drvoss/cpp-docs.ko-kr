---
title: immediatebind (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.immediatebind
helpviewer_keywords:
- immediatebind attribute
ms.assetid: 186d40e6-9166-4d0c-9853-4e7e4d25226f
ms.openlocfilehash: d0fb85a3f5642bc5fffcad29892ca15bb13a1ce0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166916"
---
# <a name="immediatebind"></a>immediatebind

데이터 바인딩된 개체의 속성에 대 한 모든 변경 내용이 데이터베이스에 즉시 전달 됨을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
[immediatebind]
```

## <a name="remarks"></a>설명

**Immediatebind** C++ 특성은 [immediatebind](/windows/win32/Midl/immediatebind) MIDL 특성과 동일한 기능을 포함 합니다.

## <a name="example"></a>예제

**Immediatebind**를 사용 하는 방법에 대 한 예제는 [바인딩](bindable.md) 가능을 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 메서드|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|None|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[requestedit](requestedit.md)
