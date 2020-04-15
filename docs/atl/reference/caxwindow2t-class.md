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
ms.openlocfilehash: 14080b624132979df533135bc1eef108dc793398
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318693"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T 클래스

이 클래스는 ActiveX 컨트롤을 호스트하는 창을 조작하는 메서드를 제공하며 라이센스가 부여된 ActiveX 컨트롤을 호스팅하는 데도 지원합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>매개 변수

*TBase*<br/>
파생되는 `CAxWindowT` 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|`CAxWindow2T` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAxWindow2T::만들기](#create)|호스트 창을 만듭니다.|
|[CAxWindow2T::컨트롤릭 만들기](#createcontrollic)|사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|
|[CAxWindow2T::만들기제어](#createcontrollicex)|라이센스가 부여된 ActiveX 컨트롤을 만들고, 초기화하고, 지정된 창에서 호스트하고, 컨트롤에서 인터페이스 포인터(또는 포인터)를 검색합니다.|
|[CAxWindow2T::GetWndClassName](#getwndclassname)|창 클래스의 이름을 검색 하는 정적 메서드입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAxWindow2T::연산자 =](#operator_eq)|기존 `CAxWindow2T` 개체에 HWND를 할당합니다.|

## <a name="remarks"></a>설명

`CAxWindow2T`에서는 ActiveX 컨트롤을 호스트하는 창을 조작하는 메서드를 제공합니다. `CAxWindow2T`또한 라이센스ActiveX 컨트롤을 호스팅하는 데 에도 사용할 수 있습니다. 호스팅은 에 의해 포장되는 **"AtlAxWinLic80** `CAxWindow2T`"에 의해 제공됩니다.

클래스는 `CAxWindow2` `CAxWindow2T` 클래스의 전문화로 구현됩니다. 이 전문화는 다음과 같이 선언됩니다.

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT`멤버는 [CAxWindow](../../atl/reference/caxwindow-class.md)에서 문서화됩니다.

이 클래스의 멤버를 사용하는 샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="caxwindow2tcaxwindow2t"></a><a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T

`CAxWindow2T` 개체를 생성합니다.

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
기존 창의 핸들입니다.

## <a name="caxwindow2tcreate"></a><a name="create"></a>CAxWindow2T::만들기

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

`CAxWindow2T::Create`[CWindow::제어](../../atl/reference/cwindow-class.md#create) 호스팅 ()을`AtlAxWinLic80`제공하는 창 클래스로 설정된 LPCTSTR *lpstrWndClass* 매개 변수로 만듭니다.

매개 `CWindow::Create` 변수 및 반환 값에 대한 설명은 을 참조하십시오.

**참고 사항** 0이 *MenuOrID* 매개 변수의 값으로 사용되는 경우 컴파일러 오류를 방지하려면 0U(기본값)로 지정해야 합니다.

### <a name="example"></a>예제

을 사용하는 `CAxWindow2T::Create`샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="caxwindow2tcreatecontrollic"></a><a name="createcontrollic"></a>CAxWindow2T::컨트롤릭 만들기

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

*블스트릭키*<br/>
컨트롤에 대한 라이센스 키; 라이선스가 없는 컨트롤을 만드는 경우 NULL입니다.

### <a name="remarks"></a>설명

나머지 매개 변수 및 반환 값에 대한 설명은 [CAxWindow::CreateControl을](../../atl/reference/caxwindow-class.md#createcontrol) 참조하십시오.

### <a name="example"></a>예제

을 사용하는 `CAxWindow2T::CreateControlLic`샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="caxwindow2tcreatecontrollicex"></a><a name="createcontrollicex"></a>CAxWindow2T::만들기제어

라이센스가 부여된 ActiveX 컨트롤을 만들고, 초기화하고, 지정된 창에서 호스트하고, 컨트롤에서 인터페이스 포인터(또는 포인터)를 검색합니다.

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

*블스트릭키*<br/>
컨트롤에 대한 라이센스 키; 라이선스가 없는 컨트롤을 만드는 경우 NULL입니다.

### <a name="remarks"></a>설명

나머지 매개 변수 및 반환 값에 대한 설명은 [CAxWindow::CreateControlEx를](../../atl/reference/caxwindow-class.md#createcontrolex) 참조하십시오.

### <a name="example"></a>예제

을 사용하는 `CAxWindow2T::CreateControlLicEx`샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="caxwindow2tgetwndclassname"></a><a name="getwndclassname"></a>CAxWindow2T::GetWndClassName

창 클래스의 이름을 검색합니다.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Return Value

라이센스가 부여되고 라이선스가 부여되지 않은`AtlAxWinLic80`ActiveX 컨트롤을 호스트할 수 있는 window 클래스() 이름이 포함된 문자열에 대한 포인터입니다.

## <a name="caxwindow2toperator-"></a><a name="operator_eq"></a>CAxWindow2T::연산자 =

기존 `CAxWindow2T` 개체에 HWND를 할당합니다.

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
기존 창의 핸들입니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md)
