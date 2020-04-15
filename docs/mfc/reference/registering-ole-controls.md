---
title: OLE 컨트롤 등록
ms.date: 11/04/2016
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
ms.openlocfilehash: 2f2d7872e8b9369b5eef283e5b52a54c29afd563
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372965"
---
# <a name="registering-ole-controls"></a>OLE 컨트롤 등록

다른 OLE 서버 개체와 마찬가지로 OLE 컨트롤은 다른 OLE 인식 응용 프로그램에서 액세스할 수 있습니다. 이는 컨트롤의 형식 라이브러리 및 클래스를 등록하여 달성됩니다.

다음 함수를 사용하면 Windows 등록 데이터베이스에서 컨트롤의 클래스, 속성 페이지 및 형식 라이브러리를 추가하고 제거할 수 있습니다.

### <a name="registering-ole-controls"></a>OLE 컨트롤 등록

|||
|-|-|
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|등록 데이터베이스에 컨트롤의 클래스를 추가합니다.|
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|등록 데이터베이스에 컨트롤 속성 페이지를 추가합니다.|
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|컨트롤의 형식 라이브러리를 등록 데이터베이스에 추가합니다.|
|[AfxOleUnregisterClass](#afxoleunregisterclass)|등록 데이터베이스에서 컨트롤 클래스 또는 속성 페이지 클래스를 제거합니다.|
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|등록 데이터베이스에서 컨트롤의 형식 라이브러리를 제거합니다.|

`AfxOleRegisterTypeLib`일반적으로 컨트롤 DLL의 구현에서 호출됩니다. `DllRegisterServer` 마찬가지로 `AfxOleUnregisterTypeLib` `DllUnregisterServer`에서 호출됩니다. `AfxOleRegisterControlClass`을 `AfxOleRegisterPropertyPageClass`위해 `AfxOleUnregisterClass` 일반적으로 컨트롤의 `UpdateRegistry` 클래스 팩터리 또는 속성 페이지의 멤버 함수에 의해 호출됩니다.

## <a name="afxoleregistercontrolclass"></a><a name="afxoleregistercontrolclass"></a>아프올레레지스터컨트롤클래스

Windows 등록 데이터베이스에 컨트롤 클래스를 등록합니다.

```
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,
    REFCLSID clsid,
    LPCTSTR pszProgID,
    UINT idTypeName,
    UINT idBitmap,
    int nRegFlags,
    DWORD dwMiscStatus,
    REFGUID tlid,
    WORD wVerMajor,
    WORD wVerMinor);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
컨트롤 클래스와 연결된 모듈의 인스턴스 핸들입니다.

*clsid*<br/>
컨트롤의 고유 클래스 ID입니다.

*pszProgID*<br/>
컨트롤의 고유 프로그램 ID입니다.

*idTypeName*<br/>
컨트롤에 대 한 사용자가 읽을 수 있는 형식 이름을 포함 하는 문자열의 리소스 ID입니다.

*id비트맵*<br/>
도구 모음 또는 팔레트에서 OLE 컨트롤을 나타내는 데 사용되는 비트맵의 리소스 ID입니다.

*n레그 플래그*<br/>
다음 플래그 중 하나 이상을 포함합니다.

- `afxRegInsertable`OLE 개체에 대한 개체 삽입 대화 상자에 컨트롤이 표시되도록 허용합니다.

- `afxRegApartmentThreading`레지스트리의 스레딩 모델을 스레딩모델=아파트로 설정합니다.

- `afxRegFreeThreading`레지스트리의 스레딩 모델을 스레딩모델=무료로 설정합니다.

   두 플래그를 `afxRegApartmentThreading` 결합하고 `afxRegFreeThreading` 스레딩 모델=둘 다로 설정할 수 있습니다. 스레딩 모델 등록에 대한 자세한 내용은 Windows SDK의 [InprocServer32를](/windows/win32/com/inprocserver32) 참조하십시오.

> [!NOTE]
> MFC 4.2 이전의 MFC 버전에서 **int** *nRegFlags* 매개 변수는 BOOL 매개 변수인 *bInsertable으로*개체 삽입 대화 상자에서 컨트롤을 삽입하거나 허용하지 않았습니다.

*dwMisc상태*<br/>
다음 상태 플래그 중 하나 이상을 포함합니다(플래그설명은 Windows SDK의 OLEMISC 열거형 참조).

- OLEMISC_RECOMPOSEONRESIZE

- OLEMISC_ONLYICONIC

- OLEMISC_INSERTNOTREPLACE

- OLEMISC_STATIC

- OLEMISC_CANTLINKINSIDE

- OLEMISC_CANLINKBYOLE1

- OLEMISC_ISLINKOBJECT

- OLEMISC_INSIDEOUT

- OLEMISC_ACTIVATEWHENVISIBLE

- OLEMISC_RENDERINGISDEVICEINDEPENDENT

- OLEMISC_INVISIBLEATRUNTIME

- OLEMISC_ALWAYSRUN

- OLEMISC_ACTSLIKEBUTTON

- OLEMISC_ACTSLIKELABEL

- OLEMISC_NOUIACTIVATE

- OLEMISC_ALIGNABLE

- OLEMISC_IMEMODE

- OLEMISC_SIMPLEFRAME

- OLEMISC_SETCLIENTSITEFIRST

*tlid*<br/>
컨트롤 클래스의 고유 ID입니다.

*wVerMajor*<br/>
컨트롤 클래스의 주 버전 번호입니다.

*wVerMinor*<br/>
컨트롤 클래스의 부 버전 번호입니다.

### <a name="return-value"></a>Return Value

컨트롤 클래스가 등록된 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이렇게 하면 OLE 제어를 인식하는 컨테이너에서 컨트롤을 사용할 수 있습니다. `AfxOleRegisterControlClass`시스템의 컨트롤 이름과 위치로 레지스트리를 업데이트하고 컨트롤이 레지스트리에서 지원하는 스레딩 모델을 설정합니다. 자세한 내용은 [기술 참고 64,](../../mfc/tn064-apartment-model-threading-in-activex-controls.md)"OLE 컨트롤의 아파트 모델 스레딩" 및 Windows SDK의 [프로세스 및 스레드 정보를](/windows/win32/ProcThread/about-processes-and-threads) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]

위의 예제에서는 삽입 `AfxOleRegisterControlClass` 가능한 플래그와 아파트 모델 ORed의 플래그를 함께 사용하여 여섯 번째 매개 변수를 만드는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]

컨트롤은 활성화된 컨테이너에 대한 개체 삽입 대화 상자에 표시되며 아파트 모델 인식이 됩니다. 아파트 모델 인식 컨트롤은 정적 클래스 데이터가 잠금으로 보호되도록 해야 하므로 한 아파트의 컨트롤이 정적 데이터에 액세스하는 동안 이 작업이 완료되기 전에 스케줄러에 의해 비활성화되지 않고 동일한 클래스의 다른 인스턴스가 동일한 정적 데이터를 사용하기 시작합니다. 정적 데이터에 대한 모든 액세스는 중요한 섹션 코드로 둘러싸여 있습니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

## <a name="afxoleregisterpropertypageclass"></a><a name="afxoleregisterpropertypageclass"></a>아프올레레지스터프로퍼티페이지클래스

Windows 등록 데이터베이스에 속성 페이지 클래스를 등록합니다.

```
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,
   REFCLSID  clsid,
   UINT idTypeName,
   int nRegFlags);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
속성 페이지 클래스와 연결된 모듈의 인스턴스 핸들입니다.

*clsid*<br/>
속성 페이지의 고유 클래스 ID입니다.

*idTypeName*<br/>
속성 페이지에 대해 사용자가 읽을 수 있는 이름이 포함된 문자열의 리소스 ID입니다.

*n레그 플래그*<br/>
플래그가 포함될 수 있습니다.

- `afxRegApartmentThreading`레지스트리의 스레딩 모델을 스레딩 모델 = 아파트로 설정합니다.

> [!NOTE]
> MFC 4.2 이전의 MFC 버전에서는 int *nRegFlags* 매개 **변수를** 사용할 수 없습니다. 또한 `afxRegInsertable` 플래그는 속성 페이지에 대한 유효한 옵션이 아니며 설정된 경우 MFC에서 ASSERT가 발생합니다.

### <a name="return-value"></a>Return Value

컨트롤 클래스가 등록된 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이렇게 하면 OLE 제어를 인식하는 컨테이너에서 속성 페이지를 사용할 수 있습니다. `AfxOleRegisterPropertyPageClass`레지스트리를 속성 페이지 이름과 시스템의 위치로 업데이트하고 컨트롤이 레지스트리에서 지원하는 스레딩 모델을 설정합니다. 자세한 내용은 [기술 참고 64,](../../mfc/tn064-apartment-model-threading-in-activex-controls.md)"OLE 컨트롤의 아파트 모델 스레딩" 및 Windows SDK의 [프로세스 및 스레드 정보를](/windows/win32/ProcThread/about-processes-and-threads) 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

## <a name="afxoleregistertypelib"></a><a name="afxoleregistertypelib"></a>아프올레레지스터타이핑리브

Windows 등록 데이터베이스에 형식 라이브러리를 등록하고 OLE 컨트롤을 인식하는 다른 컨테이너에서 형식 라이브러리를 사용할 수 있도록 허용합니다.

```
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,
    REFGUID tlid,
    LPCTSTR pszFileName = NULL,
    LPCTSTR pszHelpDir  = NULL);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
형식 라이브러리와 연결된 애플리케이션의 인스턴스 핸들입니다.

*tlid*<br/>
형식 라이브러리의 고유 ID입니다.

*pszFileName*<br/>
컨트롤에 대해 지역화된 형식 라이브러리(.TLB) 파일의 선택적인 파일 이름을 가리킵니다.

*pszHelpDir*<br/>
형식 라이브러리에 대한 도움말 파일을 찾을 수 있는 디렉터리의 이름입니다. NULL인 경우, 도움말 파일은 해당 형식 라이브러리 자체와 동일한 디렉터리에 있는 것으로 간주됩니다.

### <a name="return-value"></a>Return Value

형식 라이브러리가 등록된 경우 0이 아닌 값이고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 시스템에서 레지스트리를 형식 라이브러리 이름 및 해당 위치로 업데이트합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]

[!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="afxoleunregisterclass"></a><a name="afxoleunregisterclass"></a>아fxOleUn레지스터클래스

Windows 등록 데이터베이스에서 컨트롤 또는 속성 페이지 클래스 항목을 제거합니다.

```
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID);
```

### <a name="parameters"></a>매개 변수

*Clsid*<br/>
컨트롤 또는 속성 페이지의 고유 클래스 ID입니다.

*pszProgID*<br/>
컨트롤 또는 속성 페이지의 고유 프로그램 ID입니다.

### <a name="return-value"></a>Return Value

컨트롤 또는 속성 페이지 클래스가 등록취소된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

## <a name="afxoleunregistertypelib"></a><a name="afxoleunregistertypelib"></a>아프올레언레지스터타입리브

Windows 등록 데이터베이스에서 형식 라이브러리 항목을 제거 하려면이 함수를 호출 합니다.

```
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID);
```

### <a name="parameters"></a>매개 변수

*tlID*<br/>
형식 라이브러리의 고유 ID입니다.

### <a name="return-value"></a>Return Value

형식 라이브러리가 등록취소된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
