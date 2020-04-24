---
title: CMemFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
helpviewer_keywords:
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
ms.openlocfilehash: 1bd88ad17bdb047de4c344ab96f3d9aecbe23c31
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752639"
---
# <a name="cmemfile-class"></a>CMemFile 클래스

메모리 파일을 지원하는 [CFile-파생](../../mfc/reference/cfile-class.md)클래스입니다.

## <a name="syntax"></a>구문

```
class CMemFile : public CFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMemFile::CMemFile](#cmemfile)|메모리 파일 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMemFile::첨부](#attach)|에 메모리 블록을 `CMemFile`연결합니다.|
|[CMemFile::D에타치](#detach)|메모리 블록을 `CMemFile` 분리하고 분리된 메모리 블록에 대한 포인터를 반환합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMemFile::Alloc](#alloc)|메모리 할당 동작을 수정하려면 재정의합니다.|
|[CMemFile::무료](#free)|메모리 할당 할당 동작을 수정하려면 재정의합니다.|
|[CMemFile::GrowFile](#growfile)|파일을 키를 때 동작을 수정하려면 재정의합니다.|
|[CMemFile::Memcpy](#memcpy)|파일을 읽고 쓸 때 메모리 복사 동작을 수정하려면 재정의합니다.|
|[CMemFile::Realloc](#realloc)|메모리 재할당 동작을 수정하려면 재정의합니다.|

## <a name="remarks"></a>설명

이러한 메모리 파일은 파일이 디스크가 아닌 RAM에 저장된다는 점을 제외하고는 디스크 파일처럼 행동합니다. 메모리 파일은 빠른 임시 저장소 또는 독립적인 프로세스 간에 원시 바이트 또는 직렬화된 개체를 전송하는 데 유용합니다.

`CMemFile`개체는 자동으로 자신의 메모리를 할당할 수 있습니다 또는 `CMemFile` 호출 하여 개체에 자신의 메모리 블록을 연결할 수 있습니다 [.에 연결](#attach)합니다. 두 경우 모두 메모리 파일을 자동으로 증가시키는 메모리는 0이 아닌 `nGrowBytes` `nGrowBytes` 경우 -sized 증분으로 할당됩니다.

메모리가 원래 개체에 `CMemFile` 의해 할당된 경우 개체가 파괴되면 메모리 `CMemFile` 블록이 자동으로 삭제됩니다. 그렇지 않으면 개체에 연결한 메모리를 할당 할 책임이 있습니다.

[Detach를](#detach)호출하여 개체에서 분리할 때 제공된 `CMemFile` 포인터를 통해 메모리 블록에 액세스할 수 있습니다.

가장 일반적인 `CMemFile` 용도는 개체를 `CMemFile` 만들고 [CFile](../../mfc/reference/cfile-class.md) 멤버 함수를 호출하여 사용하는 것입니다. `CMemFile` 자동으로 만들면 [CFile::Open을](../../mfc/reference/cfile-class.md#open)호출하지 않으며 디스크 파일에만 사용됩니다. 디스크 `CMemFile` 파일을 사용하지 않으므로 데이터 멤버가 `CFile::m_hFile` 사용되지 않습니다.

`CFile` 멤버 함수 [중복](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange)및 [UnlockRange에](../../mfc/reference/cfile-class.md#unlockrange) 대해 `CMemFile`구현되지 않습니다. `CMemFile` 개체에서 이러한 함수를 호출하면 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

`CMemFile`런타임 라이브러리 함수 [malloc,](../../c-runtime-library/reference/malloc.md) [realloc을](../../c-runtime-library/reference/realloc.md)사용하고 메모리를 할당, 재할당 및 할당 해제할 [수 있습니다.](../../c-runtime-library/reference/free.md) 그리고 읽기 및 쓰기 할 때 복사 메모리를 차단하는 본질적인 [memcpy.](../../c-runtime-library/reference/memcpy-wmemcpy.md) 파일을 가져올 때 `CMemFile` 이 동작이나 동작을 변경하려면 사용자 고유의 `CMemFile` 클래스를 파생하여 적절한 함수를 재정의합니다.

자세한 `CMemFile`내용은 [MFC](../../mfc/files-in-mfc.md) 및 [메모리 관리(MFC)의](../../mfc/memory-management.md) 문서 파일을 참조하고 *런타임 라이브러리 참조에서* [파일 처리를](../../c-runtime-library/file-handling.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CMemFile`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cmemfilealloc"></a><a name="alloc"></a>CMemFile::Alloc

이 함수는 `CMemFile` 멤버 함수에서 호출합니다.

```
virtual BYTE* Alloc(SIZE_T nBytes);
```

### <a name="parameters"></a>매개 변수

*n바이트*<br/>
할당할 메모리 바이트 수입니다.

### <a name="return-value"></a>Return Value

할당된 메모리 블록에 대한 포인터 또는 할당에 실패한 경우 NULL입니다.

### <a name="remarks"></a>설명

사용자 지정 메모리 할당을 구현하려면 이 함수를 재정의합니다. 이 함수를 재정의하는 경우 [Free](#free) 및 [Realloc도](#realloc) 재정의할 수 있습니다.

기본 구현은 런타임 라이브러리 함수 [malloc을](../../c-runtime-library/reference/malloc.md) 사용하여 메모리를 할당합니다.

## <a name="cmemfileattach"></a><a name="attach"></a>CMemFile::첨부

이 함수를 호출하여 메모리 `CMemFile`블록을 에 연결합니다.

```cpp
void Attach(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>매개 변수

*lp버퍼*<br/>
에 연결할 버퍼에 대한 `CMemFile`포인터

*n버퍼 크기*<br/>
버퍼 크기를 바이트로 지정하는 정수입니다.

*nGrow바이트*<br/>
메모리 할당이 바이트 단위로 증가합니다.

### <a name="remarks"></a>설명

이렇게 `CMemFile` 하면 메모리 블록을 메모리 파일로 사용합니다.

*nGrowBytes가* 0이면 `CMemFile` 파일 길이를 *nBufferSize로*설정합니다. 즉, 첨부되기 전에 메모리 블록의 데이터가 `CMemFile` 파일로 사용됩니다. 이러한 방식으로 생성된 메모리 파일은 생성할 수 없습니다.

파일을 늘릴 수 없으므로 파일을 늘리려고 `CMemFile` 시도하지 않도록 주의하십시오. 예를 들어 `CMemFile` [CFile:Write의](../../mfc/reference/cfile-class.md#write) 재정의를 호출하여 끝을 지나서 쓰거나 *nBufferSize*보다 긴 길이의 [CFile:SetLength를](../../mfc/reference/cfile-class.md#setlength) 호출하지 마십시오.

*nGrowBytes가* 0보다 `CMemFile` 크면 첨부한 메모리 블록의 내용을 무시합니다. 의 `CMemFile` 재정의를 `CFile::Write`사용하여 메모리 파일의 내용을 처음부터 작성해야 합니다. 파일의 끝을 지나서 `CMemFile` 작성하거나 `CFile::SetLength`의 `CMemFile` 재정의를 호출하여 파일을 늘리려고 하면 *nGrowBytes*단위로 메모리 할당이 증가합니다. `Attach` [Alloc와](#alloc)호환되는 메서드와 함께 전달한 메모리 블록이 할당되지 않은 경우 메모리 할당을 늘리지 못합니다. `Alloc`의 기본 구현과 호환되려면 런타임 라이브러리 함수 [malloc](../../c-runtime-library/reference/malloc.md) 또는 [calloc를](../../c-runtime-library/reference/calloc.md)사용하여 메모리를 할당해야 합니다.

## <a name="cmemfilecmemfile"></a><a name="cmemfile"></a>CMemFile::CMemFile

첫 번째 오버로드는 빈 메모리 파일을 엽니다.

```
CMemFile(UINT nGrowBytes = 1024);

CMemFile(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>매개 변수

*nGrow바이트*<br/>
메모리 할당이 바이트 단위로 증가합니다.

*lpBuffe*r 크기 *nBufferSize의*정보를 수신 하는 버퍼에 대 한 포인터 .

*n버퍼 크기*<br/>
파일 버퍼의 크기를 바이트로 지정하는 정수입니다.

### <a name="remarks"></a>설명

파일은 생성자에서 열리며 [CFile::Open](../../mfc/reference/cfile-class.md#open)을 호출해서는 안 됩니다.

두 번째 오버로드는 첫 번째 생성자 및 동일한 매개 변수를 사용하여 즉시 [Attach라고](#attach) 하는 경우와 동일하게 작동합니다. 자세한 내용은 `Attach`를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]

## <a name="cmemfiledetach"></a><a name="detach"></a>CMemFile::D에타치

이 함수를 호출하여 `CMemFile`에서 사용 중인 메모리 블록에 대한 포인터를 가져옵니다.

```
BYTE* Detach();
```

### <a name="return-value"></a>Return Value

메모리 파일의 내용을 포함하는 메모리 블록에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수를 호출하면 `CMemFile`을 닫습니다. `CMemFile` [연결](#attach)을 호출하여 메모리 블록을 다시 연결할 수 있습니다. 파일을 다시 연결하고 그 안에 있는 데이터를 사용하려면 [CFile::GetLength를](../../mfc/reference/cfile-class.md#getlength) 호출하여 호출하기 `Detach`전에 파일의 길이를 얻어야 합니다. 데이터(== `nGrowBytes` 0)를 `CMemFile` 사용할 수 있도록 메모리 블록을 연결하면 메모리 파일을 늘릴 수 없습니다.

## <a name="cmemfilefree"></a><a name="free"></a>CMemFile::무료

이 함수는 `CMemFile` 멤버 함수에서 호출합니다.

```
virtual void Free(BYTE* lpMem);
```

### <a name="parameters"></a>매개 변수

*lpMem*<br/>
할당 할 메모리에 대한 포인터입니다.

### <a name="remarks"></a>설명

사용자 지정 메모리 할당 을 구현 하려면이 함수를 재정의 합니다. 이 함수를 재정의하는 경우 [Alloc](#alloc) 및 [Realloc도](#realloc) 재정의할 수 있습니다.

## <a name="cmemfilegrowfile"></a><a name="growfile"></a>CMemFile::GrowFile

이 함수는 여러 멤버 `CMemFile` 함수에서 호출됩니다.

```
virtual void GrowFile(SIZE_T dwNewLen);
```

### <a name="parameters"></a>매개 변수

*dw뉴렌*<br/>
메모리 파일의 새 크기입니다.

### <a name="remarks"></a>설명

파일을 증가하는 방법을 `CMemFile` 변경하려면 재정의할 수 있습니다. 기본 구현에서는 [Realloc을](#realloc) 호출하여 기존 블록(또는 [Alloc에서](#alloc) 메모리 블록을 생성)하여 `nGrowBytes` 생성자 또는 [Attach](#attach) 호출에 지정된 값의 배수로 메모리를 할당합니다.

## <a name="cmemfilememcpy"></a><a name="memcpy"></a>CMemFile::Memcpy

이 함수는 `CMemFile` [CFile::Read](../../mfc/reference/cfile-class.md#read) 및 [CFile:Write의](../../mfc/reference/cfile-class.md#write) 재정의에 의해 호출되어 메모리 파일로 데이터를 전송합니다.

```
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,
    const BYTE* lpMemSource,
    SIZE_T nBytes);
```

### <a name="parameters"></a>매개 변수

*lpMemTarget*<br/>
원본 메모리가 복사될 메모리 블록에 대한 포인터입니다.

*lpMem출처*<br/>
소스 메모리 블록에 대한 포인터입니다.

*n바이트*<br/>
복사할 바이트 수입니다.

### <a name="return-value"></a>Return Value

*lpMemTarget의*복사본입니다.

### <a name="remarks"></a>설명

이러한 메모리 복사본을 `CMemFile` 수행하는 방법을 변경하려면 이 함수를 재정의합니다.

## <a name="cmemfilerealloc"></a><a name="realloc"></a>CMemFile::Realloc

이 함수는 `CMemFile` 멤버 함수에서 호출합니다.

```
virtual BYTE* Realloc(
    BYTE* lpMem,
    SIZE_T nBytes);
```

### <a name="parameters"></a>매개 변수

*lpMem*<br/>
다시 할당할 메모리 블록에 대한 포인터입니다.

*n바이트*<br/>
메모리 블록의 새 크기입니다.

### <a name="return-value"></a>Return Value

재할당(및 이동)된 메모리 블록에 대한 포인터 또는 재할당에 실패한 경우 NULL입니다.

### <a name="remarks"></a>설명

사용자 지정 메모리 재할당을 구현하려면 이 함수를 재정의합니다. 이 함수를 재정의하는 경우 [Alloc](#alloc) 및 [Free도](#free) 재정의할 수 있습니다.

## <a name="see-also"></a>참조

[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
