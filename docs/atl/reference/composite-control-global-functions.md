---
title: 복합 제어 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlhost/ATL::AtlAxDialogBox
- atlhost/ATL::AtlAxCreateDialog
- atlhost/ATL::AtlAxCreateControl
- atlhost/ATL::AtlAxCreateControlEx
- atlhost/ATL::AtlAxCreateControlLic
- atlhost/ATL::AtlAxCreateControlLicEx
- atlhost/ATL::AtlAxAttachControl
- atlhost/ATL::AtlAxGetHost
- atlhost/ATL::AtlAxGetControl
- atlhost/ATL::AtlSetChildSite
- atlhost/ATL::AtlAxWinInit
- atlhost/ATL::AtlAxWinTerm
- atlhost/ATL::AtlGetObjectSourceInterface
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
ms.openlocfilehash: 99ecd4cf04b3eb696f897d6ef5a5e3839d46ef17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331607"
---
# <a name="composite-control-global-functions"></a>복합 제어 전역 함수

이러한 기능은 대화 상자를 만들고 ActiveX 컨트롤을 생성, 호스팅 및 라이센싱하는 데 대한 지원을 제공합니다.

> [!IMPORTANT]
> 다음 표에 나열된 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|사용자가 제공한 대화 상자 템플릿에서 모달 대화 상자를 만듭니다. 결과 대화 상자에ActiveX 컨트롤이 포함될 수 있습니다.|
|[AtlAxCreateDialog](#atlaxcreatedialog)|사용자가 제공한 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다. 결과 대화 상자에ActiveX 컨트롤이 포함될 수 있습니다.|
|[AtlAxCreateControl](#atlaxcreatecontrol)|ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|ActiveX 컨트롤을 만들고, 초기화하고, 지정된 창에서 호스트하고, 컨트롤에서 인터페이스 포인터(또는 포인터)를 검색합니다.|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|라이센스가 부여된 ActiveX 컨트롤을 만들고, 초기화하고, 지정된 창에서 호스트하고, 컨트롤에서 인터페이스 포인터(또는 포인터)를 검색합니다.|
|[AtlAxAttachControl](#atlaxattachcontrol)|지정한 창에 이전에 만든 컨트롤을 연결합니다.|
|[AtlAxGetHost](#atlaxgethost)|지정된 창(있는 경우)에 대해 컨테이너에 대한 직접 인터페이스 포인터를 가져오는 데 사용됩니다.|
|[AtlAxGetControl](#atlaxgetcontrol)|지정된 창(있는 경우)에 포함된 컨트롤에 대한 직접 인터페이스 포인터를 가져오는 데 사용됩니다.|
|[AtlSetChildSite](#atlsetchildsite)|자식 사이트의 `IUnknown` 초기화합니다.|
|[AtlAxWinInit](#atlaxwininit)|AxWin 개체에 대한 호스팅 코드를 초기화합니다.|
|[AtlAxWinTerm](#atlaxwinterm)|AxWin 개체에 대한 호스팅 코드를 초기화하지 않습니다.|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|개체의 기본 소스 인터페이스에 대한 정보를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlhost.h

## <a name="atlaxdialogbox"></a><a name="atlaxdialogbox"></a>아틀락스디아로그박스

사용자가 제공한 대화 상자 템플릿에서 모달 대화 상자를 만듭니다.

```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
【인】 실행 파일이 대화 상자 템플릿을 포함하는 모듈의 인스턴스를 식별합니다.

*lp템플릿 이름*<br/>
【인】 대화 상자 템플릿을 식별합니다. 이 매개 변수는 대화 상자 템플릿의 이름을 지정하는 null-terminated 문자 문자열에 대한 포인터 또는 대화 상자 템플릿의 리소스 식별자를 지정하는 정수 값입니다. 매개 변수가 리소스 식별자를 지정하는 경우 해당 고차 단어는 0이어야 하며 하위 순서 단어는 식별자를 포함해야 합니다. [MAKEINTRESOURCE](/windows/win32/api/winuser/nf-winuser-makeintresourcew) 매크로를 사용하여 이 값을 만들 수 있습니다.

*hWnd부모*<br/>
【인】 대화 상자를 소유하는 창을 식별합니다.

*lpDialogProc*<br/>
【인】 대화 상자 절차를 가리킵니다. 대화 상자 절차에 대한 자세한 내용은 [대화 상자](/windows/win32/api/winuser/nc-winuser-dlgproc)를 참조하십시오.

*dwInitParam*<br/>
【인】 WM_INITDIALOG 메시지의 *lParam* 매개 변수에서 대화 상자에 전달할 값을 지정합니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

ActiveX `AtlAxDialogBox` 컨트롤이 포함된 대화 상자 템플릿과 함께 사용하려면 유효한 CLSID, APPID 또는 URL 문자열을 대화 상자 리소스의 **CONTROL** 섹션의 *텍스트* 필드로 지정하고 동일한 섹션아래의 *클래스 이름* 필드로 "AtlAxWin80"을 지정합니다. 다음은 유효한 **CONTROL** 섹션의 모양을 보여 줍니다.

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

리소스 스크립트 편집에 대한 자세한 내용은 [텍스트 형식의 리소스 스크립트 파일 열기 방법을](../../windows/how-to-open-a-resource-script-file-in-text-format.md)참조하십시오. 리소스 정의 명령문 제어에 대한 자세한 내용은 Windows SDK: SDK 도구에서 [일반적인 제어 매개 변수를](/windows/win32/menurc/common-control-parameters) 참조하십시오.

일반적으로 대화 상자에 대한 자세한 내용은 Windows SDK의 [대화 상자](/windows/win32/api/winuser/nf-winuser-dialogboxw) 및 [CreateDialogParam을](/windows/win32/api/winuser/nf-winuser-createdialogparamw) 참조하십시오.

## <a name="atlaxcreatedialog"></a><a name="atlaxcreatedialog"></a>아틀락스창조디아로그

사용자가 제공한 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다.

```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
【인】 실행 파일이 대화 상자 템플릿을 포함하는 모듈의 인스턴스를 식별합니다.

*lp템플릿 이름*<br/>
【인】 대화 상자 템플릿을 식별합니다. 이 매개 변수는 대화 상자 템플릿의 이름을 지정하는 null-terminated 문자 문자열에 대한 포인터 또는 대화 상자 템플릿의 리소스 식별자를 지정하는 정수 값입니다. 매개 변수가 리소스 식별자를 지정하는 경우 해당 고차 단어는 0이어야 하며 하위 순서 단어는 식별자를 포함해야 합니다. [MAKEINTRESOURCE](/windows/win32/api/winuser/nf-winuser-makeintresourcew) 매크로를 사용하여 이 값을 만들 수 있습니다.

*hWnd부모*<br/>
【인】 대화 상자를 소유하는 창을 식별합니다.

*lpDialogProc*<br/>
【인】 대화 상자 절차를 가리킵니다. 대화 상자 절차에 대한 자세한 내용은 [대화 상자](/windows/win32/api/winuser/nc-winuser-dlgproc)를 참조하십시오.

*dwInitParam*<br/>
【인】 WM_INITDIALOG 메시지의 *lParam* 매개 변수에서 대화 상자에 전달할 값을 지정합니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

결과 대화 상자에ActiveX 컨트롤이 포함될 수 있습니다.

윈도우 SDK에서 [만들기디아로그](/windows/win32/api/winuser/nf-winuser-createdialogw) 및 [CreateDialogParam을](/windows/win32/api/winuser/nf-winuser-createdialogparamw) 참조하십시오.

## <a name="atlaxcreatecontrol"></a><a name="atlaxcreatecontrol"></a>아틀락스만들기제어

ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
컨트롤에 전달할 문자열에 대한 포인터입니다. 다음 방법 중 하나로 서식을 지정해야 합니다.

- 같은 ProgID`"MSCAL.Calendar.7"`

- CLSID 와 같은`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 다음과 같은 URL`"<https://www.microsoft.com>"`

- 활성 문서에 대한 참조와 같은`"file://\\\Documents\MyDoc.doc"`

- 와 같은 HTML 의 조각`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML 스트림으로 지정되도록 HTML 조각 앞에 와야 합니다.

*Hwnd*<br/>
【인】 컨트롤이 연결될 창에 핸들을 보입니다.

*pStream*<br/>
【인】 컨트롤의 속성을 초기화하는 데 사용되는 스트림에 대한 포인터입니다. NULL일 수 있습니다.

*ppUnk컨테이너*<br/>
【아웃】 컨테이너를 수신할 `IUnknown` 포인터의 주소입니다. NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

이 전역 함수는 [AtlAxCreateControlEx](#atlaxcreatecontrolex)*(lpszName*, *hWnd*, *pStream,* NULL, NULL, NULL) 호출과 동일한 결과를 제공합니다.

라이선스가 부여된 ActiveX 컨트롤을 만들려면 [AtlAxCreateControlLic](#atlaxcreatecontrollic)을 참조하십시오.

## <a name="atlaxcreatecontrolex"></a><a name="atlaxcreatecontrolex"></a>아틀락스만들기제어

ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다. 새 컨트롤에 대한 인터페이스 포인터와 이벤트 싱크를 만들 수도 있습니다.

```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
컨트롤에 전달할 문자열에 대한 포인터입니다. 다음 방법 중 하나로 서식을 지정해야 합니다.

- 같은 ProgID`"MSCAL.Calendar.7"`

- CLSID 와 같은`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 다음과 같은 URL`"<https://www.microsoft.com>"`

- 활성 문서에 대한 참조와 같은`"file://\\\Documents\MyDoc.doc"`

- 와 같은 HTML 의 조각`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML 스트림으로 지정되도록 HTML 조각 앞에 와야 합니다.

*Hwnd*<br/>
【인】 컨트롤이 연결될 창에 핸들을 보입니다.

*pStream*<br/>
【인】 컨트롤의 속성을 초기화하는 데 사용되는 스트림에 대한 포인터입니다. NULL일 수 있습니다.

*ppUnk컨테이너*<br/>
【아웃】 컨테이너를 수신할 `IUnknown` 포인터의 주소입니다. NULL일 수 있습니다.

*ppUnk제어*<br/>
【아웃】 생성된 컨트롤을 수신할 `IUnknown` 포인터의 주소입니다. NULL일 수 있습니다.

*아이드싱크*<br/>
포함된 개체에 나가는 인터페이스의 인터페이스 식별자입니다.

*펑크 싱크*<br/>
포함된 개체가 `IUnknown` 성공적으로 생성된 후 포함된 개체에 *iidSink가* 지정한 연결 지점에 연결할 싱크 개체의 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`AtlAxCreateControlEx`[AtlAxCreateControl과](#atlaxcreatecontrol) 유사하지만 새로 만든 컨트롤에 대한 인터페이스 포인터를 수신하고 컨트롤에서 발생된 이벤트를 수신하도록 이벤트 싱크를 설정할 수도 있습니다.

라이센스가 부여된 ActiveX 컨트롤을 만들려면 [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)를 참조하십시오.

## <a name="atlaxcreatecontrollic"></a><a name="atlaxcreatecontrollic"></a>아틀락스만들기컨트롤릭

사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
컨트롤에 전달할 문자열에 대한 포인터입니다. 다음 방법 중 하나로 서식을 지정해야 합니다.

- 같은 ProgID`"MSCAL.Calendar.7"`

- CLSID 와 같은`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 다음과 같은 URL`"<https://www.microsoft.com>"`

- 활성 문서에 대한 참조와 같은`"file://\\\Documents\MyDoc.doc"`

- 와 같은 HTML 의 조각`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML 스트림으로 지정되도록 HTML 조각 앞에 와야 합니다.

*Hwnd*<br/>
컨트롤이 연결될 창에 핸들을 보입니다.

*pStream*<br/>
컨트롤의 속성을 초기화하는 데 사용되는 스트림에 대한 포인터입니다. NULL일 수 있습니다.

*ppUnk컨테이너*<br/>
컨테이너를 수신할 `IUnknown` 포인터의 주소입니다. NULL일 수 있습니다.

*블스트릭*<br/>
컨트롤에 대한 라이선스를 포함하는 BSTR입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="example"></a>예제

사용 `AtlAxCreateControlLic`방법에 대한 샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="atlaxcreatecontrollicex"></a><a name="atlaxcreatecontrollicex"></a>아틀락스만들기컨트롤리카

사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다. 새 컨트롤에 대한 인터페이스 포인터와 이벤트 싱크를 만들 수도 있습니다.

```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
컨트롤에 전달할 문자열에 대한 포인터입니다. 다음 방법 중 하나로 서식을 지정해야 합니다.

- 같은 ProgID`"MSCAL.Calendar.7"`

- CLSID 와 같은`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 다음과 같은 URL`"<https://www.microsoft.com>"`

- 활성 문서에 대한 참조와 같은`"file://\\\Documents\MyDoc.doc"`

- 와 같은 HTML 의 조각`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML 스트림으로 지정되도록 HTML 조각 앞에 와야 합니다.

*Hwnd*<br/>
컨트롤이 연결될 창에 핸들을 보입니다.

*pStream*<br/>
컨트롤의 속성을 초기화하는 데 사용되는 스트림에 대한 포인터입니다. NULL일 수 있습니다.

*ppUnk컨테이너*<br/>
컨테이너를 수신할 `IUnknown` 포인터의 주소입니다. NULL일 수 있습니다.

*ppUnk제어*<br/>
【아웃】 생성된 컨트롤을 수신할 `IUnknown` 포인터의 주소입니다. NULL일 수 있습니다.

*아이드싱크*<br/>
포함된 개체에 나가는 인터페이스의 인터페이스 식별자입니다.

*펑크 싱크*<br/>
포함된 개체가 `IUnknown` 성공적으로 생성된 후 포함된 개체에 *iidSink가* 지정한 연결 지점에 연결할 싱크 개체의 인터페이스에 대한 포인터입니다.

*블스트릭*<br/>
컨트롤에 대한 라이선스를 포함하는 BSTR입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`AtlAxCreateControlLicEx`[AtlAxCreateControlLic과](#atlaxcreatecontrollic) 유사하지만 새로 만든 컨트롤에 대한 인터페이스 포인터를 수신하고 컨트롤에서 발생된 이벤트를 수신하도록 이벤트 싱크를 설정할 수도 있습니다.

### <a name="example"></a>예제

사용 `AtlAxCreateControlLicEx`방법에 대한 샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="atlaxattachcontrol"></a><a name="atlaxattachcontrol"></a>아틀락스어트컨트롤

지정한 창에 이전에 만든 컨트롤을 연결합니다.

```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>매개 변수

*pControl*<br/>
【인】 컨트롤의 `IUnknown` 포인터입니다.

*Hwnd*<br/>
【인】 컨트롤을 호스트하는 창에 핸들을 보입니다.

*ppUnk컨테이너*<br/>
【아웃】 컨테이너 개체에 대한 `IUnknown` 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

[AtlAxCreateControlEx](#atlaxcreatecontrolex) 및 [AtlAxCreateControl을](#atlaxcreatecontrol) 사용하여 동시에 컨트롤을 만들고 연결합니다.

> [!NOTE]
> 연결되는 컨트롤 개체를 호출하기 `AtlAxAttachControl`전에 올바르게 초기화해야 합니다.

## <a name="atlaxgethost"></a><a name="atlaxgethost"></a>아틀락스겟호스트

핸들이 제공되는 지정된 창(있는 경우)의 컨테이너에 직접 인터페이스 포인터를 가져옵니다.

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
【인】 컨트롤을 호스팅하는 창에 대한 핸들입니다.

*Pp*<br/>
【아웃】 `IUnknown` 컨트롤의 컨테이너입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="atlaxgetcontrol"></a><a name="atlaxgetcontrol"></a>아틀락스겟컨트롤

핸들이 제공되는 지정된 창 내에 포함된 컨트롤에 직접 인터페이스 포인터를 가져옵니다.

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
【인】 컨트롤을 호스팅하는 창에 대한 핸들입니다.

*Pp*<br/>
【아웃】 호스트되는 컨트롤의 입니다. `IUnknown`

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="atlsetchildsite"></a><a name="atlsetchildsite"></a>아틀셋차일드사이트

이 함수를 호출하여 자식 개체의 `IUnknown` 사이트를 상위 개체의 사이트로 설정합니다.

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>매개 변수

*펑크 차일드*<br/>
【인】 자식의 `IUnknown` 인터페이스에 대한 포인터입니다.

*펑크 부모*<br/>
【인】 부모의 인터페이스에 `IUnknown` 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="atlaxwininit"></a><a name="atlaxwininit"></a>아틀락스위니니트

이 함수는 **"AtlAxWin80"** 및 **"AtlAxWinLic80"** 창 클래스와 몇 개의 사용자 지정 창 메시지를 등록하여 ATL의 제어 호스팅 코드를 초기화합니다.

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>Return Value

비제로 제어 호스팅 코드의 초기화가 성공한 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

ATL 컨트롤 호스팅 API를 사용하기 전에 이 함수를 호출해야 합니다. 이 함수를 호출한 후 Windows SDK에 설명된 대로 [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 또는 [CreateWindowEx에](/windows/win32/api/winuser/nf-winuser-createwindowexw)대한 호출에서 **"AtlAxWin"** 창 클래스를 사용할 수 있습니다.

## <a name="atlaxwinterm"></a><a name="atlaxwinterm"></a>아틀락스윈터

이 함수는 **"AtlAxWin80" 및 "AtlAxWinLic80"** 창 클래스를 등록 취소하여 **ATL의** 제어 호스팅 코드를 초기화하지 않습니다.

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>Return Value

항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 함수는 Windows SDK에 설명된 대로 [registerClass를](/windows/win32/api/winuser/nf-winuser-unregisterclassw) 호출하기만 하면 됩니다.

[AtlAxWinInit을](#atlaxwininit) 호출하고 더 이상 호스트 창을 만들 필요가 없는 경우 기존 호스트 창이 모두 파괴된 후 이 함수를 호출하여 정리합니다. 이 함수를 호출하지 않으면 프로세스가 종료되면 창 클래스가 자동으로 등록 취소됩니다.

## <a name="atlgetobjectsourceinterface"></a><a name="atlgetobjectsourceinterface"></a>AtlGet개체소스인터페이스

개체의 기본 소스 인터페이스에 대한 정보를 검색하려면 이 함수를 호출합니다.

```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```

### <a name="parameters"></a>매개 변수

*펑크오브지*<br/>
【인】 정보를 반환할 개체에 대한 포인터입니다.

*plibid*<br/>
【아웃】 소스 인터페이스의 정의를 포함하는 형식 라이브러리의 LIBID에 대한 포인터입니다.

*piid*<br/>
【아웃】 개체의 기본 소스 인터페이스의 인터페이스 ID에 대한 포인터입니다.

*pdw메이저*<br/>
【아웃】 소스 인터페이스의 정의를 포함하는 형식 라이브러리의 주 버전 번호에 대한 포인터입니다.

*pdw마이너*<br/>
【아웃】 소스 인터페이스의 정의를 포함하는 형식 라이브러리의 부 버전 번호에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`AtlGetObjectSourceInterface`기본 소스 인터페이스의 인터페이스 ID와 해당 인터페이스를 설명하는 형식 라이브러리의 LIBID 및 주 및 부 버전 번호를 제공할 수 있습니다.

> [!NOTE]
> 이 함수가 요청된 정보를 성공적으로 검색하려면 *punkObj로* 표시되는 개체가 구현(및 `IDispatch` 통해 `IDispatch::GetTypeInfo`형식 `IProvideClassInfo2` `IPersist`정보를 반환)해야 하며 또한 구현해야 합니다. 원본 인터페이스의 형식 정보는 에 대한 형식 정보와 동일한 `IDispatch`형식 라이브러리에 있어야 합니다.

### <a name="example"></a>예제

아래 예제에서는 이벤트 싱크 클래스를 정의하는 `CEasySink`방법을 보여 주며, 이를 통해 맨 `IDispEventImpl` 손필수에 전달할 수 있는 템플릿 인수의 수를 줄입니다. `EasyAdvise`및 `EasyUnadvise` `AtlGetObjectSourceInterface` DispEvent조언 또는 [디스프EventUnadvise를](idispeventsimpleimpl-class.md#dispeventunadvise)호출하기 전에 [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) 멤버를 초기화하는 데 사용합니다. [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise)

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)<br/>
[복합 제어 매크로](../../atl/reference/composite-control-macros.md)
