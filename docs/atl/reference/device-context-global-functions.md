---
title: 장치 컨텍스트 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: d2d25660083f074683a3f42f878497ce14a008b8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833467"
---
# <a name="device-context-global-functions"></a>장치 컨텍스트 전역 함수

이 함수는 지정 된 장치에 대 한 장치 컨텍스트를 만듭니다.

|Name|설명|
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|장치 컨텍스트를 만듭니다.|

## <a name="atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a> AtlCreateTargetDC

[DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) 구조체에 지정 된 장치에 대 한 장치 컨텍스트를 만듭니다.

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>매개 변수

*hdc*<br/>
진행 장치 컨텍스트의 기존 핸들 또는 NULL입니다.

*ptd*<br/>
진행 `DVTARGETDEVICE` 대상 장치에 대 한 정보를 포함 하는 구조에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

에 지정 된 장치에 대 한 장치 컨텍스트에 대 한 핸들을 반환 합니다 `DVTARGETDEVICE` . 장치를 지정 하지 않은 경우 기본 디스플레이 장치에 대 한 핸들을 반환 합니다.

### <a name="remarks"></a>설명

구조가 NULL이 고 *hdc* 가 null 이면는 기본 디스플레이 장치에 대 한 장치 컨텍스트를 만듭니다.

*Hdc* 가 null이 아니고 *ptd* 가 null 인 경우 함수는 기존 *hdc*를 반환 합니다.

## <a name="requirements"></a>요구 사항

**헤더:.**

## <a name="see-also"></a>참조

[함수](../../atl/reference/atl-functions.md)
