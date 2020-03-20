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
ms.openlocfilehash: 4a0e67ff1e800ff0f838b863eaaf839d4456ed82
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545560"
---
# <a name="cstreamrowset-class"></a>CStreamRowset 클래스

`CCommand` 또는 `CTable` 선언에 사용 됩니다.

## <a name="syntax"></a>구문

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>매개 변수

*TAccessor*<br/>
접근자 클래스입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CStreamRowset](#cstreamrowset)|생성자입니다. `CStreamRowset` 개체를 인스턴스화하고 초기화 합니다.|
|[닫기](#close)|클래스에서 [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) 인터페이스 포인터를 해제 합니다.|

## <a name="remarks"></a>주의

`CCommand` 또는 `CTable` 선언에 `CStreamRowset`를 사용 합니다. 예를 들면 다음과 같습니다.

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

또는

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute`는 `m_spStream`에 저장 된 `ISequentialStream` 포인터를 반환 합니다. 그런 다음 `Read` 메서드를 사용 하 여 XML 형식의 (유니코드 문자열) 데이터를 검색 합니다. 예를 들면 다음과 같습니다.

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000은 XML 서식 지정을 수행 하 고 행 집합의 모든 열과 모든 행을 하나의 XML 문자열로 반환 합니다.

> [!NOTE]
>  이 기능은 SQL Server 2000 에서만 작동 합니다.

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a>CStreamRowset:: CStreamRowset

`CStreamRowset` 개체를 인스턴스화하고 초기화 합니다.

### <a name="syntax"></a>구문

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a>CStreamRowset:: Close

클래스에서 [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) 인터페이스 포인터를 해제 합니다.

### <a name="syntax"></a>구문

```cpp
void Close();
```

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)