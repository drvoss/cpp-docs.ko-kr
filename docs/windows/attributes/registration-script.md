---
title: registration_script (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.registration_script
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
ms.openlocfilehash: 780f3d41676d01458f47542d6f0862a278edff6a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214580"
---
# <a name="registration_script"></a>registration_script

지정 된 사용자 지정 등록 스크립트를 실행 합니다.

## <a name="syntax"></a>구문

```cpp
[ registration_script(script) ]
```

### <a name="parameters"></a>매개 변수

*스크립트도*<br/>
사용자 지정 등록 스크립트 (.rgs) 파일의 전체 경로입니다. **None**값 (예: `script = "none"`)은 coclass에 등록 요구 사항이 없음을 나타냅니다.

## <a name="remarks"></a>주의

**Registration_script** C++ 특성은 *스크립트로*지정 된 사용자 지정 등록 스크립트를 실행 합니다. 이 특성을 지정 하지 않으면 구성 요소 등록에 대 한 정보를 포함 하는 표준 .rgs 파일이 사용 됩니다. .Rgs 파일에 대 한 자세한 내용은 [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)를 참조 하세요.

이 특성을 사용하려면 [coclass](coclass.md), [progid](progid.md)또는 [vi_progid](vi-progid.md) 특성(또는 이 중 하나를 암시하는 다른 특성)을 동일한 요소에 적용해야 합니다.

## <a name="example"></a>예제

다음 코드는 구성 요소에 cpp_attr_ref_registration_script 라는 레지스트리 스크립트가 있도록 지정 합니다.

```cpp
// cpp_attr_ref_registration_script.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="REG")];

[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]
__interface IFace {};

// requires "cpp_attr_ref_registration_script.rgs"
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]
class CMyClass:public IFace {};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**클래스**, **구조체**|
|**반복 가능**|아니요|
|**필수 특성**|`coclass`, `progid`또는 `vi_progid`중 하나 이상입니다.|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[COM 특성](com-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[rdx](rdx.md)
