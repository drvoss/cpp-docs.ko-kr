---
title: 수동 접근자 사용
ms.date: 10/24/2018
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
ms.openlocfilehash: a6c0e5236702229a61a828344ba5d0d288898aee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209328"
---
# <a name="using-manual-accessors"></a>수동 접근자 사용

알 수 없는 명령을 처리할 때 다음 네 가지 작업을 수행 해야 합니다.

- 매개 변수 확인

- 명령 실행

- 출력 열 확인

- 반환 행 집합이 여러 개 있는지 확인

OLE DB 소비자 템플릿으로 이러한 작업을 수행 하려면 `CManualAccessor` 클래스를 사용 하 고 다음 단계를 수행 합니다.

1. `CManualAccessor`를 템플릿 매개 변수로 사용 하 여 `CCommand` 개체를 엽니다.

    ```cpp
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;
    ```

1. `IDBSchemaRowset` 인터페이스에 대 한 세션을 쿼리하고 프로시저 매개 변수 행 집합을 사용 합니다. `IDBSchemaRowset` 인터페이스를 사용할 수 없는 경우 `ICommandWithParameters` 인터페이스를 쿼리 합니다. 정보에 대 한 `GetParameterInfo`를 호출 합니다. 두 인터페이스를 모두 사용할 수 없는 경우에는 매개 변수가 없는 것으로 간주할 수 있습니다.

1. 각 매개 변수에 대해 `AddParameterEntry`를 호출 하 여 매개 변수를 추가 하 고 설정 합니다.

1. 행 집합을 연 다음 bind 매개 변수를 **false**로 설정 합니다.

1. `GetColumnInfo`를 호출 하 여 출력 열을 검색 합니다. `AddBindEntry`를 사용 하 여 출력 열을 바인딩에 추가 합니다.

1. `GetNextResult`를 호출 하 여 더 많은 행 집합을 사용할 수 있는지 확인 합니다. 2-5 단계를 반복 합니다.

수동 접근자에 대 한 예제는 [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) 샘플의 `CDBListView::CallProcedure`을 참조 하세요.

## <a name="see-also"></a>참고 항목

[접근자 사용](../../data/oledb/using-accessors.md)
