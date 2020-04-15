---
title: CSocketAddr 클래스
ms.date: 10/22/2018
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
ms.openlocfilehash: 66d33d62212389a2b0f318250c1c16a99167c6eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330687"
---
# <a name="csocketaddr-class"></a>CSocketAddr 클래스

이 클래스는 호스트 이름을 호스트 주소로 변환하는 방법을 제공하여 IPv4 및 IPV6 형식을 모두 지원합니다.

## <a name="syntax"></a>구문

```
class CSocketAddr
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C소켓 애드버:::C소켓 애드버](#csocketaddr)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C소켓 애드:::찾기 애드](#findaddr)|제공된 호스트 이름을 호스트 주소로 변환하려면 이 메서드를 호출합니다.|
|[C소켓 애드러::FindINET4Addr](#findinet4addr)|이 메서드를 호출하여 IPv4 호스트 이름을 호스트 주소로 변환합니다.|
|[C소켓 애드러::FindINET6Addr](#findinet6addr)|이 메서드를 호출하여 IPv6 호스트 이름을 호스트 주소로 변환합니다.|
|[C소켓 애드너::GetAddrInfo](#getaddrinfo)|이 메서드를 호출하여 목록의 특정 `addrinfo` 요소에 대한 포인터를 반환합니다.|
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|이 메서드를 호출하여 목록에 `addrinfo` 대한 포인터를 반환합니다.|

## <a name="remarks"></a>설명

이 클래스는 라이브러리의 Windows 소켓 API 함수 및 소켓 래퍼와 함께 사용할 네트워크 주소를 찾기 위한 IP 버전에 구애받지 않는 접근 방식을 제공합니다.

네트워크 주소를 조회하는 데 사용되는 이 클래스의 멤버는 Win32 API 함수 [getaddrinfo를](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)사용합니다. 함수의 ANSI 또는 유니코드 버전은 코드가 ANSI 또는 UNICODE에 대해 컴파일되는지 여부에 따라 호출됩니다.

이 클래스는 IPv4 및 IPv6 네트워크 주소를 모두 지원합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsocket.h

## <a name="csocketaddrcsocketaddr"></a><a name="csocketaddr"></a>C소켓 애드버:::C소켓 애드버

생성자입니다.

```
CSocketAddr();
```

### <a name="remarks"></a>설명

새 `CSocketAddr` 개체를 만들고 호스트에 대 한 응답 정보를 포함 하는 링크 된 목록을 초기화 합니다.

## <a name="csocketaddrfindaddr"></a><a name="findaddr"></a>C소켓 애드:::찾기 애드

제공된 호스트 이름을 호스트 주소로 변환하려면 이 메서드를 호출합니다.

```
int FindAddr(
    const TCHAR *szHost,
    const TCHAR *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const TCHAR *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```

### <a name="parameters"></a>매개 변수

*szHost*<br/>
호스트 이름 또는 점선 IP 주소입니다.

*szPortOr서비스 이름*<br/>
호스트의 포트 번호 또는 서비스 이름입니다.

*n포트노*<br/>
포트 번호.

*플래그*<br/>
0 또는 AI_PASSIVE, AI_CANONNAME 또는 AI_NUMERICHOST 조합.

*addr_family*<br/>
주소 가족(예: PF_INET).

*sock_type*<br/>
소켓 유형(예: SOCK_STREAM).

*ai_proto*<br/>
프로토콜(예: IPPROTO_IP 또는 IPPROTO_IPV6).

### <a name="return-value"></a>Return Value

주소가 성공적으로 계산되면 0을 반환합니다. 실패 시 0이 아닌 Windows 소켓 오류 코드를 반환합니다. 성공하면 계산된 주소는 을 사용하여 `CSocketAddr::GetAddrInfoList` 참조할 수 있는 `CSocketAddr::GetAddrInfo`링크된 목록에 저장됩니다.

### <a name="remarks"></a>설명

호스트 이름 매개 변수는 IPv4 또는 IPv6 형식일 수 있습니다. 이 메서드는 Win32 API 함수 [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) 변환을 수행 하도록 호출 합니다.

## <a name="csocketaddrfindinet4addr"></a><a name="findinet4addr"></a>C소켓 애드러::FindINET4Addr

이 메서드를 호출하여 IPv4 호스트 이름을 호스트 주소로 변환합니다.

```
int FindINET4Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>매개 변수

*szHost*<br/>
호스트 이름 또는 점선 IP 주소입니다.

*n포트노*<br/>
포트 번호.

*플래그*<br/>
0 또는 AI_PASSIVE, AI_CANONNAME 또는 AI_NUMERICHOST 조합.

*sock_type*<br/>
소켓 유형(예: SOCK_STREAM).

### <a name="return-value"></a>Return Value

주소가 성공적으로 계산되면 0을 반환합니다. 실패 시 0이 아닌 Windows 소켓 오류 코드를 반환합니다. 성공하면 계산된 주소는 을 사용하여 `CSocketAddr::GetAddrInfoList` 참조할 수 있는 `CSocketAddr::GetAddrInfo`링크된 목록에 저장됩니다.

### <a name="remarks"></a>설명

이 메서드는 Win32 API 함수 [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) 변환을 수행 하도록 호출 합니다.

## <a name="csocketaddrfindinet6addr"></a><a name="findinet6addr"></a>C소켓 애드러::FindINET6Addr

이 메서드를 호출하여 IPv6 호스트 이름을 호스트 주소로 변환합니다.

```
int FindINET6Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>매개 변수

*szHost*<br/>
호스트 이름 또는 점선 IP 주소입니다.

*n포트노*<br/>
포트 번호.

*플래그*<br/>
0 또는 AI_PASSIVE, AI_CANONNAME 또는 AI_NUMERICHOST 조합.

*sock_type*<br/>
소켓 유형(예: SOCK_STREAM).

### <a name="return-value"></a>Return Value

주소가 성공적으로 계산되면 0을 반환합니다. 실패 시 0이 아닌 Windows 소켓 오류 코드를 반환합니다. 성공하면 계산된 주소는 을 사용하여 `CSocketAddr::GetAddrInfoList` 참조할 수 있는 `CSocketAddr::GetAddrInfo`링크된 목록에 저장됩니다.

### <a name="remarks"></a>설명

이 메서드는 Win32 API 함수 [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) 변환을 수행 하도록 호출 합니다.

## <a name="csocketaddrgetaddrinfo"></a><a name="getaddrinfo"></a>C소켓 애드너::GetAddrInfo

이 메서드를 호출하여 목록의 특정 `addrinfo` 요소에 대한 포인터를 반환합니다.

```
addrinfo* const GetAddrInfo(int nIndex = 0) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[addrinfo](/windows/win32/api/ws2def/ns-ws2def-addrinfow) 목록의 특정 요소에 대한 참조입니다.

### <a name="return-value"></a>Return Value

호스트에 대한 `addrinfo` 응답 정보가 포함된 연결된 목록에서 *nIndex에서* 참조하는 구조에 대한 포인터를 반환합니다.

## <a name="csocketaddrgetaddrinfolist"></a><a name="getaddrinfolist"></a>CSocketAddr::GetAddrInfoList

이 메서드를 호출하여 목록에 `addrinfo` 대한 포인터를 반환합니다.

```
addrinfo* const GetAddrInfoList() const;
```

### <a name="return-value"></a>Return Value

호스트에 대한 응답 정보를 `addrinfo` 포함하는 하나 이상의 구조체의 연결된 목록에 대한 포인터입니다. 자세한 내용은 [addrinfo 구조를](/windows/win32/api/ws2def/ns-ws2def-addrinfow)참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
