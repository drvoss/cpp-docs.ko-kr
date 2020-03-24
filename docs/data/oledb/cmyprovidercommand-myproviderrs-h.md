---
title: CCustomCommand(CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidercommand
- ccustomcommand
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
- CCustomCommand class in CustomRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
ms.openlocfilehash: afa8571173117a23962eb84f6fa5b4cf2c3c46e7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211759"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand(CustomRS.H)

`CCustomCommand` 클래스는 공급자 명령 개체에 대 한 구현입니다. `IAccessor`, `ICommandText`및 `ICommandProperties` 인터페이스에 대 한 구현을 제공 합니다. `IAccessor` 인터페이스는 행 집합의 인터페이스와 동일 합니다. 명령 개체는 접근자를 사용 하 여 매개 변수에 대 한 바인딩을 지정 합니다. 행 집합 개체는이를 사용 하 여 출력 열에 대 한 바인딩을 지정 합니다. `ICommandText` 인터페이스는 명령을 텍스트로 지정 하는 유용한 방법입니다. 이 예제에서는 나중에 사용자 지정 코드를 추가할 때 `ICommandText` 인터페이스를 사용 합니다. 또한 `ICommand::Execute` 메서드를 재정의 합니다. `ICommandProperties` 인터페이스는 명령 및 행 집합 개체에 대 한 모든 속성을 처리 합니다.

```cpp
// CCustomCommand
class ATL_NO_VTABLE CCustomCommand :
class ATL_NO_VTABLE CCustomCommand :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IAccessorImpl<CCustomCommand>,
   public ICommandTextImpl<CCustomCommand>,
   public ICommandPropertiesImpl<CCustomCommand>,
   public IObjectWithSiteImpl<CCustomCommand>,
   public IConvertTypeImpl<CCustomCommand>,
   public IColumnsInfoImpl<CCustomCommand>
```

`IAccessor` 인터페이스는 명령 및 행 집합에 사용 되는 모든 바인딩을 관리 합니다. 소비자는 `DBBINDING` 구조체의 배열을 사용 하 여 `IAccessor::CreateAccessor`를 호출 합니다. 각 `DBBINDING` 구조에는 열 바인딩을 처리 하는 방법에 대 한 정보 (예: 형식 및 길이)가 포함 되어 있습니다. 공급자는 구조를 받은 다음 데이터를 전송 하는 방법과 변환이 필요한 지 여부를 결정 합니다. 명령 개체에서 `IAccessor` 인터페이스를 사용 하 여 명령의 매개 변수를 처리 합니다.

Command 개체는 `IColumnsInfo`의 구현도 제공 합니다. OLE DB에는 `IColumnsInfo` 인터페이스가 필요 합니다. 인터페이스를 사용 하면 소비자가 명령의 매개 변수에 대 한 정보를 검색할 수 있습니다. 행 집합 개체는 `IColumnsInfo` 인터페이스를 사용 하 여 출력 열에 대 한 정보를 공급자에 게 반환 합니다.

또한이 공급자에는 `IObjectWithSite`이라는 인터페이스가 포함 되어 있습니다. `IObjectWithSite` 인터페이스는 ATL 2.0에서 구현 되었으며 구현자는 자신에 대 한 정보를 해당 자식에 전달할 수 있도록 합니다. 명령 개체는 `IObjectWithSite` 정보를 사용 하 여 생성 된 모든 행 집합 개체를 생성 한 사람에 게 알립니다.

## <a name="see-also"></a>참고 항목

[공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)
