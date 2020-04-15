---
title: CStreamRowset 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
ms.openlocfilehash: ad4987422fd200faef141150908d4df0722f669a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366268"
---
# <a name="cstreamrowset-class"></a>CStreamRowset 클래스

또는 `CCommand` `CTable` 선언에 사용됩니다.

## <a name="syntax"></a>구문

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>매개 변수

*T 액세스 자*<br/>
접근자 클래스입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CStreamRowset](#cstreamrowset)|생성자입니다. `CStreamRowset` 개체를 인스턴스화하고 초기화합니다.|
|[닫기](#close)|클래스에서 [I순량 스트림](/previous-versions/windows/desktop/ms718035(v=vs.85)) 인터페이스 포인터를 해제합니다.|

## <a name="remarks"></a>설명

예를 `CStreamRowset` `CCommand` 들어 `CTable` 사용자 또는 선언에 사용하십시오.

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

또는

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute``ISequentialStream` 에 저장된 포인터를 반환합니다. `m_spStream` 그런 다음 `Read` 메서드를 사용하여 XML 형식으로 유니코드 문자열( 유니코드 문자열) 데이터를 검색합니다. 다음은 그 예입니다.

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000은 XML 서식을 수행하며 행 집합의 모든 열과 모든 행을 하나의 XML 문자열로 반환합니다.

> [!NOTE]
> 이 기능은 SQL Server 2000에서만 작동합니다.

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a>CStreamRowset::CStreamRowset

`CStreamRowset` 개체를 인스턴스화하고 초기화합니다.

### <a name="syntax"></a>구문

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a>CStreamRowset::닫기

클래스에서 [I순량 스트림](/previous-versions/windows/desktop/ms718035(v=vs.85)) 인터페이스 포인터를 해제합니다.

### <a name="syntax"></a>구문

```cpp
void Close();
```

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)
