---
title: 아이올레인플레이스액티브오브젝트임플 클래스
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
ms.openlocfilehash: b39ba2845a5483444dac53d1616654e902969c77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326594"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>아이올레인플레이스액티브오브젝트임플 클래스

이 클래스는 내부 컨트롤과 해당 컨테이너 간의 통신을 지원하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IOleInPlaceActiveObjectImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IOleInPlace액티브오브젝트임플::컨텍스트민감성 도움말](#contextsensitivehelp)|상황에 맞는 도움말을 활성화합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[아이올레인플레이스액티브오브젝트임플::인에이블모드리스](#enablemodeless)|모덜리스 대화 상자를 활성화합니다. ATL 구현은 S_OK 반환합니다.|
|[아이올레인플레이스액티브오브젝트임플::겟윈도우](#getwindow)|창 핸들을 가져옵니다.|
|[아이올레인플레이스액티브오브젝트임플::온닥윈도우활성화](#ondocwindowactivate)|컨테이너의 문서 창이 활성화되거나 비활성화될 때 컨트롤에 대해 설명합니다. ATL 구현은 S_OK 반환합니다.|
|[IOleInPlace액티브오브젝트임플::온프레임윈도우활성화](#onframewindowactivate)|컨테이너의 최상위 프레임 창이 활성화되거나 비활성화될 때 컨트롤에 알립니다. ATL 구현은|
|[아이올레인플레이스액티브오브젝트임플::축소보더](#resizeborder)|테두리 크기를 조정하는 데 필요한 컨트롤을 알립니다. ATL 구현은 S_OK 반환합니다.|
|[아이올레인플레이스액티브오브젝트임플::번역가속기](#translateaccelerator)|컨테이너에서 메뉴 가속기 키 메시지를 처리합니다. ATL 구현은 E_NOTIMPL 반환합니다.|

## <a name="remarks"></a>설명

[IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) 인터페이스는 내부 제어와 컨테이너 간의 통신을 지원합니다. 예를 들어 컨트롤 및 컨테이너의 활성 상태를 통신하고 자체 크기를 조정해야 하는 컨트롤을 알려줍니다. 클래스는 `IOleInPlaceActiveObjectImpl` 디버그 `IOleInPlaceActiveObject` 빌드에서 `IUnknown` 덤프 장치에 정보를 전송하여 기본 구현 및 지원을 제공합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="ioleinplaceactiveobjectimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a>IOleInPlace액티브오브젝트임플::컨텍스트민감성 도움말

상황에 맞는 도움말을 활성화합니다.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IOleWindow::컨텍스트민감성](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) Windows SDK의 도움말을 참조하십시오.

## <a name="ioleinplaceactiveobjectimplenablemodeless"></a><a name="enablemodeless"></a>아이올레인플레이스액티브오브젝트임플::인에이블모드리스

모덜리스 대화 상자를 활성화합니다.

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IOleInPlaceActiveObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) SDK에서 사용 모드가 없습니다.

## <a name="ioleinplaceactiveobjectimplgetwindow"></a><a name="getwindow"></a>아이올레인플레이스액티브오브젝트임플::겟윈도우

컨테이너는 컨트롤의 창 핸들을 얻기 위해 이 함수를 호출합니다.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>설명

일부 컨테이너는 현재 창이 있는 경우에도 창이 없는 컨트롤로 작동하지 않습니다. ATL 구현에서 데이터 멤버가 `CComControl::m_bWasOnceWindowless` TRUE이면 함수가 E_FAIL 반환합니다. 그렇지 않으면 \* *phwnd가* NULL이 `GetWindow` 아닌 경우 컨트롤 클래스의 데이터 멤버에 `m_hWnd` *phwnd를* 할당하고 S_OK 반환합니다.

[IOleWindow::GetWindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) 윈도우 SDK에서.

## <a name="ioleinplaceactiveobjectimplondocwindowactivate"></a><a name="ondocwindowactivate"></a>아이올레인플레이스액티브오브젝트임플::온닥윈도우활성화

컨테이너의 문서 창이 활성화되거나 비활성화될 때 컨트롤에 대해 설명합니다.

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IOleInPlaceActiveObject::OnDocWindow](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) Windows SDK에서 활성화를 참조하십시오.

## <a name="ioleinplaceactiveobjectimplonframewindowactivate"></a><a name="onframewindowactivate"></a>IOleInPlace액티브오브젝트임플::온프레임윈도우활성화

컨테이너의 최상위 프레임 창이 활성화되거나 비활성화될 때 컨트롤에 알립니다.

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IOleInPlaceActiveObject::OnFrameWindow](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) Windows SDK에서 활성화를 참조하십시오.

## <a name="ioleinplaceactiveobjectimplresizeborder"></a><a name="resizeborder"></a>아이올레인플레이스액티브오브젝트임플::축소보더

테두리 크기를 조정하는 데 필요한 컨트롤을 알립니다.

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IOleInPlaceActiveObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) SDK에서 경계 조정을 참조하십시오.

## <a name="ioleinplaceactiveobjectimpltranslateaccelerator"></a><a name="translateaccelerator"></a>아이올레인플레이스액티브오브젝트임플::번역가속기

컨테이너에서 메뉴 가속기 키 메시지를 처리합니다.

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>Return Value

이 메서드는 다음 반환 값을 지원합니다.

메시지가 성공적으로 번역되었는지 S_OK.

메시지가 번역되지 않은 경우 S_FALSE.

### <a name="remarks"></a>설명

[IOleInPlaceActive개체::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) SDK의 번역가속기를 참조하십시오.

## <a name="see-also"></a>참고 항목

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[액티브X컨트롤 인터페이스](/windows/win32/com/activex-controls-interfaces)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
