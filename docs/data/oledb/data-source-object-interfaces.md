---
title: 데이터 소스 개체 인터페이스
ms.date: 10/24/2018
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
ms.openlocfilehash: a615694a9db75cdaf3b187cf6d29248bd26ef978
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544605"
---
# <a name="data-source-object-interfaces"></a>데이터 소스 개체 인터페이스

다음 표는 OLE DB가 데이터 원본 개체에 대해 정의한 필수 인터페이스와 선택적 인터페이스를 보여줍니다.

|인터페이스|필수 여부|OLE DB 템플릿에서 구현 됩니까?|
|---------------|---------------|--------------------------------------|
|`IDBCreateSession`|필수|예|
|`IDBInitialize`|필수|예|
|`IDBProperties`|필수|예|
|[IPersist](/windows/win32/api/objidl/nn-objidl-ipersist)|필수|예|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|선택 사항|아니요|
|`IDBDataSourceAdmin`|선택 사항|아니요|
|`IDBInfo`|선택 사항|아니요|
|[IPersistFile](/windows/win32/api/objidl/nn-objidl-ipersistfile)|선택 사항|아니요|
|`ISupportErrorInfo`|선택 사항|아니요|

데이터 원본 개체는 상속을 통해 `IDBProperties`, `IDBInitialize`및 `IDBCreateSession` 인터페이스를 구현 합니다. 이러한 구현 클래스 중 하나에서 상속하거나 상속하지 않도록 하여 추가 기능을 지원하도록 선택할 수 있습니다. `IDBDataSourceAdmin` 인터페이스를 지원 하려는 경우 `IDBDataSourceAdminImpl` 클래스에서 상속 해야 합니다.

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
