---
title: CCustomRowset(CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyproviderrowset
- ccustomrowset
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
ms.openlocfilehash: 8e90db287bc7ac8994914766045eb210446dfd48
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079788"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset(CustomRS.H)

이 마법사는 행 집합 개체에 대 한 항목을 생성 합니다. 이 경우 `CCustomRowset`라고 합니다. `CCustomRowset` 클래스는 행 집합 개체에 필요한 모든 인터페이스를 구현 하는 `CRowsetImpl`이라는 OLE DB 공급자 클래스에서 상속 됩니다. 다음 코드는 `CRowsetImpl`의 상속 체인을 보여 줍니다.

```cpp
template <class T, class Storage, class CreatorClass,
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,
      CSimpleRow, IRowsetLocateImpl< T >>
```

또한 `CRowsetImpl` `IAccessor` 및 `IColumnsInfo` 인터페이스를 사용 합니다. 테이블의 출력 필드에 대해 이러한 인터페이스를 사용 합니다. 또한 클래스는 소비자가 두 행이 동일한 지 여부를 확인할 수 있도록 하는 `IRowsetIdentity`에 대 한 구현을 제공 합니다. `IRowsetInfo` 인터페이스는 행 집합 개체에 대 한 속성을 구현 합니다. 공급자는 `IConvertType` 인터페이스를 사용 하 여 소비자가 요청한 데이터 형식과 공급자가 사용 하는 데이터 형식의 차이를 해결할 수 있습니다.

`IRowset` 인터페이스는 실제로 데이터 검색을 처리 합니다. 소비자는 먼저 `GetNextRows` 라는 메서드를 호출 하 여 `HROW`이라고 하는 행에 대 한 핸들을 반환 합니다. 그런 다음 소비자는 해당 `HROW`를 사용 하 여 `IRowset::GetData`를 호출 하 여 요청 된 데이터를 검색 합니다.

또한 `CRowsetImpl`는 여러 템플릿 매개 변수를 사용 합니다. 이러한 매개 변수를 사용 하 여 `CRowsetImpl` 클래스가 데이터를 처리 하는 방법을 결정할 수 있습니다. `ArrayType` 인수를 사용 하면 행 데이터를 저장 하는 데 사용 되는 저장소 메커니즘을 확인할 수 있습니다. *Rowclass* 매개 변수는 `HROW`포함 하는 클래스를 지정 합니다.

*RowsetInterface* 매개 변수를 사용 하 여 `IRowsetLocate` 또는 `IRowsetScroll` 인터페이스를 사용할 수도 있습니다. `IRowsetLocate` 및 `IRowsetScroll` 인터페이스는 모두 `IRowset`에서 상속 됩니다. 따라서 OLE DB 공급자 템플릿은 이러한 인터페이스에 대 한 특별 한 처리를 제공 해야 합니다. 이러한 인터페이스 중 하나를 사용 하려는 경우이 매개 변수를 사용 해야 합니다.

## <a name="see-also"></a>참고 항목

[공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)<br/>
