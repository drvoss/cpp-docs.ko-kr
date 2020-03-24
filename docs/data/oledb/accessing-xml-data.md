---
title: XML 데이터 액세스
ms.date: 10/18/2018
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
ms.openlocfilehash: be4225003211449a98d3fbe5fd686b9b8058a651
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212279"
---
# <a name="accessing-xml-data"></a>XML 데이터 액세스

데이터 원본에서 XML 데이터를 검색 하는 방법에는 두 가지가 있습니다. 하나는 [CStreamRowset](../../data/oledb/cstreamrowset-class.md) 을 사용 하 고 다른 하나는 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)를 사용 합니다.

|기능|CStreamRowset|CXMLAccessor|
|-------------------|-------------------|------------------|
|전송 된 데이터의 양|모든 열과 행에서 한 번에 데이터를 검색 합니다.|모든 열에서 데이터를 검색 하지만 한 번에 한 행씩 검색 합니다. `MoveNext`와 같은 메서드를 사용 하 여 행을 탐색 해야 합니다.|
|문자열 서식 지정|SQL Server XML 문자열의 형식을 지정 하 고 소비자에 게 보냅니다.|원시 형식으로 행 집합 데이터를 검색 한 다음 (공급자가 유니코드 문자열로 전송 하도록 요청) XML 형식으로 데이터를 포함 하는 문자열을 작성 합니다.|
|서식 지정 제어|일부 SQL Server 2000 관련 속성을 설정 하 여 XML 문자열의 형식을 지정 하는 방법을 제어할 수 있습니다.|생성 된 XML 문자열의 형식을 제어할 수 없습니다.|

`CStreamRowset`는 XML 형식으로 데이터를 검색 하는 보다 전체 효율적인 방법을 제공 하지만 SQL Server 2000 에서만 지원 됩니다.

## <a name="retrieving-xml-data-using-cstreamrowset"></a>CStreamRowset를 사용 하 여 XML 데이터 검색

`CCommand` 또는 `CTable` 선언에서 행 집합 형식으로 [CStreamRowset](../../data/oledb/cstreamrowset-class.md) 를 지정 합니다. 접근자를 사용 하거나 접근자를 사용 하지 않고 사용할 수 있습니다. 예를 들면 다음과 같습니다.

```cpp
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;
```

-또는-

```cpp
CCommand<CNoAccessor, CStreamRowset> myCmd;
```

일반적으로 `CCommand::Open`를 호출 하는 경우 (예: `CRowset` `TRowset` 클래스로 지정) `IRowset` 포인터를 가져옵니다. `ICommand::Execute`는 `CRowset` 개체의 `m_spRowset` 멤버에 저장 되는 `IRowset` 포인터를 반환 합니다. `MoveFirst`, `MoveNext`및 `GetData`와 같은 메서드는 해당 포인터를 사용 하 여 데이터를 검색 합니다.

이와 대조적으로 `CCommand::Open`를 호출 하지만 `CStreamRowset`를 `TRowset` 클래스로 지정 하는 경우 `ICommand::Execute`는 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)의 `ISequentialStream` 데이터 멤버에 저장 된 `m_spStream` 포인터를 반환 합니다. 그런 다음 `Read` 메서드를 사용 하 여 XML 형식의 (유니코드 문자열) 데이터를 검색 합니다. 예를 들면 다음과 같습니다.

```cpp
myCmd.m_spStream->Read()
```

SQL Server 2000은 XML 서식 지정을 수행 하 고 행 집합의 모든 열과 모든 행을 하나의 XML 문자열로 반환 합니다.

`Read` 메서드를 사용 하는 예제는 [간단한 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)에서 **소비자에 게 XML 지원 추가** 를 참조 하세요.

> [!NOTE]
> `CStreamRowset`를 사용 하는 XML 지원은 SQL Server 2000 에서만 작동 하며, SQL Server 2000 용 OLE DB 공급자 (MDAC와 함께 설치 됨)가 있어야 합니다.

## <a name="retrieving-xml-data-using-cxmlaccessor"></a>CXMLAccessor를 사용 하 여 XML 데이터 검색

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) 를 사용 하면 데이터 저장소의 스키마에 대해 알지 못하는 경우 데이터 원본의 데이터를 문자열 데이터로 액세스할 수 있습니다. `CXMLAccessor`는 `CDynamicStringAccessorW`와 같이 작동 합니다. 단, 이전에는 데이터 저장소에서 액세스 하는 모든 데이터를 XML 형식 (태그가 지정 된) 데이터로 변환 합니다. XML 태그 이름은 데이터 저장소의 열 이름과 최대한 유사 하 게 일치 합니다.

다른 접근자 클래스와 같이 `CXMLAccessor` 사용 하 여 `CCommand` 또는 `CTable`에 템플릿 매개 변수로 전달 합니다.

```cpp
CTable<CXMLAccessor, CRowset> rs;
```

[Getxmlrowdata](../../data/oledb/cxmlaccessor-getxmlrowdata.md) 를 사용 하 여 테이블에서 한 번에 한 행씩 데이터를 검색 하 고 `MoveNext`와 같은 메서드를 사용 하 여 행을 탐색할 수 있습니다. 예를 들면 다음과 같습니다.

```cpp
// Open data source, session, and rowset
hr = rs.MoveFirst();

while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
{
    CStringW strRowData;
    myCmd.GetXMLRowData(strRowData);

    printf_s( "%S\n", strRowData );

    hr = rs.MoveNext();
}
```

[Getxmlcolumndata](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) 를 사용 하 여 열 (데이터 형식) 정보를 XML 형식의 문자열 데이터로 검색할 수 있습니다.

## <a name="see-also"></a>참고 항목

[접근자 사용](../../data/oledb/using-accessors.md)
