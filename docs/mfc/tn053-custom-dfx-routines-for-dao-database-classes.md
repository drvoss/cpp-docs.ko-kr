---
title: 'TN053: DAO 데이터베이스 클래스에 대한 사용자 지정 DFX 루틴'
ms.date: 09/17/2019
helpviewer_keywords:
- MFC, DAO and
- database classes [MFC], DAO
- DAO [MFC], MFC
- DFX (DAO record field exchange) [MFC], custom routines
- TN053
- DAO [MFC], classes
- DFX (DAO record field exchange) [MFC]
- custom DFX routines [MFC]
ms.assetid: fdcf3c51-4fa8-4517-9222-58aaa4f25cac
ms.openlocfilehash: f7ad854f4dbb4e90c09e886c69260e4e2eea3be2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365257"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: DAO 데이터베이스 클래스에 대한 사용자 지정 DFX 루틴

> [!NOTE]
> DAO는 Access 데이터베이스와 함께 사용되며 Office 2013을 통해 지원됩니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다. Visual C++ 환경 및 마법사는 DAO를 지원하지 않습니다(DAO 클래스가 포함되어 있지만 여전히 사용할 수 있음). 새 프로젝트에 는 [OLE DB 템플릿](../data/oledb/ole-db-templates.md) 또는 [ODBC 및 MFC를](../data/odbc/odbc-and-mfc.md) 사용하는 것이 좋습니다. 기존 응용 프로그램을 유지 관리하는 데만 DAO를 사용해야 합니다.

이 기술 노트는 DAO 레코드 필드 교환(DFX) 메커니즘에 대해 설명합니다. DFX 루틴에서 무슨 일이 일어나고 있는지 `DFX_Text` 이해하기 위해 함수를 예제로 자세히 설명합니다. 이 기술 노트에 대한 추가 정보 소스로 다른 개별 DFX 함수에 대한 코드를 검사할 수 있습니다. ODBC 데이터베이스 클래스에서 사용되는 사용자 지정 RFX 루틴이 필요한 만큼 사용자 지정 DFX 루틴이 자주 필요하지 않을 수 있습니다.

이 기술 노트에는 다음이 포함되어 있습니다.

- DFX 개요

- DAO 레코드 필드 교환 및 동적 [바인딩을](#_mfcnotes_tn053_examples) 사용하는 예제

- [DFX 작동 방식](#_mfcnotes_tn053_how_dfx_works)

- [사용자 지정 DFX 루틴이 수행하는 일](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)

- [DFX_Text 세부 정보](#_mfcnotes_tn053_details_of_dfx_text)

**DFX 개요**

DAO 레코드 필드 교환 메커니즘(DFX)은 클래스를 사용할 때 데이터를 검색하고 `CDaoRecordset` 업데이트하는 절차를 단순화하는 데 사용됩니다. 이 프로세스는 클래스의 데이터 `CDaoRecordset` 멤버를 사용하여 단순화됩니다. 에서 `CDaoRecordset`파생하여 테이블 또는 쿼리의 각 필드를 나타내는 파생 클래스에 데이터 멤버를 추가할 수 있습니다. 이 "정적 바인딩" 메커니즘은 간단하지만 모든 응용 프로그램에 대해 선택한 데이터 가져오기/업데이트 방법이 아닐 수 있습니다. DFX는 현재 레코드가 변경될 때마다 모든 바인딩 필드를 검색합니다. 통화가 변경될 때 모든 필드를 가져올 필요가 없는 성능에 민감한 응용 프로그램을 개발하는 `CDaoRecordset::GetFieldValue` `CDaoRecordset::SetFieldValue` 경우 "동적 바인딩"을 통해 선택한 데이터 액세스 방법일 수 있습니다.

> [!NOTE]
> DFX 및 동적 바인딩은 상호 배타적이지 않으므로 정적 바인딩과 동적 바인딩을 하이브리드로 사용할 수 있습니다.

## <a name="example-1--use-of-dao-record-field-exchange-only"></a><a name="_mfcnotes_tn053_examples"></a>예제 1 — DAO 레코드 필드 교환만 사용

(파생 `CDaoRecordset` 클래스가 `CMySet` 이미 열려 있다고 가정)

```
// Add a new record to the customers table
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```

**예제 2 — 동적 바인딩만 사용**

(클래스를 `CDaoRecordset` 사용 `rs`하 여 가정 하 고 이미 열려 있습니다.)

```
// Add a new record to the customers table
COleVariant  varFieldValue1 (_T("MSFT"),
    VT_BSTRT);

//Note: VT_BSTRT flags string type as ANSI,
    instead of UNICODE default
COleVariant  varFieldValue2  (_T("Microsoft"),
    VT_BSTRT);

rs.AddNew();

rs.SetFieldValue(_T("Customer_ID"),
    varFieldValue1);

rs.SetFieldValue(_T("Customer_Name"),
    varFieldValue2);

rs.Update();
```

**예제 3 — DAO 레코드 필드 교환 및 동적 바인딩 사용**

(-파생 클래스를 `emp` `CDaoRecordset`사용하여 직원 데이터를 탐색한다고 가정)

```
// Get the employee's data so that it can be displayed
emp.MoveNext();

// If user wants to see employee's photograph,
// fetch it
COleVariant varPhoto;
if (bSeePicture)
    emp.GetFieldValue(_T("photo"),
    varPhoto);

// Display the data
PopUpEmployeeData(emp.m_strFirstName,
    emp.m_strLastName,
    varPhoto);
```

## <a name="how-dfx-works"></a><a name="_mfcnotes_tn053_how_dfx_works"></a>DFX 작동 방식

DFX 메커니즘은 MFC ODBC 클래스에서 사용하는 RFX(레코드 필드 교환) 메커니즘과 유사한 방식으로 작동합니다. DFX와 RFX의 원칙은 동일하지만 내부의 차이는 많습니다. DFX 함수의 디자인은 거의 모든 코드가 개별 DFX 루틴에서 공유되도록 하는 것이었습니다. 가장 높은 수준에서 DFX는 몇 가지 작업을 수행합니다.

- DFX는 필요한 경우 SQL **SELECT** 절 및 SQL **매개 변수 절을 생성합니다.**

- DFX는 DAO `GetRows` 함수에서 사용하는 바인딩 구조를 구성합니다(자세한 내용은 나중에 참조).

- DFX는 더티 필드를 검색하는 데 사용되는 데이터 버퍼를 관리합니다(이중 버퍼링이 사용되는 경우).

- DFX는 **NULL** 및 **DIRTY** 상태 배열을 관리하고 업데이트에 필요한 경우 값을 설정합니다.

DFX 메커니즘의 핵심은 `CDaoRecordset` 파생 클래스의 `DoFieldExchange` 함수입니다. 이 함수는 적절한 작업 유형의 개별 DFX 함수에 대한 호출을 디스패치합니다. 내부 `DoFieldExchange` MFC 함수를 호출하기 전에 작업 유형을 설정합니다. 다음 목록은 다양한 작업 유형과 간략한 설명을 보여 주며 있습니다.

|작업(Operation)|Description|
|---------------|-----------------|
|`AddToParameterList`|매개 변수 절 을 빌드합니다.|
|`AddToSelectList`|SELECT 절 빌드|
|`BindField`|바인딩 구조 설정|
|`BindParam`|매개변수 값 설정|
|`Fixup`|NULL 상태 설정|
|`AllocCache`|더러운 검사를 위해 캐시를 할당합니다.|
|`StoreField`|현재 레코드를 캐시에 저장합니다.|
|`LoadField`|멤버 값으로 캐시 복원|
|`FreeCache`|캐시 를 해제합니다.|
|`SetFieldNull`|필드 상태 & 값을 NULL로 설정|
|`MarkForAddNew`|PSEUDO NULL이 아닌 경우 필드를 더럽게 표시합니다.|
|`MarkForEdit`|캐시와 일치하지 않는 경우 필드가 더러워지다|
|`SetDirtyField`|더티로 표시된 필드 값 설정|

다음 섹션에서는 각 작업에 대해 `DFX_Text`자세히 설명합니다.

DAO 레코드 필드 교환 프로세스에 대해 이해해야 할 가장 `GetRows` 중요한 `CDaoRecordset` 기능은 개체의 함수를 사용한다는 것입니다. DAO `GetRows` 함수는 여러 가지 방법으로 작동할 수 있습니다. 이 기술 노트는 이 `GetRows` 기술 노트의 범위를 벗어난 것으로 간단히 설명합니다.
DAO는 `GetRows` 여러 가지 방법으로 작동할 수 있습니다.

- 한 번에 여러 레코드와 여러 데이터 필드를 가져올 수 있습니다. 이를 통해 대규모 데이터 구조와 각 필드 및 구조의 각 데이터 레코드에 대한 적절한 오프셋을 처리하는 복잡성으로 더 빠른 데이터 액세스를 수행할 수 있습니다. MFC는 이 다중 레코드 페칭 메커니즘을 활용하지 않습니다.

- 또 `GetRows` 다른 방법은 프로그래머가 하나의 데이터 레코드에 대해 각 필드의 검색된 데이터에 대한 바인딩 주소를 지정할 수 있도록 하는 것입니다.

- 또한 DAO는 호출자가 메모리를 할당할 수 있도록 가변 길이 열에 대해 호출자에게 "다시 호출"합니다. 이 두 번째 기능은 데이터 복사본 수를 최소화하고 `CDaoRecordset` 클래스(파생 클래스)의 구성원에 데이터를 직접 저장하도록 허용하는 이점이 있습니다. 이 두 번째 메커니즘은 MFC가 파생 `CDaoRecordset` 클래스의 데이터 멤버에 바인딩하는 데 사용하는 방법입니다.

## <a name="what-your-custom-dfx-routine-does"></a><a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a>사용자 지정 DFX 루틴이 수행하는 일

이 토론에서 DFX 함수에서 구현된 가장 중요한 작업은 에 필요한 데이터 구조를 성공적으로 호출할 `GetRows`수 있는 기능이어야 합니다. DFX 함수도 지원해야 하는 다른 여러 작업이 있지만 `GetRows` 호출을 올바르게 준비하는 것만큼 중요하거나 복잡한 작업은 없습니다.

DFX의 사용은 온라인 설명서에 설명되어 있습니다. 기본적으로 두 가지 요구 사항이 있습니다. 먼저 각 바인딩필드 및 `CDaoRecordset` 매개 변수에 대해 파생 클래스에 멤버를 추가해야 합니다. 다음을 `CDaoRecordset::DoFieldExchange` 재정의해야 합니다. 멤버의 데이터 형식은 중요합니다. 데이터베이스의 필드의 데이터와 일치하거나 적어도 해당 유형으로 변환할 수 있어야 합니다. 예를 들어 긴 정수와 같은 데이터베이스의 숫자 필드는 항상 텍스트로 변환하고 `CString` 멤버에 바인딩할 수 있지만 데이터베이스의 텍스트 필드는 긴 정수및 긴 정수 멤버에 바인딩된 숫자 표현으로 반드시 변환될 필요는 없습니다. DAO와 Microsoft Jet 데이터베이스 엔진은 MFC가 아닌 변환을 담당합니다.

## <a name="details-of-dfx_text"></a><a name="_mfcnotes_tn053_details_of_dfx_text"></a>DFX_Text 세부 정보

앞에서 설명한 것처럼 DFX의 작동 방식을 설명하는 가장 좋은 방법은 예제를 통해 작업하는 것입니다. 이 목적을 위해 DFX의 `DFX_Text` 적어도 기본적인 이해를 제공하는 데 도움이 꽤 잘 작동해야합니다의 내부를 통해 가는.

- `AddToParameterList`

   이 작업은 Jet에서 요구하는 SQL`Parameters <param name>, <param type> ... ;`매개 **변수** 절("")을 빌드합니다. 각 매개 변수의 이름이 지정되고 형식이 지정됩니다(RFX 호출에 지정된 대로). 함수 `CDaoFieldExchange::AppendParamType` 함수를 참조하여 개별 형식의 이름을 확인합니다. 의 `DFX_Text`경우 사용 되는 형식은 **텍스트**입니다.

- `AddToSelectList`

   SQL **SELECT** 절을 빌드합니다. 이것은 DFX 호출에 의해 지정된 열 이름이 단순히 추가 ("")이기`SELECT <column name>, ...`때문에 매우 간단합니다.

- `BindField`

   작업의 가장 복잡한. 앞에서 설명한 것처럼 이 에 의해 `GetRows` 사용되는 DAO 바인딩 구조가 설정되는 위치입니다. 코드에서 볼 수 있듯이 `DFX_Text` 구조내의 정보 유형은 사용되는 DAO 타입(DAO_CHAR 또는 `DFX_Text` **DAO_WCHAR)을** 포함한다.**DAO_CHAR** 또한 사용되는 바인딩 유형도 설정됩니다. 이전 섹션에서는 `GetRows` 간략하게 설명되었지만 MFC에서 사용하는 바인딩 유형은 항상 직접 주소 바인딩(DAOBINDING_DIRECT)임을 설명하기에 충분했습니다.**DAOBINDING_DIRECT** 또한 MFC가 메모리 할당을 `DFX_Text`제어하고 올바른 길이의 주소를 지정할 수 있도록 가변 길이 열 바인딩(예:) 콜백 바인딩이 사용됩니다. 즉, MFC는 항상 DAO에게 데이터를 넣을 위치를 알려 멤버 변수에 직접 바인딩할 수 있다는 것입니다. 나머지 바인딩 구조는 메모리 할당 콜백 함수의 주소및 열 바인딩 유형(열 이름으로 바인딩)과 같은 것으로 채워져 있습니다.

- `BindParam`

   이 작업은 매개 변수 `SetParamValue` 멤버에 지정된 매개 변수 값으로 호출하는 간단한 작업입니다.

- `Fixup`

   각 필드에 대한 **NULL** 상태를 채웁니다.

- `SetFieldNull`

   이 작업은 각 필드 상태를 **NULL로만** 표시하고 멤버 변수의 값을 **PSEUDO_NULL.**

- `SetDirtyField`

   더티로 표시된 각 필드에 대한 호출입니다. `SetFieldValue`

나머지 모든 작업은 데이터 캐시를 사용하는 것만 처리합니다. 데이터 캐시는 특정 작업을 더 간단하게 만드는 데 사용되는 현재 레코드의 데이터의 추가 버퍼입니다. 예를 들어 "더티" 필드를 자동으로 검색할 수 있습니다. 온라인 설명서에 설명된 대로 완전히 또는 현장 수준에서 해제할 수 있습니다. 버퍼의 구현은 맵을 활용합니다. 이 맵은 동적으로 할당된 데이터의 복사본을 "바인딩된" 필드(또는 `CDaoRecordset` 파생 데이터 멤버)의 주소와 일치시키기 위해 사용됩니다.

- `AllocCache`

   캐시된 필드 값을 동적으로 할당하고 맵에 추가합니다.

- `FreeCache`

   캐시된 필드 값을 삭제하고 맵에서 제거합니다.

- `StoreField`

   현재 필드 값을 데이터 캐시에 복사합니다.

- `LoadField`

   캐시된 값을 필드 멤버에 복사합니다.

- `MarkForAddNew`

   현재 필드 값이**NULL이** 아닌지 확인하고 필요한 경우 더럽게 표시합니다.

- `MarkForEdit`

   현재 필드 값을 데이터 캐시와 비교하고 필요한 경우 더러워서 표시합니다.

> [!TIP]
> 표준 데이터 형식에 대한 기존 DFX 루틴에서 사용자 지정 DFX 루틴을 모델링합니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
