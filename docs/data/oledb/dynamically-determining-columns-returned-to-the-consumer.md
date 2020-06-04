---
title: 소비자에게 반환되는 열을 동적으로 결정
ms.date: 10/26/2018
helpviewer_keywords:
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
ms.openlocfilehash: 6b6061fc7da6f4c4dd53ae70a0e2d5ba7ec40023
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079639"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>소비자에게 반환되는 열을 동적으로 결정

PROVIDER_COLUMN_ENTRY 매크로는 일반적으로 `IColumnsInfo::GetColumnsInfo` 호출을 처리 합니다. 그러나 소비자가 책갈피를 사용 하도록 선택할 수 있기 때문에 공급자는 소비자가 책갈피를 요청 하는지 여부에 따라 반환 되는 열을 변경할 수 있어야 합니다.

`IColumnsInfo::GetColumnsInfo` 호출을 처리 하려면 *사용자 지정*RS. h의 `CCustomWindowsFile` 사용자 레코드에서 함수 `GetColumnInfo`정의 하는 PROVIDER_COLUMN_MAP을 삭제 하 고 고유한 `GetColumnInfo` 함수의 정의로 바꿉니다.

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H
class CCustomWindowsFile
{
public:
   DWORD dwBookmark;
   static const int iSize = 256;
   TCHAR szCommand[iSize];
   TCHAR szText[iSize];
   TCHAR szCommand2[iSize];
   TCHAR szText2[iSize];
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);
   bool operator==(const CCustomWindowsFile& am)
   {
      return (lstrcmpi(szCommand, am.szCommand) == 0);
   }
};
```

다음으로, 다음 코드와 같이 *사용자 지정*RS .cpp에서 `GetColumnInfo` 함수를 구현 합니다.

`GetColumnInfo`는 먼저 OLE DB 속성 `DBPROP_BOOKMARKS` 설정 되었는지 확인 합니다. 속성을 가져오기 위해 `GetColumnInfo`는 행 집합 개체에 대 한 포인터 (`pRowset`)를 사용 합니다. `pThis` 포인터는 속성 맵이 저장 된 클래스인 행 집합을 만든 클래스를 나타냅니다. `pThis` 포인터를 `RCustomRowset` 포인터로 대입문 `GetColumnInfo` 합니다.

`DBPROP_BOOKMARKS` 속성을 확인 하려면 `GetColumnInfo` `IRowsetInfo` 인터페이스를 사용 합니다 .이 인터페이스는 `pRowset` 인터페이스에서 `QueryInterface`를 호출 하 여 가져올 수 있습니다. 대신, ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 메서드를 대신 사용할 수 있습니다.

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp
ATLCOLUMNINFO* CCustomWindowsFile::GetColumnInfo(void* pThis, ULONG* pcCols)
{
   static ATLCOLUMNINFO _rgColumns[5];
   ULONG ulCols = 0;
  
   // Check the property flag for bookmarks; if it is set, set the zero
   // ordinal entry in the column map with the bookmark information.
   CCustomRowset* pRowset = (CCustomRowset*) pThis;
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
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),
         DBTYPE_BYTES, 0, 0, GUID_NULL, CCustomWindowsFile, dwBookmark,
         DBCOLUMNFLAGS_ISBOOKMARK)
         ulCols++;
      }
   }
  
   // Next, set the other columns up.
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szCommand)
   ulCols++;
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szText)
   ulCols++;
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szCommand2)
   ulCols++;
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szText2)
   ulCols++;
  
   if (pcCols != NULL)
      *pcCols = ulCols;
  
   return _rgColumns;
}
```

이 예제에서는 정적 배열을 사용 하 여 열 정보를 저장 합니다. 소비자가 책갈피 열을 원하지 않는 경우 배열의 한 항목은 사용 되지 않습니다. 정보를 처리 하려면 ADD_COLUMN_ENTRY 및 ADD_COLUMN_ENTRY_EX의 두 배열 매크로를 만듭니다. ADD_COLUMN_ENTRY_EX는 책갈피 열을 지정 하는 경우 필요한 추가 매개 변수 *플래그*를 사용 합니다.

```cpp
////////////////////////////////////////////////////////////////////////  
// CustomRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = flags; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \  
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \  
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;  
```

`GetColumnInfo` 함수에서 책갈피 매크로는 다음과 같이 사용 됩니다.

```cpp
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,
   DBCOLUMNFLAGS_ISBOOKMARK)
```

이제 향상 된 공급자를 컴파일하고 실행할 수 있습니다. 공급자를 테스트 하려면 [간단한 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)에 설명 된 대로 테스트 소비자를 수정 합니다. 공급자를 사용 하 여 테스트 소비자를 실행 하 고 테스트 소비자가 공급자에서 적절 한 문자열을 검색 하는지 확인 합니다.

## <a name="see-also"></a>참고 항목

[단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
