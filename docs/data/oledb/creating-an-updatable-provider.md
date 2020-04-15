---
title: 업데이트 가능 공급자 만들기
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 720ceba397d17642402de4d44cbb4481852fa153
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365554"
---
# <a name="creating-an-updatable-provider"></a>업데이트 가능 공급자 만들기

Visual C++는 데이터 저장소를 업데이트(쓰기)할 수 있는 업데이트할 수 있는 업데이트 할 수 있는 공급자 또는 공급자를 지원합니다. 이 항목에서는 OLE DB 템플릿을 사용하여 업데이터 공급자를 만드는 방법에 대해 설명합니다.

이 항목에서는 실행 가능한 공급자로 시작하는 것으로 가정합니다. 업데이터 공급자를 만드는 데는 두 단계가 있습니다. 먼저 공급자가 데이터 저장소를 변경하는 방법을 결정해야 합니다. 특히 업데이트 명령이 발행될 때까지 변경 작업을 즉시 수행할지 또는 연기할지 여부가 표시됩니다. ["공급자를 업데이터로 만들기"](#vchowmakingprovidersupdatable)섹션에서는 공급자 코드에서 수행해야 하는 변경 및 설정을 설명합니다.

다음으로 공급자에 소비자가 요청할 수 있는 모든 기능을 지원하는 모든 기능이 포함되어 있는지 확인해야 합니다. 소비자가 데이터 저장소를 업데이트하려는 경우 공급자는 데이터 저장소에 데이터를 유지하는 코드를 포함해야 합니다. 예를 들어 C 런타임 라이브러리 또는 MFC를 사용하여 데이터 원본에서 이러한 작업을 수행할 수 있습니다. "데이터[원본에 쓰기"](#vchowwritingtothedatasource)섹션에서는 데이터 원본에 쓰고, NULL 및 기본값을 처리하고, 열 플래그를 설정하는 방법을 설명합니다.

> [!NOTE]
> [UpdatePV는](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) 업데이터 공급자의 예입니다. UpdatePV는 MyProv와 동일하지만 업데이트 가능한 지원을 합니다.

## <a name="making-providers-updatable"></a><a name="vchowmakingprovidersupdatable"></a>공급자를 업데이터로 만들기

공급자를 업데이터로 만드는 핵심은 공급자가 데이터 저장소에서 수행할 작업과 공급자가 이러한 작업을 수행하는 방법을 이해하는 것입니다. 특히 가장 큰 문제는 업데이트 명령이 발급될 때까지 데이터 저장소에 대한 업데이트를 즉시 수행할지 아니면 지연(일괄 처리)할지 여부입니다.

먼저 행 집합 클래스에서 `IRowsetChangeImpl` `IRowsetUpdateImpl` 상속할지 또는 상속할지 결정해야 합니다. 구현하도록 선택한 이 중 어느 메서드의 기능에 따라 세 `SetData` `InsertRows`가지 `DeleteRows`메서드의 기능이 영향을 받습니다.

- [IRowsetChangeImpl에서](../../data/oledb/irowsetchangeimpl-class.md)상속하는 경우 이러한 세 가지 메서드를 호출하면 즉시 데이터 저장소가 변경됩니다.

- [IRowsetUpdateImpl에서](../../data/oledb/irowsetupdateimpl-class.md)상속하는 경우 메서드는 호출할 `Update`때까지 데이터 `GetOriginalData`저장소에 `Undo`대한 변경 내용을 연기합니다. 업데이트에 여러 변경 사항이 포함된 경우 일괄 처리 모드에서 수행됩니다(일괄 처리 변경으로 상당한 메모리 오버헤드가 추가될 수 있음).

`IRowsetChangeImpl`에서 `IRowsetUpdateImpl` 파생됩니다. 따라서 `IRowsetUpdateImpl` 변경 기능과 일괄 처리 기능을 제공합니다.

### <a name="to-support-updatability-in-your-provider"></a>공급자의 업데이터 성을 지원하려면

1. 행 집합 클래스에서 상속 `IRowsetChangeImpl` `IRowsetUpdateImpl`또는 . 이러한 클래스는 데이터 저장소를 변경하기 위한 적절한 인터페이스를 제공합니다.

   **IRowsetChange 추가**

   다음 `IRowsetChangeImpl` 양식을 사용하여 상속 체인에 추가합니다.

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   또한 `COM_INTERFACE_ENTRY(IRowsetChange)` 행 `BEGIN_COM_MAP` 집합 클래스의 섹션에 추가합니다.

   **IRowsetUpdate 추가**

   다음 `IRowsetUpdate` 양식을 사용하여 상속 체인에 추가합니다.

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > 상속 체인에서 `IRowsetChangeImpl` 선을 제거해야 합니다. 앞에서 언급한 지시문에 대한 이 한 `IRowsetChangeImpl`가지 예외는 에 대한 코드를 포함해야 합니다.

1. COM 맵에 다음을`BEGIN_COM_MAP ... END_COM_MAP`추가합니다( )

   |  구현하는 경우   |           COM 맵에 추가             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | 구현하는 경우 | 속성 세트 맵에 추가 |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. 명령에서 속성 집합 맵에 다음을`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`추가합니다(

   |  구현하는 경우   |                                             속성 세트 맵에 추가                                              |
   |---------------------|------------------------------------------------------------------------------------------------------------------|
   | `IRowsetChangeImpl` |                            `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`                             |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. 속성 설정 맵에 아래와 같이 다음 설정도 모두 포함해야 합니다.

    ```cpp
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)

    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)
    ```

   속성 식별 및 값에 대 한 Atldb.h에서 보면 이러한 매크로 호출에 사용 되는 값을 찾을 수 있습니다 (Atldb.h 온라인 설명서와 다른 경우 Atldb.h 문서를 대체).

   > [!NOTE]
   > OLE DB `VARIANT_FALSE` `VARIANT_TRUE` 템플릿에는 많은 설정이 필요합니다. OLE DB 사양은 읽기/쓰기가 가능합니다만 OLE DB 템플릿은 하나의 값만 지원할 수 있습니다.

   **IRowsetChangeImpl을 구현하는 경우**

   을 구현하는 `IRowsetChangeImpl`경우 공급자에서 다음 속성을 설정해야 합니다. 이러한 속성은 주로 를 통해 `ICommandProperties::SetProperties`인터페이스를 요청하는 데 사용됩니다.

   - `DBPROP_IRowsetChange`: 이 설정을 `DBPROP_IRowsetChange`자동으로 설정합니다.

   - `DBPROP_UPDATABILITY`: 지원되는 메서드를 지정하는 `IRowsetChange` `SetData`비트 `DeleteRows`마스크 `InsertRow`: .

   - `DBPROP_CHANGEINSERTEDROWS`: 소비자가 `IRowsetChange::DeleteRows` 호출하거나 `SetData` 새로 삽입된 행을 호출할 수 있습니다.

   - `DBPROP_IMMOBILEROWS`: 행 집합은 삽입되거나 업데이트된 행의 순서를 다시 정렬하지 않습니다.

   **IRowsetUpdateImpl을 구현하는 경우**

   구현하는 `IRowsetUpdateImpl`경우 `IRowsetChangeImpl` 이전에 나열된 모든 속성을 설정하는 것 외에도 공급자에서 다음 속성을 설정해야 합니다.

   - `DBPROP_IRowsetUpdate`.

   - `DBPROP_OWNINSERT`: READ_ONLY VARIANT_TRUE.

   - `DBPROP_OWNUPDATEDELETE`: READ_ONLY VARIANT_TRUE.

   - `DBPROP_OTHERINSERT`: READ_ONLY VARIANT_TRUE.

   - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY VARIANT_TRUE.

   - `DBPROP_REMOVEDELETED`: READ_ONLY VARIANT_TRUE.

   - `DBPROP_MAXPENDINGROWS`.

   > [!NOTE]
   > 알림을 지원하는 경우 다른 속성도 있을 수 있습니다. 이 목록의 `IRowsetNotifyCP` 섹션을 참조하십시오.

## <a name="writing-to-the-data-source"></a><a name="vchowwritingtothedatasource"></a>데이터 원본에 쓰기

데이터 원본에서 읽으려면 함수를 호출합니다. `Execute` 데이터 원본에 쓰려면 함수를 호출합니다. `FlushData` 일반적으로 플러시는 테이블이나 인덱스를 디스크에 저장한다는 의미입니다.

```cpp
FlushData(HROW, HACCESSOR);
```

행 핸들(HROW) 및 접근자 핸들(HACCESSOR) 인수를 사용하면 쓸 영역을 지정할 수 있습니다. 일반적으로 한 번에 단일 데이터 필드를 작성합니다.

메서드는 `FlushData` 원래 저장 된 형식으로 데이터를 씁니다. 이 함수를 재정의하지 않으면 공급자가 올바르게 작동하지만 변경 내용은 데이터 저장소로 플러시되지 않습니다.

### <a name="when-to-flush"></a>플러시 시기

공급자 템플릿은 데이터를 데이터 저장소에 기록해야 할 때마다 FlushData를 호출합니다. 일반적으로 다음 함수에 대한 호출의 결과로 발생합니다(항상 그렇지는 않음).

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows`(행에 삽입할 새 데이터가 있는 경우)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>작동 방법

소비자는 플러시(예: Update)가 필요한 호출을 수행하며 이 호출은 항상 다음을 수행하는 공급자에게 전달됩니다.

- 상태 `SetDBStatus` 값이 바인딩될 때마다 호출됩니다.

- 열 플래그를 확인합니다.

- `IsUpdateAllowed`.

이 세 단계는 보안을 제공하는 데 도움이 됩니다. 그런 다음 `FlushData`공급자가 를 호출합니다.

### <a name="how-to-implement-flushdata"></a>플러시 데이터를 구현하는 방법

을 `FlushData`구현하려면 다음과 같은 몇 가지 문제를 고려해야 합니다.

데이터 저장소에서 변경 내용을 처리할 수 있는지 확인합니다.

NULL 값 처리.

### <a name="handling-default-values"></a>기본값 처리.

사용자 고유의 `FlushData` 메서드를 구현하려면 다음을 수행해야 합니다.

- 행 집합 클래스로 이동합니다.

- 행 집합 클래스에서 다음 의 선언을 넣습니다.

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- 의 `FlushData`구현을 제공합니다.

실제로 업데이트되는 `FlushData` 행과 열만 저장소를 잘 구현합니다. HROW 및 HACCESSOR 매개 변수를 사용하여 최적화를 위해 저장되는 현재 행과 열을 확인할 수 있습니다.

일반적으로 가장 큰 과제는 고유한 네이티브 데이터 저장소로 작업하는 것입니다. 가능하면 다음을 시도해 보십시오.

- 데이터 저장소에 쓰기 방법을 가능한 한 간단하게 유지합니다.

- NULL 값을 처리합니다(선택 사항이지만 권장).

- 기본값(선택 사항이지만 권장)을 처리합니다.

가장 좋은 방법은 NULL 및 기본값에 대해 데이터 저장소에 실제 지정된 값을 두는 것입니다. 이 데이터를 추정할 수 있는 경우에 가장 적합합니다. 그렇지 않은 경우 NULL 및 기본값을 허용하지 않는 것이 좋습니다.

다음 예제에서는 `FlushData` `RUpdateRowset` `UpdatePV` 샘플의 클래스에서 구현되는 방법을 보여 주며(샘플 코드의 Rowset.h 참조).

```cpp
///////////////////////////////////////////////////////////////////////////
// class RUpdateRowset (in rowset.h)
...
HRESULT FlushData(HROW, HACCESSOR)
{
    ATLTRACE2(atlTraceDBProvider, 0, "RUpdateRowset::FlushData\n");

    USES_CONVERSION;
    enum {
        sizeOfString = 256,
        sizeOfFileName = MAX_PATH
    };
    FILE*    pFile = NULL;
    TCHAR    szString[sizeOfString];
    TCHAR    szFile[sizeOfFileName];
    errcode  err = 0;

    ObjectLock lock(this);

    // From a filename, passed in as a command text,
    // scan the file placing data in the data array.
    if (m_strCommandText == (BSTR)NULL)
    {
        ATLTRACE( "RRowsetUpdate::FlushData -- "
                  "No filename specified\n");
        return E_FAIL;
    }

    // Open the file
    _tcscpy_s(szFile, sizeOfFileName, OLE2T(m_strCommandText));
    if ((szFile[0] == _T('\0')) ||
        ((err = _tfopen_s(&pFile, &szFile[0], _T("w"))) != 0))
    {
        ATLTRACE("RUpdateRowset::FlushData -- Could not open file\n");
        return DB_E_NOTABLE;
    }

    // Iterate through the row data and store it.
    for (long l=0; l<m_rgRowData.GetSize(); l++)
    {
        CAgentMan am = m_rgRowData[l];

        _putw((int)am.dwFixed, pFile);

        if (_tcscmp(&am.szCommand[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szCommand2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);
    }

    if (fflush(pFile) == EOF || fclose(pFile) == EOF)
    {
        ATLTRACE("RRowsetUpdate::FlushData -- "
                 "Couldn't flush or close file\n");
    }

    return S_OK;
}
```

### <a name="handling-changes"></a>변경 처리

공급자가 변경 내용을 처리하려면 먼저 데이터 저장소(예: 텍스트 파일 또는 비디오 파일)에 변경할 수 있는 시설이 있는지 확인해야 합니다. 그렇지 않으면 공급자 프로젝트와 별도로 해당 코드를 만들어야 합니다.

### <a name="handling-null-data"></a>NULL 데이터 처리

최종 사용자가 NULL 데이터를 보낼 수 있습니다. 데이터 원본의 필드에 NULL 값을 작성하면 잠재적인 문제가 발생할 수 있습니다. 도시 및 우편 번호의 값을 허용하는 주문 접수 응용 프로그램을 상상해 보십시오. 이 경우 배달이 불가능하기 때문에 두 값 중 하나 또는 둘 다를 허용할 수 있지만 둘 다 허용할 수는 없습니다. 따라서 응용 프로그램에 적합한 필드에서 NULL 값의 특정 조합을 제한해야 합니다.

공급자 개발자는 해당 데이터를 저장하는 방법, 데이터 저장소에서 해당 데이터를 읽는 방법 및 해당 데이터를 사용자에게 지정하는 방법을 고려해야 합니다. 특히 데이터 원본에서 행 집합 데이터의 데이터 상태를 변경하는 방법(예: DataStatus = NULL)을 고려해야 합니다. 소비자가 NULL 값을 포함하는 필드에 액세스할 때 반환할 값을 결정합니다.

UpdatePV 샘플의 코드를 살펴보십시오. 공급자가 NULL 데이터를 처리하는 방법을 보여 줍니다. UpdatePV에서 공급자는 데이터 저장소에 문자열 "NULL"을 작성하여 NULL 데이터를 저장합니다. 데이터 저장소에서 NULL 데이터를 읽을 때 해당 문자열을 보고 버퍼를 비워 NULL 문자열을 만듭니다. 또한 해당 데이터 값이 `IRowsetImpl::GetDBStatus` 비어 있는 경우 DBSTATUS_S_ISNULL 반환하는 재정의가 있습니다.

### <a name="marking-nullable-columns"></a>Nullable 열 표시

스키마 행 집합(참조)도 `IDBSchemaRowsetImpl`구현하는 경우 구현은 DBSCHEMA_COLUMNS 행 집합(일반적으로 CxxxSchemaColSchemaRowset에 의해 공급자에 표시됨)에 열이 null임을 지정해야 합니다.

또한 null able 모든 열에 `GetColumnInfo`의 버전에서 DBCOLUMNFLAGS_ISNULLABLE 값이 포함되도록 지정해야 합니다.

OLE DB 템플릿 구현에서 열을 null로 표시하지 못하면 공급자는 해당 열에 값이 포함되어야 하며 소비자가 null 값을 보낼 수 없다고 가정합니다.

다음 예제에서는 UpdatePV에서 CUpdateCommand(UpProvRS.cpp 참조)에서 `CommonGetColInfo` 함수를 구현하는 방법을 보여 주십니다. 열에 nullable 열에 대한 이 DBCOLUMNFLAGS_ISNULLABLE 어떻게 있는지 설명합니다.

```cpp
/////////////////////////////////////////////////////////////////////////////
// CUpdateCommand (in UpProvRS.cpp)

ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols, bool bBookmark)
{
    static ATLCOLUMNINFO _rgColumns[6];
    ULONG ulCols = 0;

    if (bBookmark)
    {
        ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,
                            sizeof(DWORD), DBTYPE_BYTES,
                            0, 0, GUID_NULL, CAgentMan, dwBookmark,
                            DBCOLUMNFLAGS_ISBOOKMARK)
        ulCols++;
    }

    // Next set the other columns up.
    // Add a fixed length entry for OLE DB conformance testing purposes
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Fixed"), 1, 4, DBTYPE_UI4,
                        10, 255, GUID_NULL, CAgentMan, dwFixed,
                        DBCOLUMNFLAGS_WRITE |
                        DBCOLUMNFLAGS_ISFIXEDLENGTH)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command"), 2, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text"), 3, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command2"), 4, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text2"), 5, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    if (pcCols != NULL)
    {
        *pcCols = ulCols;
    }

    return _rgColumns;
}
```

### <a name="default-values"></a>기본값

NULL 데이터와 마찬가지로 기본값 변경을 처리할 책임이 있습니다.

`Execute` 기본값은 `FlushData` S_OK 반환하는 것입니다. 따라서 이 함수를 재정의하지 않으면 변경 내용이 성공한 것으로 나타납니다(S_OK 반환됨) 데이터 저장소로 전송되지 는 않습니다.

`UpdatePV` 샘플(Rowset.h)에서 메서드는 `SetDBStatus` 다음과 같이 기본값을 처리합니다.

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* pdbStatus, CSimpleRow* pRow,
                            ATLCOLUMNINFO* pColInfo)
{
    ATLASSERT(pRow != NULL && pColInfo != NULL && pdbStatus != NULL);

    void* pData = NULL;
    char* pDefaultData = NULL;
    DWORD* pFixedData = NULL;

    switch (*pdbStatus)
    {
        case DBSTATUS_S_DEFAULT:
            pData = (void*)&m_rgRowData[pRow->m_iRowset];
            if (pColInfo->wType == DBTYPE_STR)
            {
                pDefaultData = (char*)pData + pColInfo->cbOffset;
                strcpy_s(pDefaultData, "Default");
            }
            else
            {
                pFixedData = (DWORD*)((BYTE*)pData +
                                          pColInfo->cbOffset);
                *pFixedData = 0;
                return S_OK;
            }
            break;
        case DBSTATUS_S_ISNULL:
        default:
            break;
    }
    return S_OK;
}
```

### <a name="column-flags"></a>열 플래그

열에서 기본값을 지원하는 경우 공급자 클래스 \<\>SchemaRowset 클래스의 메타데이터를 사용하여 설정해야 합니다. `m_bColumnHasDefault = VARIANT_TRUE`을 설정합니다.

또한 DBCOLUMNFLAGS 열거형 형식을 사용하여 지정된 열 플래그를 설정할 책임이 있습니다. 열 플래그는 열 특성을 설명합니다.

예를 `CUpdateSessionColSchemaRowset` `UpdatePV` 들어(Session.h)의 클래스에서 첫 번째 열은 다음과 같은 방식으로 설정됩니다.

```cpp
// Set up column 1
trData[0].m_ulOrdinalPosition = 1;
trData[0].m_bIsNullable = VARIANT_FALSE;
trData[0].m_bColumnHasDefault = VARIANT_TRUE;
trData[0].m_nDataType = DBTYPE_UI4;
trData[0].m_nNumericPrecision = 10;
trData[0].m_ulColumnFlags = DBCOLUMNFLAGS_WRITE |
                            DBCOLUMNFLAGS_ISFIXEDLENGTH;
lstrcpyW(trData[0].m_szColumnDefault, OLESTR("0"));
m_rgRowData.Add(trData[0]);
```

이 코드는 무엇보다도 열이 기본값 0을 지원하고, 쓸 수 있고, 열의 모든 데이터가 동일한 길이를 갖도록 지정합니다. 열의 데이터를 가변 길이로 설정하려면 이 플래그를 설정하지 않습니다.

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 만들기](creating-an-ole-db-provider.md)
