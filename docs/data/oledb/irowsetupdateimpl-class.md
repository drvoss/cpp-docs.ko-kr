---
title: IRowsetUpdateImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
- ATL.IRowsetUpdateImpl.GetOriginalData
- IRowsetUpdateImpl.GetOriginalData
- ATL::IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetPendingRows
- GetPendingRows
- IRowsetUpdateImpl.GetPendingRows
- ATL::IRowsetUpdateImpl::GetPendingRows
- ATL.IRowsetUpdateImpl.GetPendingRows
- ATL.IRowsetUpdateImpl.GetRowStatus
- IRowsetUpdateImpl::GetRowStatus
- IRowsetUpdateImpl.GetRowStatus
- ATL::IRowsetUpdateImpl::GetRowStatus
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
- SetData method
- GetOriginalData method
- GetPendingRows method
- GetRowStatus method
- Undo method
- Update method
- IsUpdateAllowed method
- m_mapCachedData
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
ms.openlocfilehash: 6347a42b9065239f768c6b50c430946393358df1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370741"
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl 클래스

[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85)) 인터페이스의 OLE DB 템플릿 구현입니다.

## <a name="syntax"></a>구문

```cpp
template <
   class T,
   class Storage,
   class UpdateArray = CAtlArray<Storage>,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>
>

class IRowsetUpdateImpl : public IRowsetChangeImpl<
   T,
   Storage,
   IRowsetUpdate,
   RowClass,
   MapClass>
```

### <a name="parameters"></a>매개 변수

*T*<br/>
에서 `IRowsetUpdateImpl`파생된 클래스입니다.

*스토리지*<br/>
사용자 레코드입니다.

*업데이트 배열*<br/>
행 집합을 업데이트하기 위한 캐시된 데이터가 포함된 배열입니다.

*로우 클래스*<br/>
`HROW`의 저장 장치입니다.

*맵 클래스*<br/>
공급자가 보유한 모든 행 핸들의 저장소 단위입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="interface-methods-used-with-irowsetchange"></a>인터페이스 방법(IRowsetChange와 함께 사용)

|||
|-|-|
|[Setdata](#setdata)|하나 이상의 열에서 데이터 값을 설정합니다.|

### <a name="interface-methods-used-with-irowsetupdate"></a>인터페이스 방법(IRowsetUpdate와 함께 사용)

|||
|-|-|
|[겟 오리지널데이터](#getoriginaldata)|보류 중인 변경 내용을 무시하고 데이터 원본으로 가장 최근에 전송되거나 데이터 원본에서 가져온 데이터를 가져옵니다.|
|[GetPendingRows](#getpendingrows)|보류 중인 변경 내용이 있는 행 목록을 반환합니다.|
|[겟로우 상태](#getrowstatus)|지정된 행의 상태를 반환합니다.|
|[취소](#undo)|마지막 가져오기 또는 업데이트 이후 행에 대한 모든 변경 내용을 취소합니다.|
|[업데이트](#update)|마지막 가져오기 또는 업데이트 이후 행에 대한 변경 내용을 전송합니다.|

### <a name="implementation-methods-callback"></a>구현 방법(콜백)

|||
|-|-|
|[IsUpdate허용됨](#isupdateallowed)|업데이트를 허용하기 전에 보안, 무결성 등을 확인하는 데 사용됩니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_mapCachedData](#mapcacheddata)|지연된 작업에 대한 원본 데이터를 포함합니다.|

## <a name="remarks"></a>설명

먼저 [IRowsetChange에](/previous-versions/windows/desktop/ms715790(v=vs.85))대한 설명서를 읽고 이해해야 합니다. 또한 데이터 설정에 대한 *OLE DB 프로그래머의 참조* 6장을 읽어야 합니다.

`IRowsetUpdateImpl`OLE DB `IRowsetUpdate` 인터페이스를 구현하여 소비자가 데이터 원본에 대한 `IRowsetChange` 변경 내용 전송을 지연시키고 전송 전에 변경 내용을 실행 취소할 수 있습니다.

> [!IMPORTANT]
> 공급자를 구현하기 전에 다음 설명서를 읽는 것이 좋습니다.

- [업데이터 제공자 만들기](../../data/oledb/creating-an-updatable-provider.md)

- OLE DB *프로그래머 의 참조* 6 장

- 또한 `RUpdateRowset` [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) 샘플에서 클래스가 어떻게 사용되는지 확인하십시오.

## <a name="irowsetupdateimplsetdata"></a><a name="setdata"></a>IRowset업데이트임플::셋데이터

하나 이상의 열에서 데이터 값을 설정합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>매개 변수

*올레 DB 프로그래머의 참조에서* [IRowsetChange::SetData를](/previous-versions/windows/desktop/ms721232(v=vs.85)) 참조하십시오.

### <a name="remarks"></a>설명

이 메서드는 [IRowsetChangeImpl:SetData](../../data/oledb/irowsetchangeimpl-setdata.md) 메서드를 재정의하지만 작업의 즉각적인 또는 지연된 처리를 허용하도록 원본 데이터의 캐싱을 포함합니다.

## <a name="irowsetupdateimplgetoriginaldata"></a><a name="getoriginaldata"></a>IRowset업데이트임플::겟오리지널데이터

보류 중인 변경 내용을 무시하고 데이터 원본으로 가장 최근에 전송되거나 데이터 원본에서 가져온 데이터를 가져옵니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (GetOriginalData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pData);
```

#### <a name="parameters"></a>매개 변수

[IRowsetUpdate::GetOriginalData](/previous-versions/windows/desktop/ms709947(v=vs.85)) *올레 DB 프로그래머의 참조*.

## <a name="irowsetupdateimplgetpendingrows"></a><a name="getpendingrows"></a>IRowset업데이트임플::GetPendingrows

보류 중인 변경 내용이 있는 행 목록을 반환합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (GetPendingRows )(HCHAPTER /* hReserved */,
   DBPENDINGSTATUS dwRowStatus,
   DBCOUNTITEM* pcPendingRows,
   HROW** prgPendingRows,
   DBPENDINGSTATUS** prgPendingStatus);
```

#### <a name="parameters"></a>매개 변수

*h예약*<br/>
【인】 [IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)). *hChapter*

다른 매개 변수에 대 한 [참조 IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)) *OLE DB 프로그래머의 참조*.

### <a name="remarks"></a>설명

자세한 내용은 [IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)) OLE *DB 프로그래머의 참조를*참조하십시오.

## <a name="irowsetupdateimplgetrowstatus"></a><a name="getrowstatus"></a>IRowset업데이트임플::겟로우상태

지정된 행의 상태를 반환합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBPENDINGSTATUS rgPendingStatus[]);
```

#### <a name="parameters"></a>매개 변수

*h예약*<br/>
【인】 [IRowsetUpdate::GetRowStatus의](/previous-versions/windows/desktop/ms724377(v=vs.85)) *hChapter* 매개 변수에 해당합니다.

다른 매개 변수에 대 한 [참조 IRowsetUpdate::GetRowStatus](/previous-versions/windows/desktop/ms724377(v=vs.85)) *OLE DB 프로그래머의 참조*.

## <a name="irowsetupdateimplundo"></a><a name="undo"></a>IRowset업데이트임플::취소

마지막 가져오기 또는 업데이트 이후 행에 대한 모든 변경 내용을 취소합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (Undo )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[ ],
   DBCOUNTITEM* pcRowsUndone,
   HROW** prgRowsUndone,
   DBROWSTATUS** prgRowStatus);
```

#### <a name="parameters"></a>매개 변수

*h예약*<br/>
【인】 [IRowsetUpdate::취소의](/previous-versions/windows/desktop/ms719655(v=vs.85)) *hChapter* 매개 변수에 해당 합니다.

*pcRowsUndone*<br/>
【아웃】 [IRowsetUpdate::취소의](/previous-versions/windows/desktop/ms719655(v=vs.85)) *pcRows* 매개 변수에 해당 합니다.

*prgRowsUndone*<br/>
【인】 [IRowsetUpdate::취소의](/previous-versions/windows/desktop/ms719655(v=vs.85)) *prgRows* 매개 변수에 해당합니다.

다른 매개 변수에 대 한 [참조 IRowsetUpdate::취소](/previous-versions/windows/desktop/ms719655(v=vs.85)) *OLE DB 프로그래머의 참조에서*.

## <a name="irowsetupdateimplupdate"></a><a name="update"></a>IRowset업데이트임플::업데이트

마지막 가져오기 또는 업데이트 이후 행에 대한 변경 내용을 전송합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (Update )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBCOUNTITEM* pcRows,
   HROW** prgRows,
   DBROWSTATUS** prgRowStatus);
```

#### <a name="parameters"></a>매개 변수

*h예약*<br/>
【인】 [IRowsetUpdate::Update의](/previous-versions/windows/desktop/ms719709(v=vs.85)) *hChapter* 매개 변수에 해당합니다.

다른 매개 변수에 대 한 [참조 IRowsetUpdate::Update](/previous-versions/windows/desktop/ms719709(v=vs.85)) *OLE DB 프로그래머의 참조*.

### <a name="remarks"></a>설명

변경 내용은 [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)를 호출하여 전송됩니다. 변경 사항이 적용하려면 소비자가 [CRowset::Update를](../../data/oledb/crowset-update.md) 호출해야 합니다. *OLE DB 프로그래머 참조의*행 상태에 설명된 대로 *prgRowstatus를* 적절한 값으로 설정합니다. [Row States](/previous-versions/windows/desktop/ms722752(v=vs.85))

## <a name="irowsetupdateimplisupdateallowed"></a><a name="isupdateallowed"></a>IRowsetUpdateImpl::IsUpdate허용됨

이 메서드를 재정의하여 업데이트 전에 보안, 무결성 등을 확인합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,
   HROW /* [in] */ /* hRowUpdate */,
   DBROWSTATUS* /* [out] */ /* pRowStatus */);
```

#### <a name="parameters"></a>매개 변수

*상태*<br/>
【인】 행에서 보류 중인 작업의 상태입니다.

*hRowUpdate*<br/>
【인】 사용자가 업데이트하려는 행을 처리합니다.

*pRow 상태*<br/>
【아웃】 사용자에게 반환된 상태입니다.

### <a name="remarks"></a>설명

업데이트를 허용해야 한다고 결정한 경우 S_OK 반환합니다. 그렇지 않으면 E_FAIL 반환합니다. 업데이트를 허용하는 경우 `DBROWSTATUS` [IRowsetUpdateImpl::Update를](../../data/oledb/irowsetupdateimpl-update.md) 적절한 [행 상태로](/previous-versions/windows/desktop/ms722752(v=vs.85))설정해야 합니다.

## <a name="irowsetupdateimplm_mapcacheddata"></a><a name="mapcacheddata"></a>IRowset업데이트임플::m_mapCachedData

지연된 작업에 대한 원본 데이터를 포함하는 맵입니다.

### <a name="syntax"></a>구문

```cpp
CAtlMap<
   HROW hRow,
   Storage* pData
>
m_mapCachedData;
```

#### <a name="parameters"></a>매개 변수

*hRow*<br/>
데이터의 행을 처리합니다.

*Pdata*<br/>
캐시할 데이터에 대한 포인터입니다. 데이터는 *저장소* 유형(사용자 레코드 클래스)입니다. [IRowsetUpdateImpl 클래스에서](../../data/oledb/irowsetupdateimpl-class.md) *저장소* 템플릿 인수를 참조하십시오.

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 아키텍처](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[업데이터 제공자 만들기](../../data/oledb/creating-an-updatable-provider.md)
