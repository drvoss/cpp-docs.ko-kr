---
title: registration_script (c + + COM 특성) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.registration_script
dev_langs:
- C++
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: edc9d5aa1d7c49de34ee3dbb02d2a55542962a50
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791809"
---
# <a name="registrationscript"></a>registration_script

지정 된 사용자 지정 등록 스크립트를 실행합니다.

## <a name="syntax"></a>구문

```cpp
[ registration_script(script) ]
```

### <a name="parameters"></a>매개 변수

*스크립트*<br/>
사용자 지정 등록 스크립트 (.rgs) 파일에 전체 경로입니다. 값이 **none**와 같은 `script = "none"`, coclass 없는 등록 요구 사항이 있음을 나타냅니다.

## <a name="remarks"></a>설명

합니다 **registration_script** c + + 특성으로 지정 된 사용자 지정 등록 스크립트 실행 *스크립트*합니다. 이 특성은 지정 하지 않으면 표준.rgs 파일 (구성 요소를 등록 하는 것에 대 한 정보 포함)이 사용 됩니다. .Rgs 파일에 대 한 자세한 내용은 참조 하세요. [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.

이 특성을 사용 하려면 합니다 [coclass](coclass.md)를 [progid](progid.md), 또는 [vi_progid](vi-progid.md) 특성 (또는 다음 중 하나를 암시 하는 다른 특성)도 적용할 같은 요소입니다.

## <a name="example"></a>예제

다음 코드는 구성 요소 cpp_attr_ref_registration_script.rgs 라는 레지스트리 스크립트를 갖도록 지정 합니다.

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
|**필수 특성**|다음 중 하나 이상의: `coclass`, `progid`, 또는 `vi_progid`합니다.|
|**잘못된 특성**|없음|

특성 컨텍스트에 대 한 자세한 내용은 참조 하세요. [특성 컨텍스트](cpp-attributes-com-net.md#contexts)합니다.

## <a name="see-also"></a>참고 항목

[COM 특성](com-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[rdx](rdx.md)  