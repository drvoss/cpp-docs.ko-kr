---
title: C모니커파일 클래스
ms.date: 11/04/2016
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
ms.openlocfilehash: fc74ad2499fcde63faa2c5859a87fd9ffd2846eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319777"
---
# <a name="cmonikerfile-class"></a>C모니커파일 클래스

[IMoniker에서](/windows/win32/api/objidl/nn-objidl-imoniker)명명된 데이터 [스트림(IStream)을](/windows/win32/api/objidl/nn-objidl-istream)나타냅니다.

## <a name="syntax"></a>구문

```
class CMonikerFile : public COleStreamFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C모니커파일::코모니커파일](#cmonikerfile)|`CMonikerFile` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C모니커파일:닫기](#close)|스트림을 분리하고 해제하고 모니커를 해제합니다.|
|[CMonikerFile::D에타치](#detach)|이 `IMoniker` `CMonikerFile` 개체에서 분리합니다.|
|[C모니커파일::겟모니커](#getmoniker)|현재 모니커를 반환합니다.|
|[C모니커파일::열기](#open)|스트림을 가져오려면 지정된 파일을 엽니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C모니커파일::컨텍스트 만들기](#createbindcontext)|바인딩 컨텍스트를 가져오거나 기본 초기화 바인딩 컨텍스트를 만듭니다.|

## <a name="remarks"></a>설명

모니커는 파일에 대한 경로 이름과 같은 정보를 포함합니다. 모니커 개체의 `IMoniker` 인터페이스에 대한 포인터가 있는 경우 파일이 실제로 있는 위치에 대한 다른 특정 정보없이 식별된 파일에 액세스할 수 있습니다.

에서 `COleStreamFile`파생 `CMonikerFile` 된 moniker 또는 모니커로 만들 수 있는 문자열 표현을 가져와 모니커가 이름이 되는 스트림에 바인딩합니다. 그런 다음 해당 스트림을 읽고 쓸 수 있습니다. 의 `CMonikerFile` 진정한 목적은 당신이 `IStream`스트림에 직접 `IMoniker`바인딩 할 필요가 없도록 s에 의해 명명 `CFile` 된 s에 대한 간단한 액세스를 제공하는 것입니다, 아직 스트림에 대한 기능을 가지고.

`CMonikerFile`스트림 이외의 다른 것에 바인딩하는 데 사용할 수 없습니다. 저장소 또는 개체에 바인딩하려면 인터페이스를 `IMoniker` 직접 사용해야 합니다.

스트림 및 모니커에 대한 자세한 내용은 Windows SDK의 *MFC 참조* 및 [IStream](/windows/win32/api/objidl/nn-objidl-istream) 및 [IMoniker의](/windows/win32/api/objidl/nn-objidl-imoniker) [COleStreamFile을](../../mfc/reference/colestreamfile-class.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="cmonikerfileclose"></a><a name="close"></a>C모니커파일:닫기

이 함수를 호출하여 스트림을 분리하고 해제하고 모니커를 해제합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

미개봉 또는 이미 닫힌 스트림에서 호출할 수 있습니다.

## <a name="cmonikerfilecmonikerfile"></a><a name="cmonikerfile"></a>C모니커파일::코모니커파일

`CMonikerFile` 개체를 생성합니다.

```
CMonikerFile();
```

## <a name="cmonikerfilecreatebindcontext"></a><a name="createbindcontext"></a>C모니커파일::컨텍스트 만들기

이 함수를 호출하여 기본 초기화 된 바인딩 컨텍스트를 만듭니다.

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>매개 변수

*pError*<br/>
파일 예외에 대한 포인터입니다. 오류가 발생하면 원인으로 설정됩니다.

### <a name="return-value"></a>Return Value

성공하면 바인딩할 바인딩 컨텍스트 [IBindCtx에](/windows/win32/api/objidl/nn-objidl-ibindctx) 대한 포인터입니다. 그렇지 않으면 NULL. `IBindHost` 인터페이스를 사용하여 인스턴스를 연 경우 바인딩 컨텍스트는 `IBindHost`에서 검색됩니다. 인터페이스가 없거나 `IBindHost` 인터페이스가 바인딩 컨텍스트를 반환하지 못하면 바인딩 컨텍스트가 만들어집니다. [IBindHost](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775076\(v=vs.85\)) 인터페이스에 대한 설명은 Windows SDK를 참조하십시오.

### <a name="remarks"></a>설명

바인딩 컨텍스트는 특정 모니커 바인딩 작업에 대한 정보를 저장하는 개체입니다. 이 함수를 재정의하여 사용자 바인딩 컨텍스트를 제공할 수 있습니다.

## <a name="cmonikerfiledetach"></a><a name="detach"></a>CMonikerFile::D에타치

이 함수를 호출하여 스트림을 닫습니다.

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*pError*<br/>
파일 예외에 대한 포인터입니다. 오류가 발생하면 원인으로 설정됩니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="cmonikerfilegetmoniker"></a><a name="getmoniker"></a>C모니커파일::겟모니커

이 함수를 호출하여 현재 모니커에 대한 포인터를 검색합니다.

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>Return Value

현재 모니커 인터페이스 [(IMoniker)에](/windows/win32/api/objidl/nn-objidl-imoniker)대한 포인터입니다.

### <a name="remarks"></a>설명

인터페이스가 아니므로 `CMonikerFile` 반환된 포인터는 [AddRef를](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)통해 참조 수를 증가시키지 않으며 `CMonikerFile` 개체가 해제될 때 모니커가 해제됩니다. 모니커를 붙들거나 직접 해제하려면 반드시 해제해야 `AddRef` 합니다.

## <a name="cmonikerfileopen"></a><a name="open"></a>C모니커파일::열기

이 멤버 함수를 호출하여 파일 또는 모니커 개체를 엽니다.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszURL*<br/>
열 파일의 URL 또는 파일 이름입니다.

*pError*<br/>
파일 예외에 대한 포인터입니다. 오류가 발생하면 원인으로 설정됩니다.

*프모니커 (것)와 함께*<br/>
스트림을 가져오는 데 사용할 `IMoniker` 모니커 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

*lpszURL* 매개 변수는 매킨토시에서 사용할 수 없습니다. 매킨토시에서는 *pMoniker* 형태만 사용할 `Open` 수 있습니다.

*lpszURL* 매개 변수에 대한 URL 또는 파일 이름을 사용할 수 있습니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\- 또는-

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>참고 항목

[코올스트림파일 클래스](../../mfc/reference/colestreamfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CAsync모니커파일 클래스](../../mfc/reference/casyncmonikerfile-class.md)
