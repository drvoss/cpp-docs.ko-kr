---
title: IRowsetChangeImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
- ATL.IRowsetChangeImpl.DeleteRows
- ATL::IRowsetChangeImpl::DeleteRows
- IRowsetChangeImpl.DeleteRows
- DeleteRows
- IRowsetChangeImpl::DeleteRows
- ATL.IRowsetChangeImpl.InsertRow
- InsertRow
- IRowsetChangeImpl.InsertRow
- ATL::IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::SetData
- ATL.IRowsetChangeImpl.SetData
- IRowsetChangeImpl.SetData
- ATL::IRowsetChangeImpl::SetData
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
- DeleteRows method
- InsertRow method
- SetData method
- FlushData method
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
ms.openlocfilehash: ae4ceea53ec91cc3f9593dd3789fcf61e0702274
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376941"
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl 클래스

OLE DB 사양의 [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) 인터페이스의 OLE DB 템플릿 구현입니다.

## <a name="syntax"></a>구문

```cpp
template <
   class T,
   class Storage,
   class BaseInterface = IRowsetChange,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface
```

### <a name="parameters"></a>매개 변수

*T*<br/>
에서 `IRowsetChangeImpl`파생된 클래스입니다.

*스토리지*<br/>
사용자 레코드입니다.

*베이스 인터페이스*<br/>
인터페이스의 기본 클래스(예: `IRowsetChange`))

*로우 클래스*<br/>
행 핸들의 저장소 단위입니다.

*맵 클래스*<br/>
공급자가 보유한 모든 행 핸들의 저장소 단위입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="interface-methods-used-with-irowsetchange"></a>인터페이스 방법(IRowsetChange와 함께 사용)

|||
|-|-|
|[삭제행](#deleterows)|행 집합에서 행을 삭제합니다.|
|[InsertRow](#insertrow)|행을 행 집합에 삽입합니다.|
|[Setdata](#setdata)|하나 이상의 열에서 데이터 값을 설정합니다.|

### <a name="implementation-method-callback"></a>구현 방법(콜백)

|||
|-|-|
|[플러시 데이터](#flushdata)|공급자가 데이터를 해당 저장소에 커밋하도록 재정의합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 데이터 저장소에 즉시 쓰기 작업을 담당합니다. "즉시"는 최종 사용자(소비자를 사용하는 사람)가 변경하면 해당 변경 내용이 즉시 데이터 저장소로 전송되며 취소할 수 없음을 의미합니다.

`IRowsetChangeImpl`기존 행의 `IRowsetChange` 열 값을 업데이트하고 행을 삭제하고 새 행을 삽입할 수 있는 OLE DB 인터페이스를 구현합니다.

OLE DB 템플릿 구현은 모든 기본`SetData` `InsertRow`메서드(, 및)를 `DeleteRows`지원합니다.

> [!IMPORTANT]
> 공급자를 구현하기 전에 다음 설명서를 읽는 것이 좋습니다.

- [업데이터 제공자 만들기](../../data/oledb/creating-an-updatable-provider.md)

- OLE DB *프로그래머 의 참조* 6 장

- 또한 `RUpdateRowset` [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) 샘플에서 클래스가 어떻게 사용되는지 확인합니다.

## <a name="irowsetchangeimpldeleterows"></a><a name="deleterows"></a>IRowsetChangeImpl::D엘레테로우스

행 집합에서 행을 삭제합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>매개 변수

*OLE DB 프로그래머의 참조에서* [IRowsetChange::Deleterows를](/previous-versions/windows/desktop/ms724362(v=vs.85)) 참조하십시오.

## <a name="irowsetchangeimplinsertrow"></a><a name="insertrow"></a>IRowset체인지임플::인서트로

행 집합에서 새 행을 만들고 초기화합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>매개 변수

[IRowsetChange::OLE](/previous-versions/windows/desktop/ms716921(v=vs.85)) *DB 프로그래머의 참조에서 삽입행을*참조하십시오.

## <a name="irowsetchangeimplsetdata"></a><a name="setdata"></a>IRowset체인지임플::세트데이터

하나 이상의 열에서 데이터 값을 설정합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>매개 변수

*올레 DB 프로그래머의 참조에서* [IRowsetChange::SetData를](/previous-versions/windows/desktop/ms721232(v=vs.85)) 참조하십시오.

## <a name="irowsetchangeimplflushdata"></a><a name="flushdata"></a>IRowset체인지임플::플러시데이터

공급자가 데이터를 해당 저장소에 커밋하도록 재정의합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>매개 변수

*hRowTo플러시*<br/>
【인】 데이터의 행을 처리합니다. 이 행의 형식은 `IRowsetImpl` 클래스의 *RowClass* 템플릿 인수(기본적으로)에서`CSimpleRow` 결정됩니다.

*h액세스토르토플러시*<br/>
【인】 바인딩 정보 및 형식 정보를 포함하는 접근자(IAccessorImpl 참조)를 처리합니다. `PROVIDER_MAP` [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)

### <a name="return-value"></a>Return Value

표준 HRESULT.

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 아키텍처](../../data/oledb/ole-db-provider-template-architecture.md)
