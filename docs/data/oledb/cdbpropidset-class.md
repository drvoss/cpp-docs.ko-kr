---
title: CDBPropIDSet 클래스
ms.date: 11/04/2016
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
- CDBPropIDSet.AddPropertyID
- CDBPropIDSet::AddPropertyID
- AddPropertyID
- ATL.CDBPropIDSet.AddPropertyID
- ATL::CDBPropIDSet::AddPropertyID
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet.operator=
- ATL.CDBPropIDSet.operator=
- ATL::CDBPropIDSet::operator=
- CDBPropIDSet::operator=
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
helpviewer_keywords:
- CDBPropIDSet class
- AddPropertyID method
- CDBPropIDSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
ms.openlocfilehash: a52d7443ab335e8546a4bcce03cf68c3b1d60e3d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212031"
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet 클래스

`DBPROPIDSET` 구조체에서 상속 하 고 키 필드와 [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) access 메서드를 초기화 하는 생성자를 추가 합니다.

## <a name="syntax"></a>구문

```cpp
class CDBPropIDSet : public tagDBPROPIDSET
```

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[AddPropertyID](#addpropertyid)|속성 ID 집합에 속성을 추가 합니다.|
|[CDBPropIDSet](#cdbpropidset)|생성자입니다.|
|[SetGUID](#setguid)|속성 ID 집합의 GUID를 설정 합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator =](#op_equal)|다른 속성 ID로 설정 된 하나의 속성을 할당 합니다.|

## <a name="remarks"></a>주의

OLE DB 소비자는 `DBPROPIDSET` 구조를 사용 하 여 소비자가 속성 정보를 가져올 속성 Id 배열을 전달 합니다. 단일 [Dbpropidset](/previous-versions/windows/desktop/ms717981(v=vs.85)) 구조에서 식별 된 속성은 하나의 속성 집합에 속합니다.

## <a name="cdbpropidsetaddpropertyid"></a><a name="addpropertyid"></a>CDBPropIDSet:: AddPropertyID

속성 id 집합에 속성 ID를 추가 합니다.

### <a name="syntax"></a>구문

```cpp
bool AddPropertyID(DBPROPID propid) throw();
```

#### <a name="parameters"></a>매개 변수

*propid*<br/>
진행 속성 ID 집합에 추가할 속성 ID입니다.

## <a name="cdbpropidsetcdbpropidset"></a><a name="cdbpropidset"></a>CDBPropIDSet:: CDBPropIDSet

생성자입니다. [Dbpropidset](/previous-versions/windows/desktop/ms717981(v=vs.85)) 구조의 `rgProperties`, `cProperties`및 (선택 사항) `guidPropertySet` 필드를 초기화 합니다.

### <a name="syntax"></a>구문

```cpp
CDBPropIDSet(const GUID& guid);

CDBPropIDSet(const CDBPropIDSet& propidset);

CDBPropIDSet();
```

#### <a name="parameters"></a>매개 변수

*guid*<br/>
진행 `guidPropertySet` 필드를 초기화 하는 데 사용 되는 GUID입니다.

*propidset*<br/>
[in] 복사 생성을 위한 다른 `CDBPropIDSet` 개체입니다.

## <a name="cdbpropidsetsetguid"></a><a name="setguid"></a>CDBPropIDSet:: SetGUID

`DBPROPIDSET` 구조의 GUID 필드를 설정 합니다.

### <a name="syntax"></a>구문

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>매개 변수

*guid*<br/>
진행 [Dbpropidset](/previous-versions/windows/desktop/ms717981(v=vs.85)) 구조체의 `guidPropertySet` 필드를 설정 하는 데 사용 되는 GUID입니다.

### <a name="remarks"></a>주의

이 필드는 [생성자](../../data/oledb/cdbpropidset-cdbpropidset.md) 로도 설정할 수 있습니다. 이 클래스의 기본 생성자를 사용 하는 경우이 함수를 호출 합니다.

## <a name="cdbpropidsetoperator-"></a><a name="op_equal"></a>CDBPropIDSet:: operator =

다른 ID 속성 집합에 설정 된 하나의 속성 ID 내용을 할당 합니다.

### <a name="syntax"></a>구문

```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();
```

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)
