---
title: CDataPath속성 클래스
ms.date: 11/04/2016
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
ms.openlocfilehash: 479f5d47d9cff72d36dbd25e434182af1ba01ef4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754656"
---
# <a name="cdatapathproperty-class"></a>CDataPath속성 클래스

비동기적으로 로드할 수 있는 OLE 컨트롤 속성을 구현합니다.

## <a name="syntax"></a>구문

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDataPath속성::CDataPath속성](#cdatapathproperty)|`CDataPathProperty` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDataPath속성::Getcontrol](#getcontrol)|개체와 연결된 비동기 OLE 컨트롤을 `CDataPathProperty` 검색합니다.|
|[CDataPath속성::GetPath](#getpath)|속성의 경로 이름을 검색합니다.|
|[CDataPath속성::열기](#open)|연결된 ActiveX(OLE) 컨트롤에 대한 비동기 속성 로드를 시작합니다.|
|[CDataPath속성::재설정 데이터](#resetdata)|제어 `CAsyncMonikerFile::OnDataAvailable` 속성이 변경되었음을 컨테이너에 알리는 호출입니다.|
|[CDataPath속성::세트 컨트롤](#setcontrol)|속성과 연결된 비동기 ActiveX(OLE) 컨트롤을 설정합니다.|
|[CDataPath속성::SetPath](#setpath)|속성의 경로 이름을 설정합니다.|

## <a name="remarks"></a>설명

비동기 속성은 동기 시작 후 로드됩니다.

클래스는 `CDataPathProperty` 에서 `CAysncMonikerFile`파생됩니다. OLE 컨트롤에서 비동기 속성을 구현하려면 에서 `CDataPathProperty`클래스를 파생하고 OnDataAvailable 을 재정의합니다. [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)

인터넷 응용 프로그램에서 비동기 모니커 및 ActiveX 컨트롤을 사용하는 방법에 대한 자세한 내용은 다음 문서를 참조하십시오.

- [인터넷 첫 번째 단계: 액티브X 컨트롤](../../mfc/activex-controls-on-the-internet.md)

- [인터넷 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="cdatapathpropertycdatapathproperty"></a><a name="cdatapathproperty"></a>CDataPath속성::CDataPath속성

`CDataPathProperty` 개체를 생성합니다.

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>매개 변수

*pControl*<br/>
이 `CDataPathProperty` 개체와 연결될 OLE 컨트롤 개체에 대한 포인터입니다.

*lpszPath*<br/>
절대 또는 상대경로는 속성의 실제 절대 위치를 참조하는 비동기 모니커를 만드는 데 사용됩니다. `CDataPathProperty`는 파일 이름이 아닌 URL을 사용합니다. 파일에 대한 `CDataPathProperty` 객체를 원하는 경우 `file://` 경로에 미리 지정합니다.

### <a name="remarks"></a>설명

*pControl이* 가리키는 `COleControl` 개체는 파생 `Open` 클래스에서 사용하고 검색됩니다. *pControl이* NULL이면 함께 `Open` 사용되는 컨트롤을 `SetControl`로 설정해야 합니다. *lpszPath가* NULL인 경우 경로를 통과하거나 `Open` `SetPath`로 설정할 수 있습니다.

## <a name="cdatapathpropertygetcontrol"></a><a name="getcontrol"></a>CDataPath속성::Getcontrol

이 멤버 함수를 `COleControl` 호출하여 개체와 연결된 개체를 검색합니다. `CDataPathProperty`

```
COleControl* GetControl();
```

### <a name="return-value"></a>Return Value

개체와 연결된 OLE 컨트롤에 `CDataPathProperty` 대한 포인터를 반환합니다. NULL 이 제어하지 않으면 연결됩니다.

## <a name="cdatapathpropertygetpath"></a><a name="getpath"></a>CDataPath속성::GetPath

이 멤버 함수를 호출하여 경로를 `CDataPathProperty` 검색하거나, 개체가 `Open`생성되거나, 에 지정되거나, `SetPath` 멤버 함수에 대한 이전 호출에서 지정될 때 설정합니다.

```
CString GetPath() const;
```

### <a name="return-value"></a>Return Value

속성 자체에 경로 이름을 반환합니다. 경로를 지정하지 않은 경우 비어 있을 수 있습니다.

## <a name="cdatapathpropertyopen"></a><a name="open"></a>CDataPath속성::열기

이 멤버 함수를 호출하여 연결된 컨트롤에 대한 비동기 속성 로드를 시작합니다.

```
virtual BOOL Open(
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    CFileException* pError = NULL);

virtual BOOL Open(CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*pControl*<br/>
이 `CDataPathProperty` 개체와 연결될 OLE 컨트롤 개체에 대한 포인터입니다.

*pError*<br/>
파일 예외에 대한 포인터입니다. 오류가 발생하면 원인으로 설정됩니다.

*lpszPath*<br/>
절대 또는 상대경로는 속성의 실제 절대 위치를 참조하는 비동기 모니커를 만드는 데 사용됩니다. `CDataPathProperty`는 파일 이름이 아닌 URL을 사용합니다. 파일에 대한 `CDataPathProperty` 객체를 원하는 경우 `file://` 경로에 미리 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

함수는 컨트롤에서 `IBindHost` 인터페이스를 가져오려고 시도합니다.

경로 `Open` 없이 호출 하기 전에 속성 경로에 대 한 값을 설정 해야 합니다. 이 작업은 개체가 생성될 때 또는 `SetPath` 멤버 함수를 호출하여 수행할 수 있습니다.

컨트롤 `Open` 없이 호출 하기 전에 ActiveX 컨트롤(이전의 OLE 컨트롤)을 개체와 연결할 수 있습니다. 이 작업은 개체가 생성될 때 또는 `SetControl`를 호출하여 수행할 수 있습니다.

[CAsyncMonikerFile::Open의](../../mfc/reference/casyncmonikerfile-class.md#open) 모든 오버로드는 `CDataPathProperty`에서 사용할 수 있습니다.

## <a name="cdatapathpropertyresetdata"></a><a name="resetdata"></a>CDataPath속성::재설정 데이터

이 함수를 `CAsyncMonikerFile::OnDataAvailable` 호출하여 컨테이너에 제어 속성이 변경되었으며 비동기적으로 로드된 모든 정보가 더 이상 유용하지 않음을 사용자에게 알립니다.

```
virtual void ResetData();
```

### <a name="remarks"></a>설명

열기를 다시 시작해야 합니다. 파생 클래스는 다른 기본값에 대해 이 함수를 재정의할 수 있습니다.

## <a name="cdatapathpropertysetcontrol"></a><a name="setcontrol"></a>CDataPath속성::세트 컨트롤

이 멤버 함수를 호출하여 비동기 OLE `CDataPathProperty` 컨트롤을 개체와 연결합니다.

```cpp
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>매개 변수

*pControl*<br/>
속성과 연결될 비동기 OLE 컨트롤에 대한 포인터입니다.

## <a name="cdatapathpropertysetpath"></a><a name="setpath"></a>CDataPath속성::SetPath

이 멤버 함수를 호출하여 속성의 pathname을 설정합니다.

```cpp
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>매개 변수

*lpszPath*<br/>
비동기적으로 로드되는 속성에 대한 절대 또는 상대적 일 수 있는 경로입니다. `CDataPathProperty`는 파일 이름이 아닌 URL을 사용합니다. 파일에 대한 `CDataPathProperty` 객체를 원하는 경우 `file://` 경로에 미리 지정합니다.

## <a name="see-also"></a>참조

[MFC 샘플 이미지](../../overview/visual-cpp-samples.md)<br/>
[CAsync모니커파일 클래스](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CAsync모니커파일 클래스](../../mfc/reference/casyncmonikerfile-class.md)
