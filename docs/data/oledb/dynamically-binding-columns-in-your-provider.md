---
title: 공급자에서 열을 동적으로 바인딩
ms.date: 11/04/2016
helpviewer_keywords:
- columns [C++], dynamic column binding
- dynamic column binding
- providers [C++], dynamic column binding
ms.assetid: 45e811e3-f5a7-4627-98cc-bf817c4e556e
ms.openlocfilehash: 8a0b4c399bf25137be86d95102da9723c3116d51
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210979"
---
# <a name="dynamically-binding-columns-in-your-provider"></a>공급자에서 열을 동적으로 바인딩

동적 열 바인딩이 정말로 필요한 지 확인 합니다. 다음 이유 때문에 필요할 수 있습니다.

- 행 집합 열은 컴파일 시간에 정의 되지 않습니다.

- 열을 추가 하는 책갈피와 같은 요소를 지원 합니다.

## <a name="to-implement-dynamic-column-binding"></a>동적 열 바인딩을 구현 하려면

1. 코드에서 `PROVIDER_COLUMN_MAP`s를 제거 합니다.

1. 사용자 레코드 (사용자 구조)에서 다음 선언을 추가 합니다.

    ```cpp
    static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);
    ```

1. `GetColumnInfo` 함수를 구현 합니다. 이 함수는 정보를 저장 하는 방법을 레이아웃 합니다. 이 함수에 대 한 속성 또는 기타 정보를 가져와야 할 수 있습니다. 사용자 고유의 정보를 추가 하기 위해 [COLUMN_ENTRY](../../data/oledb/column-entry.md) 매크로와 비슷한 매크로를 만들 수 있습니다.

   다음 예에서는 `GetColumnInfo` 함수를 보여 줍니다.

    ```cpp
    // Check the property flag for bookmarks, if it is set, set the zero
    // ordinal entry in the column map with the bookmark information.
    CAgentRowset* pRowset = (CAgentRowset*) pThis;
    CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;

    CDBPropIDSet set(DBPROPSET_ROWSET);
    set.AddPropertyID(DBPROP_BOOKMARKS);
    DBPROPSET* pPropSet = NULL;
    ULONG ulPropSet = 0;
    HRESULT hr;

    if (spRowsetProps)
       hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);

    if (pPropSet)
    {
       CComVariant var = pPropSet->rgProperties[0].vValue;
       CoTaskMemFree(pPropSet->rgProperties);
       CoTaskMemFree(pPropSet);

       if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))
       {
          ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD), DBTYPE_BYTES,
             0, 0, GUID_NULL, CAgentMan, dwBookmark, DBCOLUMNFLAGS_ISBOOKMARK)
          ulCols++;
       }
    }

    // Next, set up the other columns.
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,
       GUID_NULL, CAgentMan, szCommand)
    ulCols++;
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,
       GUID_NULL, CAgentMan, szText)
    ulCols++;

    ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,
       GUID_NULL, CAgentMan, szCommand2)
    ulCols++;
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,
       GUID_NULL, CAgentMan, szText2)
    ulCols++;

    if (pcCols != NULL)
       *pcCols = ulCols;

    return _rgColumns;
    }
    ```

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)
