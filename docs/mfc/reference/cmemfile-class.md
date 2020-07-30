---
title: CMemFile 클래스
description: CMemFile 클래스에서 사용할 수 있는 함수에 대해 설명 합니다 .이 함수를 사용 하면 메모리 파일을 사용할 수 있습니다.
ms.date: 07/23/2020
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CmemFile::GetBufferPtr
- AFX/CMemFile::GrowFile"
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
helpviewer_keywords:
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GetBufferPtr
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
ms.openlocfilehash: edd1d8b8d3979427602bdb61fc7647aec15d58b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222942"
---
# <a name="cmemfile-class"></a>CMemFile 클래스

메모리 파일을 지 원하는 [CFile](../../mfc/reference/cfile-class.md)파생 클래스입니다.

## <a name="syntax"></a>구문

```
class CMemFile : public CFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|Name|설명|
|----------|-----------------|
|[CMemFile:: CMemFile](#cmemfile)|메모리 파일 개체를 생성 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMemFile:: Attach](#attach)|에 메모리 블록을 연결 `CMemFile` 합니다.|
|[CMemFile::D etach](#detach)|에서 메모리 블록을 분리 `CMemFile` 하 고 분리 된 메모리 블록에 대 한 포인터를 반환 합니다.|
|[CMemFile:: GetBufferPtr](#getbufferptr)|메모리 파일을 백업 하는 메모리 버퍼를 가져오거나 씁니다.|

### <a name="protected-methods"></a>Protected 메서드

|Name|설명|
|----------|-----------------|
|[CMemFile:: Alloc](#alloc)|메모리 할당 동작을 수정 하려면를 재정의 합니다.|
|[CMemFile:: Free](#free)|메모리 할당 취소 동작을 수정 하려면를 재정의 합니다.|
|[CMemFile:: GrowFile](#growfile)|파일이 증가 하는 경우 수정 동작으로 재정의 합니다.|
|[CMemFile:: Memcpy](#memcpy)|파일을 읽고 쓸 때 메모리 복사 동작을 수정 하려면를 재정의 합니다.|
|[CMemFile:: Realloc](#realloc)|메모리 재할당 동작을 수정 하려면를 재정의 합니다.|

## <a name="remarks"></a>설명

이러한 메모리 파일은 디스크가 아닌 RAM에 저장 된 파일을 제외 하 고 디스크 파일 처럼 동작 합니다. 메모리 파일은 다음과 같은 경우에 유용 합니다.

- 빠른 임시 저장소
- 독립 프로세스 간에 원시 바이트 전송
- 독립 프로세스 간에 직렬화 된 개체 전송

`CMemFile`개체는 자체 메모리를 자동으로 할당할 수 있습니다. 또는 `CMemFile` [attach](#attach)를 호출 하 여 개체에 고유한 메모리 블록을 연결할 수 있습니다. 두 경우 모두 메모리 파일을 늘리기 위한 메모리가 `nGrowBytes` 0이 아닌 경우 자동으로 크기가 증가 `nGrowBytes` 합니다.

메모리 블록은 개체가 `CMemFile` 원래 개체에 의해 할당 된 경우 개체가 소멸 될 때 자동으로 삭제 됩니다 `CMemFile` . 그렇지 않으면 개체에 연결 된 메모리의 할당을 취소 해야 합니다.

`CMemFile` [Detach](#detach)를 호출 하 여 개체에서 분리할 때 제공 된 포인터를 통해 메모리 블록에 액세스할 수 있습니다.

가장 일반적으로 사용 되는 것은 `CMemFile` 개체를 만들고 `CMemFile` [CFile](../../mfc/reference/cfile-class.md) 멤버 함수를 호출 하 여 사용 하는 것입니다. 을 (를) 만들면 `CMemFile` 자동으로 열립니다 .이는 디스크 파일에만 사용 되는 [CFile:: Open](../../mfc/reference/cfile-class.md#open)을 호출 하지 않습니다. 는 `CMemFile` 디스크 파일을 사용 하지 않으므로 데이터 멤버가 `CFile::m_hFile` 사용 되지 않습니다.

`CFile` [중복](../../mfc/reference/cfile-class.md#duplicate), [Lockrange](../../mfc/reference/cfile-class.md#lockrange)및 [unlockrange](../../mfc/reference/cfile-class.md#unlockrange) 멤버 함수는에 대해 구현 되지 않습니다 `CMemFile` . 개체에서 이러한 함수를 호출 하면 `CMemFile` [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)이 발생 합니다.

`CMemFile`는 런타임 라이브러리 함수 [malloc](../../c-runtime-library/reference/malloc.md), [realloc](../../c-runtime-library/reference/realloc.md)및 [free](../../c-runtime-library/reference/free.md) 를 사용 하 여 메모리를 할당, 다시 할당 및 할당 취소 합니다. 그리고 읽고 쓸 때 복사 메모리를 차단할 내장 [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) . 이 동작을 변경 하거나가 파일을 늘릴 때 동작을 원하는 경우 `CMemFile` 에서 고유한 클래스를 파생 시키고 `CMemFile` 적절 한 함수를 재정의 합니다.

에 대 한 자세한 내용은 `CMemFile` mfc 및 [메모리 관리 (mfc)](../../mfc/memory-management.md) [의 문서 파일](../../mfc/files-in-mfc.md) 을 참조 하 고 *런타임 라이브러리 참조*에서 [파일 처리](../../c-runtime-library/file-handling.md) 를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CMemFile`

## <a name="requirements"></a>요구 사항

**헤더:** afx

## <a name="cmemfilealloc"></a><a name="alloc"></a>CMemFile:: Alloc

이 함수는 멤버 함수에 의해 호출 됩니다 `CMemFile` .

```
virtual BYTE* Alloc(SIZE_T nBytes);
```

### <a name="parameters"></a>매개 변수

*nBytes*<br/>
할당할 메모리의 바이트 수입니다.

### <a name="return-value"></a>Return Value

할당 된 메모리 블록에 대 한 포인터 이거나, 할당에 실패 한 경우 NULL입니다.

### <a name="remarks"></a>설명

사용자 지정 메모리 할당을 구현 하려면이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우 [Free](#free) 및 [Realloc](#realloc) 도 재정의할 수 있습니다.

기본 구현에서는 런타임 라이브러리 함수 [malloc](../../c-runtime-library/reference/malloc.md) 를 사용 하 여 메모리를 할당 합니다.

## <a name="cmemfileattach"></a><a name="attach"></a>CMemFile:: Attach

이 함수를 호출 하 여 메모리 블록을에 연결 `CMemFile` 합니다.

```cpp
void Attach(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuffer*<br/>
연결할 버퍼에 대 한 포인터 `CMemFile` 입니다.

*nBufferSize*<br/>
버퍼의 크기 (바이트)를 지정 하는 정수입니다.

*nGrowBytes*<br/>
메모리 할당 증가값 (바이트)입니다.

### <a name="remarks"></a>설명

그러면에서 메모리 `CMemFile` 블록을 메모리 파일로 사용 합니다.

*NGrowBytes* 가 0 이면는 `CMemFile` 파일 길이를 *nbuffersize*로 설정 합니다. 즉, 메모리 블록에 연결 되기 전에 메모리 블록의 데이터가 `CMemFile` 파일로 사용 됩니다. 이러한 방식으로 만들어진 메모리 파일은 증가 되지 않습니다.

파일의 크기가 증가할 수 없으므로에서 파일의 증가를 시도 하지 않도록 주의 해야 `CMemFile` 합니다. 예를 들어, 이전에 `CMemFile` 는 [Cfile: write](../../mfc/reference/cfile-class.md#write) 의 재정의를 호출 하지 마세요. 또는 길이가 *Nbuffersize*보다 긴 [cfile: SetLength](../../mfc/reference/cfile-class.md#setlength) 를 호출 하지 마세요.

*NGrowBytes* 가 0 보다 크면는 `CMemFile` 연결 된 메모리 블록의 내용을 무시 합니다. 의 재정의를 사용 하 여 메모리 파일의 콘텐츠를 처음부터 써야 `CMemFile` `CFile::Write` 합니다. 파일의 끝을 지나서 쓰려고 하거나의 재정의를 호출 하 여 파일을 확장 하려고 하면 `CMemFile` `CFile::SetLength` 에서 `CMemFile` 메모리 할당이 *nGrowBytes*증가 합니다. 에 전달 하는 메모리 블록이 `Attach` [Alloc](#alloc)과 호환 되는 메서드로 할당 되지 않은 경우 메모리 할당 증가는 실패 합니다. 의 기본 구현과 호환 되려면 `Alloc` 런타임 라이브러리 함수 [malloc](../../c-runtime-library/reference/malloc.md) 또는 [calloc](../../c-runtime-library/reference/calloc.md)를 사용 하 여 메모리를 할당 해야 합니다.

## <a name="cmemfilecmemfile"></a><a name="cmemfile"></a>CMemFile:: CMemFile

첫 번째 오버 로드는 빈 메모리 파일을 엽니다.

```
CMemFile(UINT nGrowBytes = 1024);

CMemFile(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>매개 변수

*nGrowBytes*<br/>
메모리 할당 증가값 (바이트)입니다.

*Lpbuffer* *Nbuffersize*크기 정보를 수신 하는 버퍼에 대 한 포인터입니다.

*nBufferSize*<br/>
파일 버퍼의 크기 (바이트)를 지정 하는 정수입니다.

### <a name="remarks"></a>설명

생성자에 의해 파일이 열립니다. [CFile:: Open](../../mfc/reference/cfile-class.md#open)을 호출 하지 마세요.

두 번째 오버 로드는 첫 번째 생성자를 사용 하 고 동일한 매개 변수를 사용 하 여 [Attach](#attach) 를 즉시 호출 하는 것과 동일 하 게 작동 합니다 자세한 내용은 `Attach`를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]

## <a name="cmemfiledetach"></a><a name="detach"></a>CMemFile::D etach

에서 사용 하는 메모리 블록에 대 한 포인터를 가져오려면이 함수를 호출 `CMemFile` 합니다.

```
BYTE* Detach();
```

### <a name="return-value"></a>Return Value

메모리 파일의 내용을 포함 하는 메모리 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 함수를 호출 하면도 닫힙니다 `CMemFile` . Attach를 호출 하 여 메모리 블록을에 다시 연결할 수 있습니다 `CMemFile` . [Attach](#attach) 파일을 다시 연결 하 고 그 안에 있는 데이터를 사용 하려는 경우에는를 호출 하기 전에 [CFile:: GetLength](../../mfc/reference/cfile-class.md#getlength) 를 호출 하 여 파일 길이를 가져와야 합니다 `Detach` . 데이터를 사용할 수 있도록 메모리 블록을에 연결 하는 경우 `CMemFile` ( `nGrowBytes` = = 0) 메모리 파일을 늘릴 수 없습니다.

## <a name="cmemfilefree"></a><a name="free"></a>CMemFile:: Free

이 함수는 멤버 함수에 의해 호출 됩니다 `CMemFile` .

```
virtual void Free(BYTE* lpMem);
```

### <a name="parameters"></a>매개 변수

*lpMem*<br/>
할당을 취소할 메모리에 대 한 포인터입니다.

### <a name="remarks"></a>설명

사용자 지정 메모리 할당 취소를 구현 하려면이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우에는 [할당](#alloc) 및 [Realloc](#realloc) 재정의할 수도 있습니다.

## <a name="cmemfilegetbufferptr"></a><a name="getbufferptr"></a>CMemFile:: GetBufferPtr

메모리 파일을 백업 하는 메모리 버퍼를 가져오거나 씁니다.

```cpp
virtual UINT GetBufferPtr(
    UINT nCommand,
    UINT nCount = 0,
    void** ppBufStart = NULL,
    void** ppBufMax = NULL
);
```

### <a name="parameters"></a>매개 변수

*n*<br/>
수행할 [buffercommand](buffercommand-enumeration.md) ( `bufferCheck` , `bufferCommit` , `bufferRead` 또는 `bufferWrite` )입니다.

*nCount*<br/>
*Ncommand*에 따라 읽기, 쓰기 또는 커밋에 대 한 버퍼의 바이트 수입니다. 버퍼에서 읽을 때-1을 지정 하 여 현재 위치에서 파일 끝으로 버퍼를 반환 합니다.

*ppBufStart*<br/>
제한이 버퍼의 시작입니다. `NULL` *Ncommand* 가 인 경우 여야 합니다 `bufferCommit` .

*ppBufMax*<br/>
제한이 버퍼의 끝입니다. `NULL`NCommand가 인 경우 여야 합니다 `bufferCommit` .

### <a name="return-value"></a>Return Value

| *명령* 값 | 반환 값 |
|--|--|
| `buffercheck` | 직접 버퍼링이 지원 되 면 [Bufferdirect](buffercommand-enumeration.md) 를 반환 하 고 그렇지 않으면 0을 반환 합니다. |
| `bufferCommit` | `0`를 반환합니다. |
| `bufferRead` 또는 `bufferWrite` | 반환 된 버퍼 공간의 바이트 수를 반환 합니다. *Ppbufstart* 와 *pp는* 읽기/쓰기 버퍼의 시작과 끝을 가리킵니다.  |

### <a name="remarks"></a>설명

메모리 버퍼 ()의 현재 위치는 `m_nPosition` *ncommand*에 따라 다음과 같은 방법으로 진행 됩니다.

| *n* | 버퍼 위치 |
|-|-|
| `bufferCommit` | 현재 위치가 커밋된 버퍼의 크기로 이동 합니다. |
| `bufferRead` | 현재 위치는 읽기 버퍼의 크기로 이동 합니다. |

## <a name="cmemfilegrowfile"></a><a name="growfile"></a>CMemFile:: GrowFile

이 함수는 여러 멤버 함수에서 호출 됩니다 `CMemFile` .

```
virtual void GrowFile(SIZE_T dwNewLen);
```

### <a name="parameters"></a>매개 변수

*dwNewLen*<br/>
메모리 파일의 새 크기입니다.

### <a name="remarks"></a>설명

파일의 크기가 증가 하는 방식을 변경 하려는 경우이를 재정의할 수 있습니다 `CMemFile` . 기본 구현에서는 [Realloc](#realloc) 를 호출 하 여 기존 블록 (또는 메모리 블록을 만들기 위한 [할당](#alloc) )을 확장 하 고 `nGrowBytes` 생성자 또는 [연결](#attach) 호출에 지정 된 값의 배수로 메모리를 할당 합니다.

## <a name="cmemfilememcpy"></a><a name="memcpy"></a>CMemFile:: Memcpy

이 함수는 `CMemFile` [cfile:: Read](../../mfc/reference/cfile-class.md#read) 및 [cfile:: Write](../../mfc/reference/cfile-class.md#write) 를 재정의 하 여 메모리 파일 간에 데이터를 전송 하는 방식으로 호출 됩니다.

```
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,
    const BYTE* lpMemSource,
    SIZE_T nBytes);
```

### <a name="parameters"></a>매개 변수

*lpMemTarget*<br/>
원본 메모리가 복사 될 메모리 블록에 대 한 포인터입니다.

*lpMemSource*<br/>
소스 메모리 블록에 대 한 포인터입니다.

*nBytes*<br/>
복사할 바이트 수입니다.

### <a name="return-value"></a>Return Value

*Lpmemtarget*의 복사본입니다.

### <a name="remarks"></a>설명

이러한 메모리를 복사 하는 방법을 변경 하려면이 함수를 재정의 `CMemFile` 합니다.

## <a name="cmemfilerealloc"></a><a name="realloc"></a>CMemFile:: Realloc

이 함수는 멤버 함수에 의해 호출 됩니다 `CMemFile` .

```
virtual BYTE* Realloc(
    BYTE* lpMem,
    SIZE_T nBytes);
```

### <a name="parameters"></a>매개 변수

*lpMem*<br/>
다시 할당할 메모리 블록에 대 한 포인터입니다.

*nBytes*<br/>
메모리 블록의 새 크기입니다.

### <a name="return-value"></a>Return Value

다시 할당 된 (그리고 이동 가능한) 메모리 블록에 대 한 포인터 이거나, 재할당에 실패 한 경우 NULL입니다.

### <a name="remarks"></a>설명

사용자 지정 메모리 재할당을 구현 하려면이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우에는 [할당](#alloc) 및 [무료](#free) 도 재정의할 수 있습니다.

## <a name="see-also"></a>참고 항목

[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
