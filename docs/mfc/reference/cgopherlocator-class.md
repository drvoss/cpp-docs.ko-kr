---
title: CGopherLocator 클래스
ms.date: 11/04/2016
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
ms.openlocfilehash: d23ef3dad68c62e74ec64454953ca372b8c31114
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373670"
---
# <a name="cgopherlocator-class"></a>CGopherLocator 클래스

고퍼 서버에서 고퍼 "로케이터"를 얻고 로케이터의 유형을 결정하고 [CGopherFileFind에서](../../mfc/reference/cgopherfilefind-class.md)로케이터를 사용할 수 있게 합니다.

> [!NOTE]
> 클래스 `CGopherConnection`및 `CGopherFile` `CGopherFileFind` `CGopherLocator` 해당 구성원은 Windows XP 플랫폼에서 작동하지 않지만 이전 플랫폼에서 계속 작동하므로 더 이상 사용되지 않습니다.

## <a name="syntax"></a>구문

```
class CGopherLocator : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CGopherLocator::CGopherLocator](#cgopherlocator)|`CGopherLocator` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CGopherLocator::GetLocatorType](#getlocatortype)|고퍼 로케이터를 구문 분석하여 속성을 결정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CGopherLocator::연산자 LPCTSTR](#operator_lpctstr)|개체에 저장된 문자에 `CGopherLocator` C 스타일 문자열로 직접 액세스합니다.|

## <a name="remarks"></a>설명

응용 프로그램은 해당 서버에서 정보를 검색하려면 먼저 gopher 서버의 로케이터를 가져와야 합니다. 로케이터가 있으면 로케이터를 불투명 토큰으로 처리해야 합니다.

각 gopher 로케이터에는 발견된 파일 또는 서버의 유형을 결정하는 특성이 있습니다. 고퍼 로케이터 유형 목록은 [GetLocatorType을](#getlocatortype) 참조하십시오.

응용 프로그램은 일반적으로 [CGopherFileFind:FindFile에](../../mfc/reference/cgopherfilefind-class.md#findfile) 대한 호출에 대한 로케이터를 사용하여 특정 정보를 검색합니다.

다른 MFC `CGopherLocator` 인터넷 클래스와 함께 작동하는 방법에 대한 자세한 내용은 [WinInet와 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="cgopherlocatorcgopherlocator"></a><a name="cgopherlocator"></a>CGopherLocator::CGopherLocator

이 멤버 함수는 개체를 만들기 위해 호출됩니다. `CGopherLocator`

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>매개 변수

*ref*<br/>
상수 `CGopherLocator` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

개체를 `CGopherLocator` 직접 만들지 않습니다. 대신 [CGopherConnection::CreateLocator를](../../mfc/reference/cgopherconnection-class.md#createlocator) 호출하여 `CGopherLocator` 개체에 대한 포인터를 만들고 반환합니다.

## <a name="cgopherlocatorgetlocatortype"></a><a name="getlocatortype"></a>CGopherLocator::GetLocatorType

로케이터 유형을 얻으려면 이 멤버 함수를 호출합니다.

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>매개 변수

*dwRef*<br/>
로케이터 유형을 수신하는 DWORD에 대한 참조입니다. 로케이터 유형 표는 **비고를** 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

가능한 유형은 다음과 같습니다.

|값|의미|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|ASCII 텍스트 파일입니다.|
|GOPHER_TYPE_DIRECTORY|추가 고퍼 항목의 디렉토리입니다.|
|GOPHER_TYPE_CSO|CSO 전화 번호부 서버입니다.|
|GOPHER_TYPE_ERROR|오류 조건을 나타냅니다.|
|GOPHER_TYPE_MAC_BINHEX|BINHEX 형식의 매킨토시 파일입니다.|
|GOPHER_TYPE_DOS_ARCHIVE|DOS 아카이브 파일입니다.|
|GOPHER_TYPE_UNIX_UUENCODED|UUENCODED 파일입니다.|
|GOPHER_TYPE_INDEX_SERVER|인덱스 서버입니다.|
|GOPHER_TYPE_TELNET|텔넷 서버.|
|GOPHER_TYPE_BINARY|이진 파일입니다.|
|GOPHER_TYPE_REDUNDANT|중복된 서버입니다. 내에 포함된 정보는 기본 서버의 복제본입니다. 기본 서버는 GOPHER_TYPE_REDUNDANT 형식이 없는 마지막 디렉터리 항목입니다.|
|GOPHER_TYPE_TN3270|TN3270 서버.|
|GOPHER_TYPE_GIF|GIF 그래픽 파일입니다.|
|GOPHER_TYPE_IMAGE|이미지 파일입니다.|
|GOPHER_TYPE_BITMAP|비트맵 파일입니다.|
|GOPHER_TYPE_MOVIE|동영상 파일입니다.|
|GOPHER_TYPE_SOUND|사운드 파일입니다.|
|GOPHER_TYPE_HTML|HTML 문서입니다.|
|GOPHER_TYPE_PDF|PDF 파일입니다.|
|GOPHER_TYPE_CALENDAR|캘린더 파일입니다.|
|GOPHER_TYPE_INLINE|인라인 파일입니다.|
|GOPHER_TYPE_UNKNOWN|항목 유형을 알 수 없습니다.|
|GOPHER_TYPE_ASK|Ask+ 항목입니다.|
|GOPHER_TYPE_GOPHER_PLUS|고퍼+ 아이템.|

## <a name="cgopherlocatoroperator-lpctstr"></a><a name="operator_lpctstr"></a>CGopherLocator::연산자 LPCTSTR

이 유용한 캐스팅 연산자는 `CGopherLocator` 개체에 포함된 null 종료C 문자열에 액세스하는 효율적인 방법을 제공합니다.

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>Return Value

문자열의 데이터에 대한 문자 포인터입니다.

### <a name="remarks"></a>설명

문자는 복사되지 않습니다. 포인터만 반환됩니다.

## <a name="see-also"></a>참고 항목

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CGopher파일찾기 클래스](../../mfc/reference/cgopherfilefind-class.md)
