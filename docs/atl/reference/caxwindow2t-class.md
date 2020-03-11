---
title: CAxWindow2T 클래스
ms.date: 11/04/2016
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
ms.openlocfilehash: 0d5991dcbf79d1c2415594636a09908586d1dc2f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864748"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T 클래스

이 클래스는 ActiveX 컨트롤을 호스트 하는 창을 조작 하기 위한 메서드를 제공 하 고 사용이 허가 된 ActiveX 컨트롤을 호스팅하기 위한 지원도 제공 합니다.

> [!IMPORTANT]
>  이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>매개 변수

*TBase*<br/>
`CAxWindowT` 파생 되는 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|`CAxWindow2T` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[CAxWindow2T:: Create](#create)|호스트 창을 만듭니다.|
|[CAxWindow2T::CreateControlLic](#createcontrollic)|사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|사용이 허가 된 ActiveX 컨트롤을 만들고 초기화 하 여 지정 된 창에 호스팅하고 컨트롤에서 인터페이스 포인터 (또는 포인터)를 검색 합니다.|
|[CAxWindow2T::GetWndClassName](#getwndclassname)|창 클래스의 이름을 검색 하는 정적 메서드입니다.|

### <a name="public-operators"></a>Public 연산자

|name|설명|
|----------|-----------------|
|[CAxWindow2T:: operator =](#operator_eq)|기존 `CAxWindow2T` 개체에 HWND를 할당 합니다.|

## <a name="remarks"></a>설명

`CAxWindow2T`는 ActiveX 컨트롤을 호스트 하는 창을 조작 하는 메서드를 제공 합니다. 또한 `CAxWindow2T`에는 사용이 허가 된 ActiveX 컨트롤 호스팅을 지원 합니다. 호스트는 `CAxWindow2T`로 래핑된 " **AtlAxWinLic80**"에서 제공 됩니다.

클래스 `CAxWindow2`은 `CAxWindow2T` 클래스의 특수화로 구현 됩니다. 이 특수화는 다음과 같이 선언 됩니다.

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT` 멤버는 [Caxwindow](../../atl/reference/caxwindow-class.md)에 문서화 됩니다.

이 클래스의 멤버를 사용 하는 샘플은 [ATL AXHost를 사용 하 여 ActiveX 컨트롤 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 을 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>요구 사항

**헤더:.**

##  <a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T

`CAxWindow2T` 개체를 생성합니다.

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
기존 창의 핸들입니다.

##  <a name="create"></a>CAxWindow2T:: Create

호스트 창을 만듭니다.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="remarks"></a>설명

`CAxWindow2T::Create`는 LPCTSTR *lpstrWndClass* 매개 변수를 컨트롤 호스팅 (`AtlAxWinLic80`)을 제공 하는 window 클래스로 설정 하 여 [CWindow:: Create](../../atl/reference/cwindow-class.md#create) 를 호출 합니다.

매개 변수 및 반환 값에 대 한 설명은 `CWindow::Create`를 참조 하세요.

**참고** *MenuOrID* 매개 변수에 대 한 값으로 0을 사용 하는 경우 컴파일러 오류를 방지 하려면 해당 값을 0u (기본값)로 지정 해야 합니다.

### <a name="example"></a>예제

`CAxWindow2T::Create`를 사용 하는 샘플은 [ATL AXHost를 사용 하 여 ActiveX 컨트롤 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 을 참조 하세요.

##  <a name="createcontrollic"></a>CAxWindow2T::CreateControlLic

사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.

```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>매개 변수

*bstrLicKey*<br/>
컨트롤의 라이선스 키입니다. 사용이 허가 되지 않은 컨트롤을 만드는 경우 NULL입니다.

### <a name="remarks"></a>설명

나머지 매개 변수 및 반환 값에 대 한 설명은 [Caxwindow:: CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) 을 참조 하세요.

### <a name="example"></a>예제

`CAxWindow2T::CreateControlLic`를 사용 하는 샘플은 [ATL AXHost를 사용 하 여 ActiveX 컨트롤 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 을 참조 하세요.

##  <a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx

사용이 허가 된 ActiveX 컨트롤을 만들고 초기화 하 여 지정 된 창에 호스팅하고 컨트롤에서 인터페이스 포인터 (또는 포인터)를 검색 합니다.

```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```

### <a name="parameters"></a>매개 변수

*bstrLicKey*<br/>
컨트롤의 라이선스 키입니다. 사용이 허가 되지 않은 컨트롤을 만드는 경우 NULL입니다.

### <a name="remarks"></a>설명

나머지 매개 변수 및 반환 값에 대 한 설명은 [Caxwindow:: CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) 를 참조 하세요.

### <a name="example"></a>예제

`CAxWindow2T::CreateControlLicEx`를 사용 하는 샘플은 [ATL AXHost를 사용 하 여 ActiveX 컨트롤 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 을 참조 하세요.

##  <a name="getwndclassname"></a>CAxWindow2T::GetWndClassName

창 클래스의 이름을 검색 합니다.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>반환 값

사용이 허가 되거나 허가 되지 않은 ActiveX 컨트롤을 호스팅할 수 있는 창 클래스 (`AtlAxWinLic80`)의 이름을 포함 하는 문자열에 대 한 포인터입니다.

##  <a name="operator_eq"></a>CAxWindow2T:: operator =

기존 `CAxWindow2T` 개체에 HWND를 할당 합니다.

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
기존 창의 핸들입니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md)
