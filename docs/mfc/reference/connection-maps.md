---
title: 연결 맵
ms.date: 11/04/2016
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
ms.openlocfilehash: 947cd09023ef4028a32db8e2e4e8b33f7e04e0dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374797"
---
# <a name="connection-maps"></a>연결 맵

OLE 컨트롤은 다른 응용 프로그램에 인터페이스를 노출할 수 있습니다. 이러한 인터페이스는 컨테이너에서 해당 컨트롤에 대한 액세스만 허용합니다. OLE 컨트롤이 다른 OLE 개체의 외부 인터페이스에 액세스하려는 경우 연결 지점을 설정해야 합니다. 이 연결 지점을 사용하면 이벤트 맵 또는 알림 기능과 같은 외부 디스패치 맵에 대한 제어 나가는 액세스를 사용할 수 있습니다.

Microsoft 재단 클래스 라이브러리는 연결 지점을 지원하는 프로그래밍 모델을 제공합니다. 이 모델에서 "연결 맵"은 OLE 컨트롤의 인터페이스 또는 연결 점을 지정하는 데 사용됩니다. 연결 맵에는 각 연결 점에 대해 하나의 매크로가 포함되어 있습니다. 연결 맵에 대한 자세한 내용은 [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) 클래스를 참조하십시오.

일반적으로 컨트롤은 이벤트용 과 속성 알림용 연결 지점의 두 가지 연결 지점만 지원합니다. 이러한 작업은 기본 `COleControl` 클래스에 의해 구현되며 컨트롤 작성기에서 추가 작업을 필요로 하지 않습니다. 클래스에서 구현하려는 추가 연결 지점을 수동으로 추가해야 합니다. 연결 맵 및 포인트를 지원하기 위해 MFC는 다음과 같은 매크로를 제공합니다.

### <a name="connection-map-declaration-and-demarcation"></a>연결 맵 선언 및 경계

|||
|-|-|
|[BEGIN_CONNECTION_PART](#begin_connection_part)|추가 연결 점을 구현하는 포함된 클래스를 선언합니다(클래스 선언에 사용해야 합니다).|
|[END_CONNECTION_PART](#end_connection_part)|연결 지점의 선언을 종료합니다(클래스 선언에 사용해야 합니다).|
|[CONNECTION_IID](#connection_iid)|컨트롤의 연결 지점의 인터페이스 ID를 지정합니다.|
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|연결 맵이 클래스에서 사용됨을 선언합니다(클래스 선언에 사용해야 합니다).|
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|연결 맵의 정의를 시작합니다(클래스 구현에서 사용해야 합니다).|
|[END_CONNECTION_MAP](#end_connection_map)|연결 맵의 정의를 종료합니다(클래스 구현에서 사용해야 합니다).|
|[CONNECTION_PART](#connection_part)|컨트롤의 연결 맵에서 연결 점을 지정합니다.|

다음 기능은 연결 점을 사용하여 연결을 설정하고 연결을 끊는 싱크를 지원합니다.

### <a name="initializationtermination-of-connection-points"></a>연결 점의 초기화/종료

|||
|-|-|
|[AfxConnectionAdvise](#afxconnectionadvise)|원본과 싱크 사이의 연결을 설정합니다.|
|[AfxConnectionUnadvise](#afxconnectionunadvise)|원본과 싱크 사이의 연결을 끊습니다.|

## <a name="begin_connection_part"></a><a name="begin_connection_part"></a>BEGIN_CONNECTION_PART

BEGIN_CONNECTION_PART 매크로를 사용하여 이벤트 및 속성 알림 연결 지점 을 벗어난 추가 연결 점의 정의를 시작합니다.

```
BEGIN_CONNECTION_PART(theClass, localClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
연결 지점이 있는 컨트롤 클래스의 이름을 지정합니다.

*localClass*<br/>
연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.

### <a name="remarks"></a>설명

클래스의 멤버 함수를 정의하는 선언(.h) 파일에서 BEGIN_CONNECTION_PART 매크로로 연결 점을 시작한 다음 CONNECTION_IID 매크로 및 구현하려는 다른 멤버 함수를 추가하고 END_CONNECTION_PART 매크로로 연결 지점 맵을 완료합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="end_connection_part"></a><a name="end_connection_part"></a>END_CONNECTION_PART

연결 지점의 선언을 종료합니다.

```
END_CONNECTION_PART(localClass)
```

### <a name="parameters"></a>매개 변수

*localClass*<br/>
연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="connection_iid"></a><a name="connection_iid"></a>CONNECTION_IID

BEGIN_CONNECTION_PART 매크로와 END_CONNECTION_PART 매크로 간에 사용하여 OLE 컨트롤에서 지원하는 연결 지점에 대한 인터페이스 ID를 정의합니다.

```
CONNECTION_IID(iid)
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
연결 점에서 호출되는 인터페이스의 인터페이스 ID입니다.

### <a name="remarks"></a>설명

*iid* 인수는 연결 지점이 연결된 싱크에서 호출할 인터페이스를 식별하는 데 사용되는 인터페이스 ID입니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]

은 인터페이스를 호출하는 연결 `ISinkInterface` 점을 지정합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="declare_connection_map"></a><a name="declare_connection_map"></a>DECLARE_CONNECTION_MAP

프로그램의 `COleControl`각 파생 클래스는 컨트롤이 지원하는 추가 연결 점을 지정하는 연결 맵을 제공할 수 있습니다.

```
DECLARE_CONNECTION_MAP()
```

### <a name="remarks"></a>설명

컨트롤이 추가 포인트를 지원하는 경우 클래스 선언 끝에 DECLARE_CONNECTION_MAP 매크로를 사용합니다. 그런 다음 클래스의 멤버 함수를 정의하는 .cpp 파일에서 BEGIN_CONNECTION_MAP 매크로를 사용하여 각 컨트롤의 연결 지점에 대해 매크로를 CONNECTION_PART END_CONNECTION_MAP 매크로를 사용하여 연결 맵의 끝을 선언합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="begin_connection_map"></a><a name="begin_connection_map"></a>BEGIN_CONNECTION_MAP

프로그램에서 각 `COleControl` 파생 클래스는 컨트롤을 지원하는 연결 포인트를 지정하기 위해 연결 맵을 제공할 수 있습니다.

```
BEGIN_CONNECTION_MAP(theClass, theBase)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 연결을 매핑할 컨트롤 클래스의 이름을 지정합니다.

*theBase*<br/>
의 기본 클래스의 이름을 *지정합니다Class*.

### <a name="remarks"></a>설명

구현에서 (. 클래스의 멤버 함수를 정의하는 CPP) 파일은 BEGIN_CONNECTION_MAP 매크로로 연결 맵을 시작한 다음 [CONNECTION_PART](#connection_part) 매크로를 사용하여 각 연결 지점에 대한 매크로 항목을 추가합니다. 마지막으로 [END_CONNECTION_MAP](#end_connection_map) 매크로로 연결 맵을 완료합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="end_connection_map"></a><a name="end_connection_map"></a>END_CONNECTION_MAP

연결 맵의 정의를 끝냅니다.

```
END_CONNECTION_MAP()
```

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="connection_part"></a><a name="connection_part"></a>CONNECTION_PART

OLE 컨트롤의 연결 점을 특정 인터페이스 ID에 매핑합니다.

```
CONNECTION_PART(theClass, iid, localClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
연결 지점이 있는 컨트롤 클래스의 이름을 지정합니다.

*Iid*<br/>
연결 점에서 호출되는 인터페이스의 인터페이스 ID입니다.

*localClass*<br/>
연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.

### <a name="remarks"></a>설명

다음은 그 예입니다.

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]

인터페이스를 호출하는 연결 지점이 있는 연결 `IID_ISinkInterface` 맵을 구현합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="afxconnectionadvise"></a><a name="afxconnectionadvise"></a>Afx커넥션어드

이 함수를 호출하여 *pUnkSrc에*의해 지정된 소스와 *pUnkSink에*의해 지정된 싱크 사이의 연결을 설정합니다.

```
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD FAR* pdwCookie);
```

### <a name="parameters"></a>매개 변수

*펀크 스크르크*<br/>
인터페이스를 호출하는 개체에 대한 포인터입니다.

*펀크싱크*<br/>
인터페이스를 구현하는 개체에 대한 포인터입니다.

*Iid*<br/>
연결의 인터페이스 ID입니다.

*bRefCount*<br/>
TRUE는 연결을 만들면 *pUnkSink의* 참조 수가 증가해야 한다는 것을 나타냅니다. FALSE는 참조 수를 증분해서는 안 있음을 나타냅니다.

*pdwCookie*<br/>
연결 식별자가 반환되는 DWORD에 대한 포인터입니다. 이 값은 연결을 끊을 때 `AfxConnectionUnadvise` *dwCookie* 매개 변수로 전달되어야 합니다.

### <a name="return-value"></a>Return Value

연결이 설정된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="afxconnectionunadvise"></a><a name="afxconnectionunadvise"></a>아fx커넥션언어드

이 함수를 호출하여 *pUnkSrc에*의해 지정된 소스와 *pUnkSink에*의해 지정된 싱크 사이의 연결을 끊습니다.

```
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD dwCookie);
```

### <a name="parameters"></a>매개 변수

*펀크 스크르크*<br/>
인터페이스를 호출하는 개체에 대한 포인터입니다.

*펀크싱크*<br/>
인터페이스를 구현하는 개체에 대한 포인터입니다.

*Iid*<br/>
연결 지점 인터페이스의 인터페이스 ID입니다.

*bRefCount*<br/>
TRUE는 연결을 연결 해제하면 *pUnkSink의* 참조 수가 감소되어야 한다는 것을 나타냅니다. FALSE는 참조 수를 감소시키지 않아야 한다는 것을 나타냅니다.

*dwCookie*<br/>
에서 반환된 `AfxConnectionAdvise`연결 식별자입니다.

### <a name="return-value"></a>Return Value

연결이 끊어진 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
