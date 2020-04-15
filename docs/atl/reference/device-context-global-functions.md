---
title: 디바이스 컨텍스트 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: e640f310a1976c29a39f0ab7c2575dfd1073c889
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330147"
---
# <a name="device-context-global-functions"></a>디바이스 컨텍스트 전역 함수

이 함수는 지정된 장치에 대한 장치 컨텍스트를 만듭니다.

|||
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|장치 컨텍스트를 만듭니다.|

## <a name="atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a>아틀창조타겟DC

[DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) 구조에 지정된 장치에 대한 장치 컨텍스트를 만듭니다.

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>매개 변수

*Hdc*<br/>
【인】 장치 컨텍스트 또는 NULL의 기존 핸들입니다.

*ptd*<br/>
【인】 대상 장치에 `DVTARGETDEVICE` 대한 정보가 포함된 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

에 지정된 장치의 장치 컨텍스트에 핸들을 `DVTARGETDEVICE`반환합니다. 장치를 지정하지 않으면 핸들을 기본 표시 장치로 반환합니다.

### <a name="remarks"></a>설명

구조가 NULL이고 *HDC가* NULL인 경우 기본 표시 장치에 대한 장치 컨텍스트를 만듭니다.

*HDC가* NULL이 아니고 *PTD가* NULL이면 함수가 기존 *HDC를*반환합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)
