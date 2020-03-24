---
title: pointer_default (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: d0c5832623c1e418f4c6e8bdb606d1d363503483
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166538"
---
# <a name="pointer_default"></a>pointer_default

매개 변수 목록에 표시 되는 최상위 포인터를 제외 하 고 모든 포인터에 대 한 기본 포인터 특성을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>매개 변수

*value*<br/>
포인터 형식 ( **ptr**, **ref**또는 **unique**)을 설명 하는 값입니다.

## <a name="remarks"></a>설명

**Pointer_default** C++ 특성에는 [pointer_default](/windows/win32/Midl/pointer-default) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

**Pointer_default**의 샘플 사용에 대해서는 [defaultvalue](defaultvalue.md) 의 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**interface**|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|None|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)
