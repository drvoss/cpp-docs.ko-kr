---
title: 'TN045: 긴 바르차-바르바이너리를 위한 MFC-데이터베이스 지원'
ms.date: 11/04/2016
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
ms.openlocfilehash: 55a68ba970d0a26163f426d51818c701c13ed051
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750288"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045: Long Varchar/Varbinary에 대한 MFC/데이터베이스 지원

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 참고 는 MFC 데이터베이스 클래스를 사용하여 ODBC **SQL_LONGVARCHAR** 및 **SQL_LONGVARBINARY** 데이터 형식을 검색하고 보내는 방법에 대해 설명합니다.

## <a name="overview-of-long-varcharvarbinary-support"></a>롱 바르차/바르바이너리 지원 개요

ODBC **SQL_LONG_VARCHAR** 및 **SQL_LONGBINARY** 데이터 유형(긴 데이터 열이라고 함)은 방대한 양의 데이터를 보유할 수 있습니다. 이 데이터를 처리할 수 있는 방법에는 세 가지가 있습니다.

- 에 바인딩합니다. / `CString` `CByteArray`

- `CLongBinary`에 바인딩합니다.

- 데이터베이스 클래스와 는 별개로 긴 데이터 값을 수동으로 검색하고 전송하지 마십시오.

세 가지 방법 각각에는 장점과 단점이 있습니다.

긴 데이터 열은 쿼리에 대한 매개 변수에 대해 지원되지 않습니다. 출력열에 대해서만 지원됩니다.

## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>긴 데이터 열을 CString/CByteArray에 바인딩

장점

이 방법은 이해하기 쉽고 익숙한 클래스로 작업합니다. 프레임워크는 `CFormView` `DDX_Text`에 `CString` 대한 지원을 제공합니다. `CString` 및 `CByteArray` 클래스와 함께 많은 일반 문자열 또는 컬렉션 기능이 있으며 데이터 값을 보유하도록 로컬로 할당된 메모리 양을 제어할 수 있습니다. 프레임워크는 호출 중 또는 `Edit` `AddNew` 함수 호출 중에 필드 데이터의 이전 복사본을 유지 관리하며 프레임워크는 자동으로 데이터 변경 내용을 검색할 수 있습니다.

> [!NOTE]
> 문자 `CString` 데이터 작업을 위해 설계되었으며 `CByteArray` 이진 데이터 작업을 위해 문자 데이터(SQL_LONGVARCHAR)와**SQL_LONGVARCHAR** `CString`이진 데이터(SQL_LONGVARBINARY)를 에 `CByteArray`넣는 것이 좋습니다.**SQL_LONGVARBINARY**

RFX함수는 데이터 `CString` `CByteArray` 열에 대해 검색된 값을 보유하도록 할당된 메모리의 기본 크기를 재정의할 수 있는 추가 인수를 가지고 있습니다. 다음 함수 선언에서 nMaxLength 인수를 참고하십시오.

```cpp
void AFXAPI RFX_Text(CFieldExchange* pFX,
    const char *szName,
    CString& value,
    int nMaxLength = 255,
    int nColumnType =
    SQL_VARCHAR);

void AFXAPI RFX_Binary(CFieldExchange* pFX,
    const char *szName,
    CByteArray& value,
    int nMaxLength = 255);
```

`CString` 긴 데이터 열을 또는 `CByteArray`로 검색하는 경우 반환되는 최대 데이터 양은 기본적으로 255바이트입니다. 이 것 이상의 것은 무시됩니다. 이 경우 프레임워크는 예외 **AFX_SQL_ERROR_DATA_TRUNCATED**throw합니다. 다행히도 **maxInT까지**nMaxLength를 더 큰 값으로 명시적으로 늘릴 수 있습니다.

> [!NOTE]
> nMaxLength값은 MFC에서 `SQLBindColumn` 함수의 로컬 버퍼를 설정하는 데 사용됩니다. 이 버퍼는 데이터 저장을 위한 로컬 버퍼이며 ODBC 드라이버에서 반환되는 데이터 양에는 실제로 영향을 주지 않습니다. `RFX_Text`백 `RFX_Binary` 엔드 데이터베이스에서 `SQLFetch` 데이터를 검색하는 데 사용한 호출만 합니다. 각 ODBC 드라이버는 단일 가져오기에서 반환할 수 있는 데이터 양에 대해 서로 다른 제한을 가지게 됩니다. 이 제한은 nMaxLength에 설정된 값보다 훨씬 작을 수 있으며, 이 경우 예외 **AFX_SQL_ERROR_DATA_TRUNCATED** throw됩니다. 이러한 상황에서는 모든 `RFX_LongBinary` 데이터를 `RFX_Text` 검색할 수 있는 대신 사용하거나 `RFX_Binary` 사용할 수 있도록 전환합니다.

ClassWizard는 **SQL_LONGVARCHAR** `CString`에 바인딩하거나 **SQL_LONGVARBINARY** `CByteArray` 바인딩합니다. 긴 데이터 열을 검색하는 255바이트 이상을 할당하려는 경우 nMaxLength에 대한 명시적 값을 제공할 수 있습니다.

긴 데이터 열이 `CString` 또는 `CByteArray`에 바인딩된 경우 " 필드 업데이트는 varCHAR 또는 SQL_**VARBINARY에**바인딩된 경우와 SQL_ 작동합니다.**VARCHAR** 동안 `Edit`. `Update`

## <a name="binding-a-long-data-column-to-a-clongbinary"></a>긴 데이터 열을 CLong Binary에 바인딩

긴 데이터 열에 **MAXINT** 바이트의 데이터가 더 포함될 수 있는 경우 `CLongBinary`을 로 검색하는 것이 좋습니다.

장점

이렇게 하면 사용 가능한 메모리까지 전체 긴 데이터 열을 검색합니다.

단점

데이터는 메모리에 보관됩니다. 또한 이 방법은 매우 많은 양의 데이터에 대해 엄청나게 비용이 많이 듭니다. 필드가 `SetFieldDirty` 작업에 포함되도록 바인딩된 데이터 멤버를 `Update` 호출해야 합니다.

에서 긴 데이터 열을 `CLongBinary`검색하는 경우 데이터베이스 클래스는 긴 데이터 열의 총 크기를 `HGLOBAL` 확인한 다음 전체 데이터 값을 보유할 수 있을 만큼 큰 메모리 세그먼트를 할당합니다. 그런 다음 데이터베이스 클래스는 전체 데이터 `HGLOBAL`값을 할당된 로 검색합니다.

데이터 원본이 긴 데이터 열의 예상 크기를 반환할 수 없는 경우 프레임워크는 **예외를 AFX_SQL_ERROR_SQL_NO_TOTAL**throw합니다. `HGLOBAL` 실패를 할당하려는 시도가 실패하면 표준 메모리 예외가 throw됩니다.

ClassWizard는 **SQL_LONGVARCHAR** 또는 **SQL_LONGVARBINARY** `CLongBinary` 바인딩합니다. 멤버 `CLongBinary` 추가 변수 대화 상자에서 변수 유형으로 선택합니다. 그런 다음 ClassWizard는 `RFX_LongBinary` `DoFieldExchange` 호출에 호출을 추가하고 바인딩필드의 총 수를 증가시게 됩니다.

긴 데이터 열 값을 업데이트하려면 먼저 `HGLOBAL` 할당된 데이터가 `CLongBinary`m_hData 의 *멤버에서* **::GlobalSize를** 호출하여 새 데이터를 보유할 수 있을 만큼 충분히 큰지 확인합니다. 너무 작으면 `HGLOBAL` 릴리스하고 적절한 크기를 할당합니다. 그런 다음 *m_dwDataLength* 새 크기를 반영하도록 설정합니다.

그렇지 않으면 *m_dwDataLength* 대체할 데이터의 크기보다 큰 경우 을 해제하고 다시 할당하거나 `HGLOBAL`할당된 상태로 둘 수 있습니다. *m_dwDataLength*실제로 사용되는 바이트 수를 나타내야 합니다.

## <a name="how-updating-a-clongbinary-works"></a>CLong Binary 작동 방식 업데이트

`CLongBinary` 작동 방식을 이해하는 것은 아니지만 아래에 설명된 이 세 번째 방법을 선택하면 긴 데이터 값을 데이터 원본에 보내는 방법에 대한 예제로 유용할 수 있습니다.

> [!NOTE]
> `CLongBinary` 필드를 업데이트에 포함하려면 필드를 명시적으로 호출해야 `SetFieldDirty` 합니다. Null 설정 을 포함하여 필드를 변경하는 경우 을 호출해야 `SetFieldDirty`합니다. 또한 두 `SetFieldNull`번째 매개 변수가 **FALSE인**을 호출하여 필드를 값을 갖는 것으로 표시해야 합니다.

필드를 업데이트할 `CLongBinary` 때 데이터베이스 클래스는 ODBC의 **DATA_AT_EXEC** 메커니즘을 사용합니다(rgbValue 인수에 대한 `SQLSetPos`ODBC 설명서 참조). 프레임워크에서 삽입 또는 업데이트 문을 준비하는 대신 `HGLOBAL` 포함 된 데이터를 가리키는 대신 의 *주소가* `CLongBinary` 열의 *값으로* 설정되고 길이 표시기는 **SQL_DATA_AT_EXEC**. 나중에 업데이트 문이 데이터 원본으로 `SQLExecDirect` 전송되면 **SQL_NEED_DATA**반환합니다. 이렇게 하면 프레임워크에 이 열의 매개 변수 값이 실제로 의 `CLongBinary`주소임을 알 수 있습니다. 프레임워크는 `SQLGetData` 작은 버퍼로 한 번 호출하여 드라이버가 데이터의 실제 길이를 반환할 것으로 예상합니다. 드라이버가 이진 큰 개체(BLOB)의 실제 길이를 반환하는 경우 MFC는 BLOB를 가져오는 데 필요한 만큼의 공간을 재할당합니다. 데이터 원본이 BLOB의 크기를 확인할 수 없다는 SQL_NO_TOTAL **반환하면**MFC는 더 작은 블록을 만듭니다. 기본 초기 크기는 64K이며 후속 블록은 두 배 크기입니다. 예를 들어 두 번째는 128K이고 세 번째는 256K입니다. 초기 크기를 구성할 수 있습니다.

## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>바인딩되지 않음: SQLGetData를 사용하여 ODBC에서 직접 데이터 검색/전송

이 방법을 사용하면 데이터베이스 클래스를 완전히 우회하고 긴 데이터 열을 직접 처리합니다.

장점

필요한 경우 데이터를 디스크에 캐시하거나 검색할 데이터의 양을 동적으로 결정할 수 있습니다.

단점

프레임워크또는 `Edit` `AddNew` 지원이 없으며 기본 기능을 수행하기 위해 직접 코드를 작성해야 합니다(열`Delete` 수준 작업이 아니므로 작동).

이 경우 긴 데이터 열은 레코드 집합의 선택 목록에 있어야 하지만 프레임워크에 바인딩해서는 안 됩니다. 이 작업을 수행하는 한 가지 방법은 lpszSQL 인수를 통해 `GetDefaultSQL` 또는 `CRecordset`lpszSQL 인수를 `Open` 함수에 제공하고 추가 열을 RFX_ 함수 호출로 바인딩하지 않는 것입니다. ODBC에는 언바운드 필드가 바운드 필드의 오른쪽에 표시되도록 하므로 언바운드 열 또는 열을 선택 목록의 끝에 추가해야 합니다.

> [!NOTE]
> 긴 데이터 열은 프레임워크에 의해 바인딩되지 않으므로 변경 내용은 `CRecordset::Update` 호출로 처리되지 않습니다. 필요한 SQL **INSERT** 및 **UPDATE** 문을 직접 만들고 보내야 합니다.

## <a name="see-also"></a>참조

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
