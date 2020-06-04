---
title: 개체 상태 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: 5617ce7fb972c98775072f72244f91052d41ece3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326173"
---
# <a name="object-status-macros"></a>개체 상태 매크로

이 매크로는 ActiveX 컨트롤에 속하는 플래그를 설정합니다.

|||
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|올레미스C 플래그를 설정하는 ATL ActiveX 컨트롤에 사용됩니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="declare_olemisc_status"></a><a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS

올레미스C 플래그를 설정하는 ATL ActiveX 컨트롤에 사용됩니다.

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>매개 변수

*잘못된 상태*<br/>
모든 적용 가능한 OLEMISC 플래그입니다.

### <a name="remarks"></a>설명

이 매크로는 ActiveX 컨트롤에 대한 OLEMISC 플래그를 설정하는 데 사용됩니다. 자세한 내용은 [IOleObject::GetMiscStatus를](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
