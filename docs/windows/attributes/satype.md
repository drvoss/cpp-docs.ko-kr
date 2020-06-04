---
title: satype (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: 4619deec6d5e4e9083fbc7bcab53caee0101285c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166278"
---
# <a name="satype"></a>satype

`SAFEARRAY` 구조의 데이터 형식을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>매개 변수

*data_type*<br/>
인터페이스 메서드에 매개 변수로 전달 되는 `SAFEARRAY` 데이터 구조체의 데이터 형식입니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 매개 변수, 인터페이스 메서드|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|None|

## <a name="remarks"></a>설명

**Satype** C++ 특성은 `SAFEARRAY`의 데이터 형식을 지정 합니다.

> [!NOTE]
> 생성 된 .idl 파일의 `SAFEARRAY` 포인터에서 간접 참조 수준이 .cpp 파일에 선언 된 방법에서 삭제 됩니다.

## <a name="example"></a>예제

```cpp
// cpp_attr_ref_satype.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyModule")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A {
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="see-also"></a>참고 항목

[컴파일러 특성](compiler-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[id](id.md)
