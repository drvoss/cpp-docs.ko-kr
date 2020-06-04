---
title: CSharedFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
ms.openlocfilehash: c715ca1b8a2b647f89ada008f3c6606ca5e58783
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750383"
---
# <a name="csharedfile-class"></a>CSharedFile 클래스

공유 메모리 파일을 지원하는 [CMemFile-파생](../../mfc/reference/cmemfile-class.md)클래스입니다.

## <a name="syntax"></a>구문

```
class CSharedFile : public CMemFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CShared 파일::CShared파일](#csharedfile)|`CSharedFile` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CShared 파일::D](#detach)|공유 메모리 파일을 닫고 메모리 블록의 핸들을 반환합니다.|
|[CShared 파일::세트 핸들](#sethandle)|공유 메모리 파일을 메모리 블록에 연결합니다.|

## <a name="remarks"></a>설명

메모리 파일은 디스크 파일처럼 행동합니다. 차이점은 메모리 파일이 디스크가 아닌 RAM에 저장된다는 점입니다. 메모리 파일은 빠른 임시 저장소 또는 독립 프로세스 간에 원시 바이트 또는 직렬화된 개체를 전송하는 데 유용합니다.

공유 메모리 파일은 [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows 함수와 함께 할당되는 메모리의 다른 메모리 파일과 다릅니다. 클래스는 `CSharedFile` 전역으로 할당된 메모리 블록(사용 `GlobalAlloc`사용하여 생성됨)에 데이터를 저장하며, 이 메모리 블록은 DDE, 클립보드 또는 다른 `IDataObject`OLE/COM 균일한 데이터 전송 작업을 사용하여 공유할 수 있습니다.

`GlobalAlloc`[malloc에서](../../c-runtime-library/reference/malloc.md)반환되는 포인터와 같이 메모리에 대한 포인터가 아닌 HGLOBAL 핸들을 반환합니다. 특정 응용 프로그램에서는 HGLOBAL 핸들이 필요합니다. 예를 들어 클립보드에 데이터를 넣려면 HGLOBAL 핸들이 필요합니다.

`CSharedFile`메모리 매핑된 파일을 사용하지 않으며 프로세스 간에 데이터를 직접 공유할 수 없습니다.

`CSharedFile`개체는 자동으로 자신의 메모리를 할당할 수 있습니다. 또는 [CSharedFile:SetHandle](#sethandle)을 `CSharedFile` 호출하여 개체에 사용자 고유의 메모리 블록을 연결할 수 있습니다. 두 경우 모두 메모리 파일을 자동으로 증가시키는 메모리는 0이 아닌 `nGrowBytes` `nGrowBytes` 경우 -sized 씩 씩씩히 할당됩니다.

자세한 내용은 [MFC의](../../mfc/files-in-mfc.md) 문서 파일 및 *런타임 라이브러리 참조의* [파일 처리를](../../c-runtime-library/file-handling.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CMemFile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxadv.h

## <a name="csharedfilecsharedfile"></a><a name="csharedfile"></a>CShared 파일::CShared파일

개체를 `CSharedFile` 구성하고 개체에 대한 메모리를 할당합니다.

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>매개 변수

*nAllocFlags*<br/>
메모리를 할당하는 방법을 나타내는 플래그입니다. 유효한 플래그 값 목록은 [GlobalAlloc를](/windows/win32/api/winbase/nf-winbase-globalalloc) 참조하십시오.

*nGrow바이트*<br/>
메모리 할당이 바이트 단위로 증가합니다.

## <a name="csharedfiledetach"></a><a name="detach"></a>CShared 파일::D

이 함수를 호출하여 메모리 파일을 닫고 메모리 블록에서 분리합니다.

```
HGLOBAL Detach();
```

### <a name="return-value"></a>Return Value

메모리 파일의 내용을 포함하는 메모리 블록의 핸들입니다.

### <a name="remarks"></a>설명

**Detach에서**반환한 핸들을 사용하여 [SetHandle을](#sethandle)호출하여 다시 열 수 있습니다.

## <a name="csharedfilesethandle"></a><a name="sethandle"></a>CShared 파일::세트 핸들

이 함수를 호출하여 전역 메모리 `CSharedFile` 블록을 개체에 연결합니다.

```cpp
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>매개 변수

*h글로벌메모리*<br/>
`CSharedFile`에 연결할 전역 메모리를 처리합니다.

*bAllowGrow*<br/>
메모리 블록이 증가할 수 있는지 여부를 지정합니다.

### <a name="remarks"></a>설명

*bAllowGrow가* 0이 아닌 경우 메모리 블록의 크기보다 파일에 더 많은 바이트를 작성하려는 경우 와 같이 필요에 따라 메모리 블록의 크기가 증가합니다.

## <a name="see-also"></a>참조

[CMemFile 클래스](../../mfc/reference/cmemfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CMemFile 클래스](../../mfc/reference/cmemfile-class.md)
