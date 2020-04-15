---
title: C최근파일리스트 클래스
ms.date: 11/04/2016
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
ms.openlocfilehash: a2102c6a39c14c548828e57ad1c49de6a5bc03dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370903"
---
# <a name="crecentfilelist-class"></a>C최근파일리스트 클래스

MRU(가장 최근에 사용됨) 파일 목록의 컨트롤을 지원합니다.

## <a name="syntax"></a>구문

```
class CRecentFileList
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C최근 파일 목록::C최근파일목록](#crecentfilelist)|`CRecentFileList` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C최근 파일 목록::추가](#add)|MRU 파일 목록에 파일을 추가합니다.|
|[C최근 파일 목록::GetDisplayName](#getdisplayname)|MRU 파일 이름의 메뉴 표시에 대 한 표시 이름을 제공 합니다.|
|[C최근 파일 목록::GetSize](#getsize)|MRU 파일 목록의 파일 수를 검색합니다.|
|[C최근 파일 목록::읽기 목록](#readlist)|레지스트리 또는 에서 MRU 파일 목록을 읽습니다. INI 파일입니다.|
|[C최근 파일 목록::제거](#remove)|MRU 파일 목록에서 파일을 제거합니다.|
|[C최근 파일 목록::업데이트 메뉴](#updatemenu)|MRU 파일 목록의 메뉴 표시를 업데이트합니다.|
|[C최근 파일 목록::쓰기 목록](#writelist)|레지스트리 또는 에서 MRU 파일 목록을 작성합니다. INI 파일입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C최근 파일 목록::연산자 \[\]](#operator_at)|지정된 `CString` 위치에서 객체를 반환합니다.|

## <a name="remarks"></a>설명

MRU 파일 목록에 파일을 추가하거나 삭제할 수 있으며, 파일 목록을 레지스트리 또는 에 기록하거나 읽을 수 있습니다. INI 파일 및 MRU 파일 목록을 표시하는 메뉴를 업데이트할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CRecentFileList`

## <a name="requirements"></a>요구 사항

**헤더:** afxadv.h

## <a name="crecentfilelistadd"></a><a name="add"></a>C최근 파일 목록::추가

가장 최근에 사용한(MRU) 파일 목록에 파일을 추가합니다.

```
virtual void Add(LPCTSTR lpszPathName);

virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
목록에 추가할 경로 이름을 지정합니다.

*lpszAppID*<br/>
응용 프로그램에 대한 응용 프로그램 사용자 모델 ID를 지정합니다.

*pItem*<br/>
목록에 추가할 셸 항목에 대한 포인터를 지정합니다.

*pLink*<br/>
목록에 추가할 Shell 링크에 대한 포인터를 지정합니다.

*Pidl*<br/>
최근 문서 폴더에 추가해야 하는 셸 항목에 대한 IDLIST를 지정합니다.

### <a name="remarks"></a>설명

파일 이름이 MRU 목록의 맨 위에 추가됩니다. MRU 목록에 파일 이름이 이미 있으면 맨 위로 이동합니다.

## <a name="crecentfilelistcrecentfilelist"></a><a name="crecentfilelist"></a>C최근 파일 목록::C최근파일목록

`CRecentFileList` 개체를 생성합니다.

```
CRecentFileList(
    UINT nStart,
    LPCTSTR lpszSection,
    LPCTSTR lpszEntryFormat,
    int nSize,
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```

### <a name="parameters"></a>매개 변수

*nStart*<br/>
MRU(가장 최근에 사용한) 파일 목록의 메뉴 표시에서 번호 매기기간격띄우기.

*lpszSection*<br/>
레지스트리 또는 응용 프로그램의 섹션 이름을 가리킵니다. MRU 파일 목록을 읽거나 쓰는 INI 파일입니다.

*lpszEntryFormat*<br/>
레지스트리 또는 응용 프로그램의 에 저장된 항목의 이름에 사용할 형식 문자열을 가리킵니다. INI 파일입니다.

*nSize*<br/>
MRU 파일 목록의 최대 파일 수입니다.

*nMaxDispLen*<br/>
MRU 파일 목록에서 파일 이름을 메뉴로 표시하는 데 사용할 수 있는 문자의 최대 길이입니다.

### <a name="remarks"></a>설명

*lpszEntryFormat으로* 가리키는 형식 문자열에는 각 MRU 항목의 인덱스를 대체하는 데 사용되는 "%d"가 포함되어야 합니다. 예를 들어 형식 문자열이 `"file%d"` 있으면 항목 이름이 `file0` `file1`지정됩니다 .

## <a name="crecentfilelistgetdisplayname"></a><a name="getdisplayname"></a>C최근 파일 목록::GetDisplayName

MRU 목록의 메뉴 표시에 사용할 MRU 파일 목록의 파일에 대한 표시 이름을 가져옵니다.

```
virtual BOOL GetDisplayName(
    CString& strName,
    int nIndex,
    LPCTSTR lpszCurDir,
    int nCurDir,
    BOOL bAtLeastName = TRUE) const;
```

### <a name="parameters"></a>매개 변수

*strName*<br/>
이름이 MRU 파일의 메뉴 목록에 표시될 파일의 전체 경로입니다.

*nIndex*<br/>
MRU 파일 목록에서 파일의 0기반 인덱스입니다.

*lpszCurDir*<br/>
현재 디렉토리를 보유하는 문자열입니다.

*n커디르*<br/>
현재 디렉터리 문자열의 길이입니다.

*bALeastName*<br/>
영하지 않은 경우 파일의 기본 이름이 최대 표시 길이를 초과하는 경우에도 반환되어야 음을 나타냅니다(생성자에게 *nMaxDispLen* 매개 변수로 `CRecentFileList` 전달됨).

### <a name="return-value"></a>Return Value

**가장** 최근에 사용한(MRU) 파일 목록에서 지정된 인덱스에 파일 이름이 없는 경우 FALSE입니다.

### <a name="remarks"></a>설명

파일이 현재 디렉터리에 있으면 함수가 디렉터리에서 해제됩니다. 파일 이름이 너무 길면 디렉터리 및 확장이 제거됩니다. 파일 이름이 여전히 너무 길면 *bAtLeastName이* 영해가 아닌 경우 표시 이름이 빈 문자열로 설정됩니다.

## <a name="crecentfilelistgetsize"></a><a name="getsize"></a>C최근 파일 목록::GetSize

MRU 파일 목록의 파일 수를 검색합니다.

```
int GetSize() const;
```

### <a name="return-value"></a>Return Value

현재 가장 최근에 사용된 MRU(파일) 파일 목록의 파일 수입니다.

## <a name="crecentfilelistoperator--"></a><a name="operator_at"></a>C최근파일목록::연산자 [ ]

오버로드된 subscript`[]`() 연산자는 `CString` *nIndex에서*제로 기반 인덱스로 지정된 단일 을 반환합니다.

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
s 집합에서 a의 `CString` `CString`0기반 인덱스입니다.

## <a name="crecentfilelistreadlist"></a><a name="readlist"></a>C최근 파일 목록::읽기 목록

레지스트리 또는 응용 프로그램의 에서 가장 최근에 사용한 (MRU) 파일 목록을 읽습니다. INI 파일입니다.

```
virtual void ReadList();
```

## <a name="crecentfilelistremove"></a><a name="remove"></a>C최근 파일 목록::제거

MRU 파일 목록에서 파일을 제거합니다.

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
가장 최근에 사용된 MRU(파일) 파일 목록에서 제거할 파일의 0기반 인덱스입니다.

## <a name="crecentfilelistupdatemenu"></a><a name="updatemenu"></a>C최근 파일 목록::업데이트 메뉴

MRU 파일 목록의 메뉴 표시를 업데이트합니다.

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
가장 최근에 사용된 MRU(파일 목록 메뉴)에 대한 [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체에 대한 포인터입니다.

## <a name="crecentfilelistwritelist"></a><a name="writelist"></a>C최근 파일 목록::쓰기 목록

가장 최근에 사용한(MRU) 파일 목록을 레지스트리 또는 응용 프로그램의 에 씁니다. INI 파일입니다.

```
virtual void WriteList();
```

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)
