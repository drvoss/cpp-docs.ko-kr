---
title: CGopherFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
ms.openlocfilehash: e157a4509fe30b814a1834690a675906ac82afe7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373700"
---
# <a name="cgopherfile-class"></a>CGopherFile 클래스

Gopher 서버에서 파일을 찾고 읽는 기능을 제공합니다.

> [!NOTE]
> 클래스 `CGopherConnection`및 `CGopherFile` `CGopherFileFind` `CGopherLocator` 해당 구성원은 Windows XP 플랫폼에서 작동하지 않지만 이전 플랫폼에서 계속 작동하므로 더 이상 사용되지 않습니다.

## <a name="syntax"></a>구문

```
class CGopherFile : public CInternetFile
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CGopher파일::CGopherFile](#cgopherfile)|`CGopherFile` 개체를 생성합니다.|

## <a name="remarks"></a>설명

이 서비스는 주로 정보를 찾기 위한 메뉴 기반 인터페이스로 작동하기 때문에 사용자가 gopher 파일에 데이터를 쓸 수 없습니다. `CGopherFile` 멤버는 `Write`에 `WriteString`대해 `CGopherFile` `Flush` 구현되지 않습니다. `CGopherFile` 개체에서 이러한 함수를 호출하면 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

다른 MFC `CGopherFile` 인터넷 클래스와 함께 작동하는 방법에 대한 자세한 내용은 [WinInet와 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CGopherFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="cgopherfilecgopherfile"></a><a name="cgopherfile"></a>CGopher파일::CGopherFile

이 멤버 함수는 개체를 생성하기 위해 호출됩니다. `CGopherFile`

```
CGopherFile(
    HINTERNET hFile,
    CGopherLocator& refLocator,
    CGopherConnection* pConnection);

CGopherFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrLocator,
    DWORD dwLocLen,
    DWORD_PTR dwContext);
```

### <a name="parameters"></a>매개 변수

*hFile*<br/>
HINTERNET 파일에 대한 핸들입니다.

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체에 대한 참조입니다.

*pConnection*<br/>
[CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 개체에 대한 포인터입니다.

*hSession*<br/>
현재 인터넷 세션에 대한 핸들입니다.

*스트로케이터*<br/>
고퍼 서버를 찾는 데 사용되는 문자열에 대한 포인터입니다. 고퍼 로케이터에 대한 자세한 내용은 [고퍼 세션을](cgopherlocator-class.md) 참조하십시오.

*dwLocLen*<br/>
*pstrLocator의*바이트 수를 포함하는 DWORD입니다.

*dwContext*<br/>
열려 있는 파일의 컨텍스트 식별자에 대한 포인터입니다.

### <a name="remarks"></a>설명

고퍼 `CGopherFile` 인터넷 세션 중에 파일에서 읽을 개체가 필요합니다.

개체를 `CGopherFile` 직접 만들지 않습니다. 대신 [CGopherConnection::OpenFile을](../../mfc/reference/cgopherconnection-class.md#openfile) 호출하여 고퍼 서버에서 파일을 엽니다.

## <a name="see-also"></a>참고 항목

[C인터넷파일 클래스](../../mfc/reference/cinternetfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C인터넷파일 클래스](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherLocator 클래스](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopher파일찾기 클래스](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CGopher커넥션 클래스](../../mfc/reference/cgopherconnection-class.md)
