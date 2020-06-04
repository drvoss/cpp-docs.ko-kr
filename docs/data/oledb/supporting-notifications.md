---
title: 알림 지원
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- events [C++], notifications in OLE DB
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB provider templates, notifications
- OLE DB providers, notifications
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
ms.openlocfilehash: d29f84a0a5b33d55c0a04a4c758050cf9746f72a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209556"
---
# <a name="supporting-notifications"></a>알림 지원

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>공급자 및 소비자에 대 한 연결 지점 인터페이스 구현

알림을 구현 하려면 공급자 클래스가 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) 및 [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md)에서 상속 해야 합니다.

`IRowsetNotifyCP` 연결 지점 인터페이스 [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))에 대 한 공급자 사이트를 구현 합니다. `IRowsetNotifyCP`는 연결 `IID_IRowsetNotify` 지점에 대 한 수신기에서 행 집합 내용에 대 한 변경 내용을 알리기 위해 브로드캐스트 함수를 구현 합니다.

또한 소비자가 알림을 처리할 수 있도록 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) 를 사용 하 여 소비자 (싱크 라고도 함)에 `IRowsetNotify`을 구현 하 고 등록 해야 합니다. 소비자에 연결 지점 인터페이스를 구현 하는 방법에 대 한 자세한 내용은 [알림 받기](../../data/oledb/receiving-notifications.md)를 참조 하세요.

또한 클래스는 다음과 같이 연결 지점 항목을 정의 하는 맵을 포함 해야 합니다.

```cpp
BEGIN_CONNECTION_POINT_MAP
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)
END_CONNECTION_POINT_MAP
```

## <a name="adding-irowsetnotify"></a>IRowsetNotify 추가

`IRowsetNotify`추가 하려면 상속 체인에 `IConnectionPointContainerImpl<rowset-name>` 및 `IRowsetNotifyCP<rowset-name>`를 추가 해야 합니다.

예를 들어 [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)의 `RUpdateRowset`에 대 한 상속 체인은 다음과 같습니다.

> [!NOTE]
> 샘플 코드가 여기에 표시된 것과 다를 수도 있습니다. 샘플 코드가 더 최신 버전입니다.

```cpp
///////////////////////////////////////////////////////////////////////////
// class RUpdateRowset (in rowset.h)

class RUpdateRowset :
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,
         CAtlArray< CAgentMan, CAtlArray<CAgentMan>>, CSimpleRow,
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll >>,
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,
      public IConnectionPointContainerImpl<RUpdateRowset>,
      public IRowsetNotifyCP<RUpdateRowset>
```

### <a name="setting-com-map-entries"></a>COM 맵 항목 설정

또한 다음을 행 집합의 COM 맵에 추가 해야 합니다.

```cpp
COM_INTERFACE_ENTRY(IConnectionPointContainer)
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)
```

이러한 매크로를 사용 하면 연결 지점 컨테이너 (`IRowsetNotify`의 기본)에 대해 `QueryInterface`를 호출 하는 모든 사용자가 공급자에서 요청 된 인터페이스를 찾을 수 있습니다. 연결 지점의 사용 방법에 대 한 예제는 ATL POLYGON 샘플 및 자습서를 참조 하세요.

### <a name="setting-connection-point-map-entries"></a>연결 지점 맵 항목 설정

연결 지점 맵도 추가 해야 합니다. 다음과 유사 하 게 표시 됩니다.

```cpp
BEGIN_CONNECTION_POINT_MAP(rowset-name)
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))
END_CONNECTION_POINT_MAP()
```

이 연결 지점 맵을 사용 하면 `IRowsetNotify` 인터페이스를 찾는 구성 요소가 공급자에서 찾을 수 있습니다.

### <a name="setting-properties"></a>속성 설정

또한 공급자에 다음 속성을 추가 해야 합니다. 지원 되는 인터페이스에 따라 속성을 추가 하기만 하면 됩니다.

|속성|지원 되는 경우 추가|
|--------------|------------------------|
|DBPROP_IConnectionPointContainer|항상|
|DBPROP_NOTIFICATIONGRANULARITY|항상|
|DBPROP_NOTIFICATIONPHASES|항상|
|DBPROP_NOTIFYCOLUMNSET|`IRowsetChange`|
|DBPROP_NOTIFYROWDELETE|`IRowsetChange`|
|DBPROP_NOTIFYROWINSERT|`IRowsetChange`|
|DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE|항상|
|DBPROP_NOTIFYROWFIRSTCHANGE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWSETRELEASE|항상|
|DBPROP_NOTIFYROWUNDOCHANGE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUNDODELETE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUNDOINSERT|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUPDATE|`IRowsetUpdate`|

알림에 대 한 대부분의 구현은 OLE DB 공급자 템플릿에 이미 포함 되어 있습니다. 상속 체인에 `IRowsetNotifyCP`를 추가 하지 않으면 컴파일러가 컴파일 스트림에서 해당 코드를 모두 제거 하 여 코드 크기를 더 작게 만듭니다.

## <a name="see-also"></a>참고 항목

[고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)
