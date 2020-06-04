---
title: IAxWinHost윈도우인터페이스
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: 561a65702f1d4f57b4db1afc75769ce4cc523c1c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329916"
---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHost윈도우인터페이스

이 인터페이스는 사용이 허가된 컨트롤 및 해당 호스트 개체를 조작하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[컨트롤릭 만들기](#createcontrollic)|라이선스가 부여된 컨트롤을 만들고 호스트 개체에 연결합니다.|
|[만들기제어LicEx](#createcontrollicex)|사용이 허가된 컨트롤을 만들고 호스트 개체에 연결하고 선택적으로 이벤트 처리기를 설정합니다.|

## <a name="remarks"></a>설명

`IAxWinHostWindowLic`[은 IAxWinHostWindow에서](../../atl/reference/iaxwinhostwindow-interface.md) 상속되며 라이센스가 부여된 컨트롤 생성을 지원하는 메서드를 추가합니다.

이 인터페이스의 멤버를 사용하는 샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="requirements"></a>요구 사항

이 인터페이스의 정의는 아래와 같이 IDL 또는 C++로 사용할 수 있습니다.

|정의 유형|파일|
|---------------------|----------|
|Idl|아틀리페이스.아이들|
|C++|ATLIFace.h (ATLBase.h에도 포함)|

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a>IAxWinHost윈도우릭::컨트롤릭 만들기

라이센스가 부여된 컨트롤을 만들고 초기화하며 `hWnd`로 식별된 창에서 호스트합니다.

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>매개 변수

*블스트릭*<br/>
【인】 컨트롤에 대한 라이센스 키가 포함된 BSTR입니다.

### <a name="remarks"></a>설명

나머지 매개 변수 및 반환 값에 대한 설명은 [IAxWinHostWindow::CreateControl을](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) 참조하십시오.

이 메서드를 호출하는 것은 [IAxWinHostWindowLic::CreateControlLicEx를](#createcontrollicex) 호출하는 것과 같습니다.

### <a name="example"></a>예제

을 사용하는 `IAxWinHostWindowLic::CreateControlLic`샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a>IAxWinHost윈도우릭::만들기제어

라이선스가 부여된 ActiveX 컨트롤을 만들고, 초기화하고, [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)과 유사한 지정된 창에서 호스트합니다.

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>매개 변수

*블스트릭*<br/>
【인】 컨트롤에 대한 라이센스 키가 포함된 BSTR입니다.

### <a name="remarks"></a>설명

나머지 매개 변수 및 반환 값에 대한 설명은 [IAxWinHostWindow::CreateControlEx를](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) 참조하십시오.

### <a name="example"></a>예제

을 사용하는 `IAxWinHostWindowLic::CreateControlLicEx`샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.
