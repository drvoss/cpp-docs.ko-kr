---
title: ATL_DRAWINFO 구조체
ms.date: 11/04/2016
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
ms.openlocfilehash: fb50f49d387e8620f3d5bbb41263738adbd8b437
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748798"
---
# <a name="atl_drawinfo-structure"></a>ATL_DRAWINFO 구조체

프린터, 메타파일 또는 ActiveX 컨트롤과 같은 다양한 대상에 렌더링하는 데 사용되는 정보를 포함합니다.

## <a name="syntax"></a>구문

```
struct ATL_DRAWINFO {
    UINT cbSize;
    DWORD dwDrawAspect;
    LONG lindex;
    DVTARGETDEVICE* ptd;
    HDC hicTargetDev;
    HDC hdcDraw;
    LPCRECTL prcBounds;
    LPCRECTL prcWBounds;
    BOOL bOptimize;
    BOOL bZoomed;
    BOOL bRectInHimetric;
    SIZEL ZoomNum;
    SIZEL ZoomDen;
};
```

## <a name="members"></a>멤버

`cbSize`<br/>
바이트로 구조의 크기입니다.

`dwDrawAspect`<br/>
대상을 나타내는 방법을 지정합니다. 표현에는 콘텐츠, 아이콘, 축소판 그림 또는 인쇄된 문서가 포함될 수 있습니다. 가능한 값 목록은 [DVASPECT](/windows/win32/api/wtypes/ne-wtypes-dvaspect) 및 [DVASPECT2를](/windows/win32/api/ocidl/ne-ocidl-dvaspect2)참조하십시오.

`lindex`<br/>
그리기 작업에 관심 있는 대상의 일부입니다. 해석은 `dwDrawAspect` 멤버의 값에 따라 다릅니다.

`ptd`<br/>
지정된 측면에 따라 그리기 최적화를 가능하게 하는 [DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) 구조에 대한 포인터입니다. 최적화된 도면 인터페이스를 지원하는 최신 객체 및 컨테이너도 이 멤버를 지원합니다. 최적화된 도면 인터페이스를 지원하지 않는 이전 객체 및 컨테이너는 항상 이 멤버에 대해 NULL을 지정합니다.

`hicTargetDev`<br/>
개체가 장치 메트릭을 추출하고 장치의 기능을 테스트할 수 있는 대상 `ptd` 장치에 대한 정보 컨텍스트입니다. NULL인 경우 `ptd` 개체는 `hicTargetDev` 멤버의 값을 무시해야 합니다.

`hdcDraw`<br/>
그릴 장치 컨텍스트입니다. 창 없는 개체의 `hdcDraw` 경우 멤버는 `MM_TEXT` 포함된 창의 클라이언트 좌표와 일치하는 논리적 좌표가 있는 매핑 모드에 있습니다. 또한 장치 컨텍스트는 일반적으로 `WM_PAINT` 메시지에 의해 전달된 컨텍스트와 동일한 상태여야 합니다.

`prcBounds`<br/>
개체를 그릴 `hdcDraw`및 사각형을 지정하는 [RECTL](/windows/win32/api/windef/ns-windef-rectl) 구조체에 대한 포인터입니다. 이 멤버는 오브젝트의 위치 지정 및 스트레칭을 제어합니다. 이 멤버는 NULL이어야 창없는 활성 개체를 그립니다. 다른 모든 상황에서 NULL은 법적 가치가 아니며 `E_INVALIDARG` 오류 코드가 발생해야 합니다. 컨테이너가 NULL이 아닌 값을 창 없는 개체에 전달하는 경우 개체는 요청된 측면을 지정된 장치 컨텍스트 및 사각형으로 렌더링해야 합니다. 컨테이너는 창없는 오브젝트에서 이 것을 요청하여 개체의 두 번째 비활성 뷰를 렌더링하거나 개체를 인쇄할 수 있습니다.

`prcWBounds`<br/>
메타파일 장치 컨텍스트인 경우(Windows `hdcDraw` SDK의 [GetDeviceCaps](/windows/win32/api/wingdi/nf-wingdi-getdevicecaps) 참조) 기본 `RECTL` 메타파일에서 경계 사각형을 지정하는 구조에 대한 포인터입니다. 사각형 구조에는 창 범위 및 창 원본이 포함됩니다. 이러한 값은 메타파일을 그리는 데 유용합니다. 표시된 `prcBounds` 사각형은 이 `prcWBounds` 사각형 내부에 중첩됩니다. 동일한 좌표 공간에 있습니다.

`bOptimize`<br/>
컨트롤의 도면을 최적화할 경우 0이 아닌 0입니다. 도면이 최적화되면 렌더링이 완료되면 장치 컨텍스트의 상태가 자동으로 복원됩니다.

`bZoomed`<br/>
대상에 확대/축소 계수가 있는 경우 0이 아닙니다. 확대/축소 계수는 `ZoomNum`에 저장됩니다.

`bRectInHimetric`<br/>
비영의 차원이 `prcBounds` HIMETRIC에 있는 경우, 그렇지 않으면 0입니다.

`ZoomNum`<br/>
오브젝트가 렌더링되는 사각형의 너비및 높이입니다. 대상의 x축을 따라 확대/축소 계수(개체의 자연 크기에서 현재 범위까지의 `ZoomNum.cx` 비율)는 `ZoomDen.cx`값으로 나눈 값입니다. y축을 따라 확대/축소 계수가 비슷한 방식으로 달성됩니다.

`ZoomDen`<br/>
대상의 실제 너비와 높이입니다.

## <a name="remarks"></a>설명

이 구조의 일반적인 사용은 대상 개체를 렌더링하는 동안 정보를 검색하는 것입니다. 예를 들어 [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced)의 오버로드 내의 ATL_DRAWINFO 값을 검색할 수 있습니다.

이 구조는 대상 장치에 대한 개체의 모양을 렌더링하는 데 사용되는 관련 정보를 저장합니다. 제공된 정보는 화면, 프린터 또는 메타파일로 그리는 데 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="see-also"></a>참조

[클래스 및 구조체](../../atl/reference/atl-classes.md)<br/>
[IViewObject::Draw](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw)<br/>
[CComControlBase::온드로우어드](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)
