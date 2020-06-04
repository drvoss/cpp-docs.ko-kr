---
title: IRowsetNotifyCP 클래스
ms.date: 11/04/2016
f1_keywords:
- IRowsetNotifyCP
- Fire_OnFieldChange
- ATL::IRowsetNotifyCP::Fire_OnFieldChange
- ATL.IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP::Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnRowChange
- ATL.IRowsetNotifyCP.Fire_OnRowChange
- Fire_OnRowChange
- ATL::IRowsetNotifyCP::Fire_OnRowChange
- IRowsetNotifyCP::Fire_OnRowChange
- Fire_OnRowsetChange
- IRowsetNotifyCP::Fire_OnRowsetChange
- IRowsetNotifyCP.Fire_OnRowsetChange
- ATL::IRowsetNotifyCP::Fire_OnRowsetChange
- ATL.IRowsetNotifyCP.Fire_OnRowsetChange
helpviewer_keywords:
- IRowsetNotifyCP class
- Fire_OnFieldChange method
- Fire_OnRowChange method
- Fire_OnRowsetChange method
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
ms.openlocfilehash: fa85bc7947b3b446ec7c6d3fdb0d7b62d308fb53
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210329"
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP 클래스

연결 지점 인터페이스 [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))에 대 한 공급자 사이트를 구현 합니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class ReentrantEventSync = CComSharedMutex>
class IRowsetNotifyCP :
   public IConnectionPointImpl<
      T,
      piid = &__uuidof(IRowsetNotify),
      CComDynamicUnkArray DynamicUnkArray>,
   public ReentrantEventSync
```

### <a name="parameters"></a>매개 변수

*T*<br/>
`IRowsetNotifyCP`에서 파생 된 클래스입니다.

*ReentrantEventSync*<br/>
재진입을 지 원하는 뮤텍스 클래스입니다. 기본값은 `CComSharedMutex`입니다. 뮤텍스는 한 스레드가 한 리소스에 상호 배타적으로 액세스 하도록 허용 하는 동기화 개체입니다.

*piid*<br/>
`IRowsetNotify` 연결 지점 인터페이스에 대 한 인터페이스 ID 포인터 (`IID*`)입니다. 기본값은 `&__uuidof(IRowsetNotify)`입니다.

*DynamicUnkArray*<br/>
클라이언트 싱크 인터페이스에 대 한 `IUnknown` 포인터의 동적으로 할당 된 배열인 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)형식의 배열입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[Fire_OnFieldChange](#onfieldchange)|열의 값에 대 한 변경 사항을 소비자에 게 알립니다.|
|[Fire_OnRowChange](#onrowchange)|행에 영향을 주는 변경 사항을 소비자에 게 알립니다.|
|[Fire_OnRowsetChange](#onrowsetchange)|전체 행 집합에 영향을 주는 변경 사항을 소비자에 게 알립니다.|

## <a name="remarks"></a>주의

`IRowsetNotifyCP`는 연결 `IID_IRowsetNotify` 지점에 대 한 수신기에서 행 집합 내용에 대 한 변경 내용을 알리기 위해 브로드캐스트 함수를 구현 합니다.

소비자가 알림을 처리할 수 있도록 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) 를 사용 하 여 소비자 ("싱크" 라고도 함)에 `IRowsetNotify`을 구현 하 고 등록 해야 합니다. 소비자에서 연결 지점 인터페이스 구현에 대 한 [알림 받기](../../data/oledb/receiving-notifications.md) 를 참조 하세요.

알림 구현에 대 한 자세한 내용은 [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)의 "알림 지원"을 참조 하십시오.

## <a name="irowsetnotifycpfire_onfieldchange"></a><a name="onfieldchange"></a>IRowsetNotifyCP:: Fire_OnFieldChange

열 값에 대 한 변경 사항을 소비자에 게 알리기 위해 [Onfieldchange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 이벤트를 브로드캐스트합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Fire_OnFieldChange(IRowset* pRowset,
   HROW hRow,
   DBORDINAL cColumns,
   DBORDINAL* rgColumns,
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>매개 변수

*OLE DB 프로그래머 참조*에서 [IRowsetNotify:: onfieldchange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 를 참조 하세요.

## <a name="irowsetnotifycpfire_onrowchange"></a><a name="onrowchange"></a>IRowsetNotifyCP:: Fire_OnRowChange

연결 지점에 대 한 모든 수신기에 [Onrowchange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 이벤트를 브로드캐스팅하 `IID_IRowsetNotify` 하 여 행에 영향을 주는 변경 사항을 소비자에 게 알립니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Fire_OnRowChange(IRowset* pRowset,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>매개 변수

*OLE DB 프로그래머 참조*의 [IRowsetNotify:: onrowchange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 를 참조 하십시오.

## <a name="irowsetnotifycpfire_onrowsetchange"></a><a name="onrowsetchange"></a>IRowsetNotifyCP:: Fire_OnRowsetChange

[OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 이벤트를 연결 `IID_IRowsetNotify` 지점의 모든 수신기에 브로드캐스트합니다 .이를 통해 소비자는 전체 행 집합에 영향을 주는 변경 사항을 소비자에 게 알립니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>매개 변수

*OLE DB 프로그래머 참조*에서 [IRowsetNotify:: OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 를 참조 하세요.

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[알림 (COM)](/windows/win32/com/notifications)<br/>
[BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)<br/>
[END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)<br/>
[CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)<br/>
[업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)
