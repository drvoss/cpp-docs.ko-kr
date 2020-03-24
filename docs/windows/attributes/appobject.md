---
title: appobject (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.appobject
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
ms.openlocfilehash: ebbb3ce71dc9b947ef49a42ee41a5ce2d5abbb34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168514"
---
# <a name="appobject"></a>appobject

Coclass를 전체 .exe 응용 프로그램과 연결 된 응용 프로그램 개체로 식별 하 고 coclass의 함수 및 속성을이 [형식 라이브러리](../../mfc/automation-clients-using-type-libraries.md)에서 전역적으로 사용할 수 있음을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
[appobject]
```

## <a name="remarks"></a>설명

**Appobject** C++ 특성은 [appobject](/windows/win32/Midl/appobject) MIDL 특성과 동일한 기능을 포함 합니다.

## <a name="example"></a>예제

다음 코드에서는 **appobject**을 포함 하는 특성 블록이 앞에 오는 간단한 클래스 정의를 보여 줍니다.

```cpp
// cpp_attr_ref_appobject.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];

[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]
__interface ICustom {};

[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]
class A : public ICustom {
   int i;
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**클래스**, **구조체**|
|**반복 가능**|예|
|**필수 특성**|`coclass`|
|**잘못된 특성**|None|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)
