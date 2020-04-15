---
title: C인터넷예외 클래스
ms.date: 11/04/2016
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
ms.openlocfilehash: b0239afa2b984ccf93d661ec11f11013c89fd912
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372415"
---
# <a name="cinternetexception-class"></a>C인터넷예외 클래스

인터넷 작업과 관련된 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CInternetException : public CException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C인터넷예외::CInternet예외](#cinternetexception)|`CInternetException` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C인터넷예외::m_dwContext](#m_dwcontext)|예외를 발생 시킨 작업과 관련 된 컨텍스트 값입니다.|
|[C인터넷예외::m_dwError](#m_dwerror)|예외를 일으킨 오류입니다.|

## <a name="remarks"></a>설명

클래스에는 `CInternetException` 두 개의 공용 데이터 멤버가 포함됩니다.

인터넷 응용 프로그램에 대한 컨텍스트 식별자에 대한 자세한 내용은 [WinInet와 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="cinternetexceptioncinternetexception"></a><a name="cinternetexception"></a>C인터넷예외::CInternet예외

이 멤버 함수는 `CInternetException` 개체를 만들 때 호출됩니다.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>매개 변수

*dwError*<br/>
예외를 일으킨 오류입니다.

### <a name="remarks"></a>설명

CInternetException을 throw하려면 MFC 글로벌 함수 [AfxThrowInternetException을](internet-url-parsing-globals.md#afxthrowinternetexception)호출합니다.

## <a name="cinternetexceptionm_dwcontext"></a><a name="m_dwcontext"></a>C인터넷예외::m_dwContext

관련 인터넷 작업과 관련된 컨텍스트 값입니다.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>설명

컨텍스트 식별자는 원래 [CInternetSession에](../../mfc/reference/cinternetsession-class.md) 지정되어 MFC에서 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)및 [CInternetFile-파생](../../mfc/reference/cinternetfile-class.md)클래스로 전달됩니다. 이 기본값을 재정의하고 *dwContext* 매개 변수를 선택한 값으로 할당할 수 있습니다. *dwContext는* 지정된 개체의 모든 작업과 연결됩니다. *dwContext는* [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)에서 반환된 작업의 상태 정보를 식별합니다.

## <a name="cinternetexceptionm_dwerror"></a><a name="m_dwerror"></a>C인터넷예외::m_dwError

예외를 일으킨 오류입니다.

```
DWORD m_dwError;
```

### <a name="remarks"></a>설명

이 오류 값은 WINERROR에 있는 시스템 오류 코드일 수 있습니다. H, 또는 위니넷의 오류 값입니다. H.

Win32 오류 코드 목록은 [오류 코드를](/windows/win32/Debug/system-error-codes)참조하십시오. 인터넷 관련 오류 메시지 목록은 을 참조하십시오. 두 항목 모두 Windows SDK에 있습니다.

## <a name="see-also"></a>참고 항목

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)
