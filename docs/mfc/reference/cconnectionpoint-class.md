---
title: C커넥포인트 클래스
ms.date: 11/04/2016
f1_keywords:
- CConnectionPoint
- AFXDISP/CConnectionPoint
- AFXDISP/CConnectionPoint::CConnectionPoint
- AFXDISP/CConnectionPoint::GetConnections
- AFXDISP/CConnectionPoint::GetContainer
- AFXDISP/CConnectionPoint::GetIID
- AFXDISP/CConnectionPoint::GetMaxConnections
- AFXDISP/CConnectionPoint::GetNextConnection
- AFXDISP/CConnectionPoint::GetStartPosition
- AFXDISP/CConnectionPoint::OnAdvise
- AFXDISP/CConnectionPoint::QuerySinkInterface
helpviewer_keywords:
- CConnectionPoint [MFC], CConnectionPoint
- CConnectionPoint [MFC], GetConnections
- CConnectionPoint [MFC], GetContainer
- CConnectionPoint [MFC], GetIID
- CConnectionPoint [MFC], GetMaxConnections
- CConnectionPoint [MFC], GetNextConnection
- CConnectionPoint [MFC], GetStartPosition
- CConnectionPoint [MFC], OnAdvise
- CConnectionPoint [MFC], QuerySinkInterface
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
ms.openlocfilehash: ce72c156ab31b742a42d2960923fc56afff656c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369436"
---
# <a name="cconnectionpoint-class"></a>C커넥포인트 클래스

"연결점"이라고 하는 다른 OLE 개체와 통신하는 데 사용하는 특별한 형식의 인터페이스를 정의합니다.

## <a name="syntax"></a>구문

```
class CConnectionPoint : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C커넥션 포인트::C커넥션 포인트](#cconnectionpoint)|`CConnectionPoint` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C커넥션 포인트::연결 얻기](#getconnections)|연결 맵의 모든 연결 점을 검색합니다.|
|[C커넥션 포인트::GetContainer](#getcontainer)|연결 맵을 소유하는 컨트롤의 컨테이너를 검색합니다.|
|[C커넥션 포인트::GetIID](#getiid)|연결 지점의 인터페이스 ID를 검색합니다.|
|[C커넥션 포인트::겟맥스커넥션](#getmaxconnections)|컨트롤에서 지원하는 최대 연결 지점 수를 검색합니다.|
|[C커넥션 포인트::GetNext연결](#getnextconnection)|*pos에서*연결 요소에 대한 포인터를 검색합니다.|
|[C커넥스포인트::시작 위치](#getstartposition)|호출에 전달할 수 있는 POSITION 값을 반환하여 `GetNextConnection` 맵 반복을 시작합니다.|
|[C커넥션 포인트::온어](#onadvise)|연결을 설정하거나 끊을 때 프레임워크에서 호출합니다.|
|[C커넥스포인트::쿼리싱크인터페이스](#querysinkinterface)|요청된 싱크 인터페이스에 대한 포인터를 검색합니다.|

## <a name="remarks"></a>설명

OLE 컨트롤의 기능을 구현하고 노출하는 데 사용되는 일반 OLE 인터페이스와 달리 연결 지점은 이벤트 발생 및 변경 알림과 같은 다른 개체에 대한 작업을 시작할 수 있는 나가는 인터페이스를 구현합니다.

연결은 "source"라고 하는 인터페이스를 호출하는 개체와 "싱크"라고 하는 인터페이스를 구현하는 개체의 두 부분으로 구성됩니다. 연결 점을 노출하면 소스가 싱크를 통해 자체에 대한 연결을 설정할 수 있습니다. 연결 지점 메커니즘을 통해 소스 개체는 멤버 함수 집합의 싱크 구현에 대한 포인터를 가져옵니다. 예를 들어 싱크에 의해 구현된 이벤트를 발생시키기 위해 소스는 싱크구현의 적절한 메서드를 호출할 수 있습니다.

기본적으로 `COleControl`-derived 클래스는 이벤트에 대한 연결 점과 속성 변경 알림에 대한 연결 지점의 두 가지 연결을 구현합니다. 이러한 연결은 각각 이벤트 발생 및 속성 값이 변경될 때 싱크(예: 컨트롤의 컨테이너)를 알리는 데 사용됩니다. OLE 컨트롤은 추가 연결 지점을 구현하기 위한 지원도 제공됩니다. 제어 클래스에서 구현된 각 추가 연결 지점에 대해 연결 지점을 구현하는 "연결 부분"을 선언해야 합니다. 하나 이상의 연결 지점을 구현하는 경우 컨트롤 클래스에서 단일 "연결 맵"을 선언해야 합니다.

다음 예제에서는 두 개의 코드 조각으로 구성된 `Sample` OLE 컨트롤에 대한 간단한 연결 맵과 하나의 연결 지점을 보여 줍니다. 두 번째는 이 맵과 점을 구현합니다. 첫 번째 조각은 **보호된** 섹션 아래에 컨트롤 클래스의 선언에 삽입됩니다.

[!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]

BEGIN_CONNECTION_PART 및 END_CONNECTION_PART 매크로는 이 `XSampleConnPt` 특정 연결 `CConnectionPoint`지점을 구현하는 포함된 클래스(파생)를 선언합니다. 멤버 `CConnectionPoint` 함수를 재정의하거나 고유한 멤버 함수를 추가하려면 이 두 매크로 간에 해당 함수를 선언합니다. 예를 들어 CONNECTION_IID 매크로는 `CConnectionPoint::GetIID` 이 두 매크로 사이에 배치될 때 멤버 함수를 재정의합니다.

두 번째 코드 조각이 구현 파일에 삽입됩니다(. 제어 클래스의 CPP)를 참조하십시오. 이 코드는 추가 연결 지점을 `SampleConnPt`포함하는 연결 맵을 구현합니다.

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]

이러한 코드 조각이 삽입되면 샘플 OLE 컨트롤은 `ISampleSink` 인터페이스에 대한 연결 지점을 노출합니다.

일반적으로 연결 점은 동일한 인터페이스에 연결된 여러 싱크로 브로드캐스트할 수 있는 "멀티캐스팅"을 지원합니다. 다음 코드 조각은 연결 지점의 각 싱크를 반복하여 멀티 캐스팅을 수행하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

이 예제는 에 대한 호출을 `SampleConnPt` 사용하여 연결 지점의 현재 연결 집합을 `CConnectionPoint::GetConnections`검색합니다. 그런 다음 연결을 통해 계속 `ISampleSink::SinkFunc` 하여 모든 활성 연결을 호출합니다.

사용에 `CConnectionPoint`대한 자세한 내용은 [연결 지점](../../mfc/connection-points.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CConnectionPoint`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="cconnectionpointcconnectionpoint"></a><a name="cconnectionpoint"></a>C커넥션 포인트::C커넥션 포인트

`CConnectionPoint` 개체를 생성합니다.

```
CConnectionPoint();
```

## <a name="cconnectionpointgetconnections"></a><a name="getconnections"></a>C커넥션 포인트::연결 얻기

연결 점에 대한 모든 활성 연결을 검색하려면 이 함수를 호출합니다.

```
const CPtrArray* GetConnections();
```

### <a name="return-value"></a>Return Value

활성 연결(싱크)의 배열에 대한 포인터입니다. 배열의 일부 포인터는 NULL일 수 있습니다. 이 배열의 NULL이 아닌 각 포인터는 캐스트 연산자를 사용하여 싱크 인터페이스에 대한 포인터로 안전하게 변환할 수 있습니다.

## <a name="cconnectionpointgetcontainer"></a><a name="getcontainer"></a>C커넥션 포인트::GetContainer

연결 점에 `IConnectionPointContainer` 대한 검색을 위해 프레임워크에서 호출합니다.

```
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```

### <a name="return-value"></a>Return Value

성공하면 컨테이너에 대한 포인터; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 함수는 일반적으로 BEGIN_CONNECTION_PART 매크로에 의해 구현됩니다.

## <a name="cconnectionpointgetiid"></a><a name="getiid"></a>C커넥션 포인트::GetIID

연결 지점의 인터페이스 ID를 검색하기 위해 프레임워크에서 호출합니다.

```
virtual REFIID GetIID() = 0;
```

### <a name="return-value"></a>Return Value

연결 지점의 인터페이스 ID에 대한 참조입니다.

### <a name="remarks"></a>설명

이 연결 지점에 대한 인터페이스 ID를 반환하려면 이 함수를 재정의합니다.

## <a name="cconnectionpointgetmaxconnections"></a><a name="getmaxconnections"></a>C커넥션 포인트::겟맥스커넥션

연결 점에서 지원 되는 연결의 최대 수를 검색 하는 프레임 워크에 의해 호출 됩니다.

```
virtual int GetMaxConnections();
```

### <a name="return-value"></a>Return Value

컨트롤에서 지원하는 최대 연결 수 또는 제한이 없는 경우 -1입니다.

### <a name="remarks"></a>설명

기본 구현은 -1을 반환하여 제한을 표시하지 않습니다.

컨트롤에 연결할 수 있는 싱크 수를 제한하려면 이 함수를 재정의합니다.

## <a name="cconnectionpointgetnextconnection"></a><a name="getnextconnection"></a>C커넥션 포인트::GetNext연결

*pos에서*연결 요소에 대한 포인터를 검색합니다.

```
LPUNKNOWN GetNextConnection(POSITION& pos) const;
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
이전 `GetNextConnection` 또는 [GetStartPosition](#getstartposition) 호출에서 반환된 위치 값에 대한 참조를 지정합니다.

### <a name="return-value"></a>Return Value

*pos*또는 NULL에 의해 지정된 연결 요소에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 연결 맵의 모든 요소를 반복하는 데 가장 유용합니다. 반복할 때 이 함수에서 반환된 NULLs를 건너뜁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

## <a name="cconnectionpointgetstartposition"></a><a name="getstartposition"></a>C커넥스포인트::시작 위치

[GetNextConnection](#getnextconnection) 호출에 전달할 수 있는 위치 값을 반환 하여 맵 반복을 시작합니다.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Return Value

맵을 반복하기 위한 시작 위치를 나타내는 위치 값; 또는 맵이 비어 있으면 NULL이 됩니다.

### <a name="remarks"></a>설명

반복 시퀀스는 예측할 수 없습니다. 따라서 "맵의 첫 번째 요소"는 특별한 의미가 없습니다.

### <a name="example"></a>예제

  [CConnectionPoint::GetNextConnection](#getnextconnection)에 대한 예제를 참조하십시오.

## <a name="cconnectionpointonadvise"></a><a name="onadvise"></a>C커넥션 포인트::온어

연결이 설정되거나 끊어질 때 프레임워크에서 호출됩니다.

```
virtual void OnAdvise(BOOL bAdvise);
```

### <a name="parameters"></a>매개 변수

*bAdvise*<br/>
TRUE, 연결이 설정되는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행하지 않습니다.

싱크가 연결되거나 연결 지점에서 연결을 끊을 때 알림을 받으면 이 기능을 재정의합니다.

## <a name="cconnectionpointquerysinkinterface"></a><a name="querysinkinterface"></a>C커넥스포인트::쿼리싱크인터페이스

요청된 싱크 인터페이스에 대한 포인터를 검색합니다.

```
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,
    void** ppInterface);
```

### <a name="parameters"></a>매개 변수

*펀크싱크*<br/>
요청되는 싱크 인터페이스의 식별자입니다.

*ppInterface*<br/>
*pUnkSink로*식별된 인터페이스 포인터에 대한 포인터입니다. 개체가 이 인터페이스를 \* 지원하지 않으면 *ppInterface가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="see-also"></a>참고 항목

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
