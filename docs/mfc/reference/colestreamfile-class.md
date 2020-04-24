---
title: 코올스트림파일 클래스
ms.date: 11/04/2016
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
ms.openlocfilehash: 202f8381361881ce3b8b62f81da5bfb81a1f952d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753751"
---
# <a name="colestreamfile-class"></a>코올스트림파일 클래스

OLE 구조적 스토리지의 일부로 복합 파일의 데이터 스트림(`IStream`)을 나타냅니다.

## <a name="syntax"></a>구문

```
class COleStreamFile : public CFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레스트림파일::콜레스트림파일](#colestreamfile)|`COleStreamFile` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleStream파일::첨부](#attach)|스트림을 개체와 연결합니다.|
|[COleStream파일::메모리 스트림 만들기](#creatememorystream)|전역 메모리에서 스트림을 만들고 개체와 연결합니다.|
|[COleStream파일::만들기스트림](#createstream)|스트림을 만들고 개체와 연결합니다.|
|[콜스트림파일::D](#detach)|개체에서 스트림을 분리합니다.|
|[COleStream파일::겟스트림](#getstream)|현재 스트림을 반환합니다.|
|[COleStream파일::오픈스트림](#openstream)|스트림을 안전하게 열고 개체와 연결합니다.|

## <a name="remarks"></a>설명

메모리 `IStorage` 스트림이 아니면 스트림을 열거나 만들 수 있기 전에 개체가 있어야 합니다.

`COleStreamFile`개체는 [CFile](../../mfc/reference/cfile-class.md) 개체와 똑같이 조작됩니다.

스트림 및 저장소 조작에 대한 자세한 내용은 [컨테이너: 복합 파일](../../mfc/containers-compound-files.md).을 참조하십시오.

자세한 내용은 Windows SDK의 [IStream](/windows/win32/api/objidl/nn-objidl-istream) 및 [IStorage를](/windows/win32/api/objidl/nn-objidl-istorage) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`COleStreamFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="colestreamfileattach"></a><a name="attach"></a>COleStream파일::첨부

제공된 OLE 스트림을 `COleStreamFile` 개체와 연결합니다.

```cpp
void Attach(LPSTREAM lpStream);
```

### <a name="parameters"></a>매개 변수

*lpStream*<br/>
개체와 연결될`IStream`OLE 스트림()을 가리킵니다. NULL이 될 수 없습니다.

### <a name="remarks"></a>설명

개체가 OLE 스트림과 아직 연결되지 않아야 합니다.

자세한 내용은 Windows SDK의 [IStream을](/windows/win32/api/objidl/nn-objidl-istream) 참조하십시오.

## <a name="colestreamfilecolestreamfile"></a><a name="colestreamfile"></a>콜레스트림파일::콜레스트림파일

`COleStreamFile` 개체를 만듭니다.

```
COleStreamFile(LPSTREAM lpStream = NULL);
```

### <a name="parameters"></a>매개 변수

*lpStream*<br/>
개체와 연결될 OLE 스트림에 대한 포인터입니다.

### <a name="remarks"></a>설명

*lpStream이* NULL이면 개체가 OLE 스트림과 연결되지 않고, 그렇지 않으면 개체가 제공된 OLE 스트림과 연결됩니다.

자세한 내용은 Windows SDK의 [IStream을](/windows/win32/api/objidl/nn-objidl-istream) 참조하십시오.

## <a name="colestreamfilecreatememorystream"></a><a name="creatememorystream"></a>COleStream파일::메모리 스트림 만들기

오류가 정상, 예상 된 조건인 전역 공유 메모리에서 새 스트림을 안전하게 만듭니다.

```
BOOL CreateMemoryStream(CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*pError*<br/>
만들기 작업의 완료 상태를 나타내는 [CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 NULL을 가리킵니다. 스트림을 만들려고 시도하여 생성된 가능한 예외를 모니터링하려는 경우 이 매개 변수를 공급합니다.

### <a name="return-value"></a>Return Value

스트림이 성공적으로 생성되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

메모리는 OLE 하위 시스템에 의해 할당됩니다.

자세한 내용은 Windows SDK에서 [CreateStreamOnHGlobal을](/windows/win32/api/combaseapi/nf-combaseapi-createstreamonhglobal) 참조하십시오.

## <a name="colestreamfilecreatestream"></a><a name="createstream"></a>COleStream파일::만들기스트림

제공된 저장소 개체에 오류가 정상, 예상 상태인 새 스트림을 안전하게 만듭니다.

```
BOOL CreateStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*lpStorage*<br/>
만들 스트림을 포함하는 OLE 저장소 개체를 가리킵니다. NULL이 될 수 없습니다.

*lpszStream이름*<br/>
만들 스트림의 이름입니다. NULL이 될 수 없습니다.

*n오픈 플래그*<br/>
스트림을 열 때 사용할 액세스 모드입니다. 배타적, 읽기/쓰기 및 만들기 모드는 기본적으로 사용됩니다. 사용 가능한 모드의 전체 목록은 [CFile::CFile](../../mfc/reference/cfile-class.md#cfile)을 참조하십시오.

*pError*<br/>
[CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 NULL을 가리킵니다. 스트림을 만들려고 시도하여 생성된 가능한 예외를 모니터링하려는 경우 이 매개 변수를 공급합니다.

### <a name="return-value"></a>Return Value

스트림이 성공적으로 생성되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

열려 있는 오류가 실패하고 *pError가* NULL이 아닌 경우 파일 예외가 throw됩니다.

자세한 내용은 [IStorage::CreateStream](/windows/win32/api/objidl/nf-objidl-istorage-createstream) Windows SDK를 참조하십시오.

## <a name="colestreamfiledetach"></a><a name="detach"></a>콜스트림파일::D

스트림을 닫지 않고 개체에서 스트림을 분리합니다.

```
LPSTREAM Detach();
```

### <a name="return-value"></a>Return Value

개체와 연결된 스트림()에`IStream`대한 포인터입니다.

### <a name="remarks"></a>설명

프로그램이 종료되기 전에 스트림을 다른 방식으로 닫아야 합니다.

자세한 내용은 Windows SDK의 [IStream을](/windows/win32/api/objidl/nn-objidl-istream) 참조하십시오.

## <a name="colestreamfilegetstream"></a><a name="getstream"></a>COleStream파일::겟스트림

이 함수를 호출하여 포인터를 현재 스트림에 반환합니다.

```
IStream* GetStream() const;
```

### <a name="return-value"></a>Return Value

현재 스트림 인터페이스 [(IStream)에](/windows/win32/api/objidl/nn-objidl-istream)대한 포인터입니다.

## <a name="colestreamfileopenstream"></a><a name="openstream"></a>COleStream파일::오픈스트림

기존 스트림을 엽니다.

```
BOOL OpenStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*lpStorage*<br/>
열 스트림을 포함하는 OLE 저장소 개체를 가리킵니다. NULL이 될 수 없습니다.

*lpszStream이름*<br/>
열 스트림의 이름입니다. NULL이 될 수 없습니다.

*n오픈 플래그*<br/>
스트림을 열 때 사용할 액세스 모드입니다. 배타적 및 읽기/쓰기 모드는 기본적으로 사용됩니다. 사용 가능한 모드의 전체 목록은 [CFile::CFile](../../mfc/reference/cfile-class.md#cfile)을 참조하십시오.

*pError*<br/>
[CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 NULL을 가리킵니다. 스트림을 열려고 시도하여 생성된 가능한 예외를 모니터링하려는 경우 이 매개 변수를 공급합니다.

### <a name="return-value"></a>Return Value

스트림이 성공적으로 열리면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

열려 있는 오류가 실패하고 *pError가* NULL이 아닌 경우 파일 예외가 throw됩니다.

자세한 내용은 Windows SDK의 [IStorage::OpenStream을](/windows/win32/api/objidl/nf-objidl-istorage-openstream) 참조하십시오.

## <a name="see-also"></a>참조

[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
