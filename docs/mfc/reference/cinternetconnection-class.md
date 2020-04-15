---
title: C인터넷커넥션 클래스
ms.date: 11/04/2016
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
ms.openlocfilehash: 6649986f279e010a833b31157922cb4fd1ea8613
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372419"
---
# <a name="cinternetconnection-class"></a>C인터넷커넥션 클래스

인터넷 서버와의 연결을 관리합니다.

## <a name="syntax"></a>구문

```
class CInternetConnection : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C인터넷 연결::인터넷 연결](#cinternetconnection)|`CInternetConnection` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C인터넷 연결::GetContext](#getcontext)|이 연결 개체에 대한 컨텍스트 ID를 가져옵니다.|
|[C인터넷 연결::GetServerName](#getservername)|연결과 연결된 서버의 이름을 가져옵니다.|
|[C인터넷 연결::GetSession](#getsession)|연결과 연결된 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에 대한 포인터를 가져옵니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C인터넷연결::연산자 HINTERNET](#operator_hinternet)|인터넷 세션에 대한 핸들입니다.|

## <a name="remarks"></a>설명

MFC 클래스 [CFtpConnection,](../../mfc/reference/cftpconnection-class.md) [CHttpConnection](../../mfc/reference/chttpconnection-class.md)및 [CGopherConnection의](../../mfc/reference/cgopherconnection-class.md)기본 클래스입니다. 이러한 각 클래스는 각 FTP, HTTP 또는 고퍼 서버와 통신하기 위한 추가 기능을 제공합니다.

인터넷 서버와 직접 통신하려면 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체와 개체가 `CInternetConnection` 있어야 합니다.

WinInet 클래스의 작동 방식에 대한 자세한 내용은 [WinInet와 함께 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="cinternetconnectioncinternetconnection"></a><a name="cinternetconnection"></a>C인터넷 연결::인터넷 연결

이 멤버 함수는 `CInternetConnection` 개체를 만들 때 호출됩니다.

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pSession*<br/>
[CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에 대한 포인터입니다.

*pstrServer*<br/>
서버 이름을 포함하는 문자열에 대한 포인터입니다.

*nPort*<br/>
이 연결에 대한 인터넷 포트를 식별하는 숫자입니다.

*dwContext*<br/>
개체에 대한 컨텍스트 `CInternetConnection` 식별자입니다. *dwContext*에 대한 자세한 내용은 **비고를** 참조하십시오.

### <a name="remarks"></a>설명

당신은 자신을 `CInternetConnection` 호출하지 않습니다; 대신 설정하려는 연결 유형에 대해 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 멤버 함수를 호출합니다.

- [C인터넷세션::겟프트연결](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [C인터넷세션::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [C인터넷세션::겟고퍼커넥션](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

*dwContext의* 기본값은 MFC에서 `CInternetConnection` **인터넷연결-파생**개체를 만든 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 파생된 개체로 전송됩니다. 기본값은 1로 설정됩니다. 그러나 연결에 대 한 [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) 생성자에서 특정 컨텍스트 식별자를 명시적으로 할당할 수 있습니다. 개체 및 개체가 수행하는 모든 작업은 해당 컨텍스트 ID와 연결됩니다. 컨텍스트 식별자가 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별되는 개체에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

## <a name="cinternetconnectiongetcontext"></a><a name="getcontext"></a>C인터넷 연결::GetContext

이 세션의 컨텍스트 ID를 얻으려면 이 멤버 함수를 호출합니다.

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Return Value

응용 프로그램에서 할당된 컨텍스트 ID입니다.

### <a name="remarks"></a>설명

컨텍스트 ID는 원래 [CInternetSession에](../../mfc/reference/cinternetsession-class.md) 지정되어 `CInternetConnection`있으며 연결을 여는 함수에 대해 호출에서 다르게 지정하지 않는 한 [CInternetFile-derived](../../mfc/reference/cinternetfile-class.md)클래스에 전파됩니다. 컨텍스트 ID는 지정된 개체의 모든 작업과 연결되며 [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)에서 반환되는 작업의 상태 정보를 식별합니다.

사용자 상태 정보를 `GetContext` 제공하기 위해 다른 WinInet 클래스와 작동하는 방법에 대한 자세한 내용은 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계 인 WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

## <a name="cinternetconnectiongetservername"></a><a name="getservername"></a>C인터넷 연결::GetServerName

이 구성원 함수를 호출하여 이 인터넷 연결과 연결된 서버의 이름을 가져옵니다.

```
CString GetServerName() const;
```

### <a name="return-value"></a>Return Value

이 연결 개체가 작업중인 서버의 이름입니다.

## <a name="cinternetconnectiongetsession"></a><a name="getsession"></a>C인터넷 연결::GetSession

이 멤버 함수를 호출하여 `CInternetSession` 이 연결과 연결된 개체에 대한 포인터를 가져옵니다.

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>Return Value

이 인터넷 연결 개체와 연결된 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에 대한 포인터입니다.

## <a name="cinternetconnectionoperator-hinternet"></a><a name="operator_hinternet"></a>C인터넷연결::연산자 HINTERNET

이 연산자를 사용하여 현재 인터넷 세션에 대한 API 수준 핸들을 가져옵니다.

```
operator HINTERNET() const;
```

## <a name="see-also"></a>참고 항목

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
