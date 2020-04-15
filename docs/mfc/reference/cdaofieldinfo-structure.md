---
title: CDaoFieldInfo 구조체
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: 9466386fefc6e5ab8fcf89bf497c1d5219e3e807
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368404"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo 구조체

구조에는 `CDaoFieldInfo` DAO(데이터 액세스 개체)에 대해 정의된 필드 개체에 대한 정보가 포함되어 있습니다.

DAO는 Office 2013을 통해 지원됩니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다.

## <a name="syntax"></a>구문

```
struct CDaoFieldInfo
{
    CString m_strName;           // Primary
    short m_nType;               // Primary
    long m_lSize;                // Primary
    long m_lAttributes;          // Primary
    short m_nOrdinalPosition;    // Secondary
    BOOL m_bRequired;            // Secondary
    BOOL m_bAllowZeroLength;     // Secondary
    long m_lCollatingOrder;      // Secondary
    CString m_strForeignName;    // Secondary
    CString m_strSourceField;    // Secondary
    CString m_strSourceTable;    // Secondary
    CString m_strValidationRule; // All
    CString m_strValidationText; // All
    CString m_strDefaultValue;   // All
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
필드 개체의 이름을 고유하게 지정합니다. 자세한 내용은 DAO 도움말의 "이름 속성" 항목을 참조하십시오.

*m_nType*<br/>
필드의 데이터 형식을 나타내는 값입니다. 자세한 내용은 DAO 도움말의 "속성 유형" 항목을 참조하십시오. 이 속성의 값은 다음 중 하나일 수 있습니다.

- `dbBoolean`예/아니요, TRUE/FALSE와 동일

- `dbByte`바이트

- `dbInteger`짧은

- `dbLong`긴

- `dbCurrency`통화; MFC 클래스 [COleCurrency](../../mfc/reference/colecurrency-class.md) 참조

- `dbSingle`단일

- `dbDouble`더블

- `dbDate`날짜/시간; MFC 클래스 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 참조

- `dbText`텍스트; MFC 클래스 [문자열](../../atl-mfc-shared/reference/cstringt-class.md) 참조

- `dbLongBinary` Long Binary (OLE 개체); `CByteArray`보다 풍부하고 사용하기 쉬운 `CLongBinary`클래스 대신 MFC 클래스 [CByteArray](../../mfc/reference/cbytearray-class.md)를 사용하는 것이 좋습니다.

- `dbMemo`메모; MFC 클래스 참조`CString`

- `dbGUID`원격 프로시저 호출과 함께 사용되는 전역 고유 식별자/범용 고유 식별자입니다. 자세한 내용은 DAO 도움말의 "속성 유형" 항목을 참조하십시오.

> [!NOTE]
> 이진 데이터에 문자열 데이터 형식을 사용하지 마십시오. 이로 인해 데이터가 유니코드/ANSI 변환 계층을 통과하여 오버헤드가 증가하고 예기치 않은 번역이 발생할 수 있습니다.

*m_lSize*<br/>
텍스트또는 텍스트 또는 숫자 값을 포함하는 필드 개체의 고정 크기를 포함하는 DAO 필드 개체의 최대 크기(바이트)를 나타내는 값입니다. 자세한 내용은 DAO 도움말의 "크기 속성" 항목을 참조하십시오. 크기는 다음 값 중 하나일 수 있습니다.

|Type|크기(바이트)|Description|
|----------|--------------------|-----------------|
|`dbBoolean`|1바이트|예/아니요(참/거짓과 동일)|
|`dbByte`|1|Byte|
|`dbInteger`|2|정수|
|`dbLong`|4|long|
|`dbCurrency`|8|화폐[(COleCurrency)](../../mfc/reference/colecurrency-class.md)|
|`dbSingle`|4|Single|
|`dbDouble`|8|Double|
|`dbDate`|8|[날짜/시간(콜레데이트 타임)](../../atl-mfc-shared/reference/coledatetime-class.md)|
|`dbText`|1 - 255|텍스트[(문자열)](../../atl-mfc-shared/reference/cstringt-class.md)|
|`dbLongBinary`|0|긴 바이너리(OLE 개체; [CByteArray;](../../mfc/reference/cbytearray-class.md) `CLongBinary`대신 사용)|
|`dbMemo`|0|메모[(문자열)](../../atl-mfc-shared/reference/cstringt-class.md)|
|`dbGUID`|16|원격 프로시저 호출과 함께 사용되는 전역 고유 식별자/범용 고유 식별자입니다.|

*m_lAttributes*<br/>
tabledef, 레코드 집합, 쿼리 def 또는 인덱스 개체에 포함된 필드 개체의 특성을 지정합니다. 반환되는 값은 C++ 비트-OR(&#124;) 연산자로 만든** **이러한 상수의 합계일 수 있습니다.

- `dbFixedField`필드 크기가 고정되어 있습니다(숫자 필드의 기본값).

- `dbVariableField`필드 크기는 가변적입니다(텍스트 필드만 해당).

- `dbAutoIncrField`새 레코드의 필드 값은 변경할 수 없는 고유한 긴 정수로 자동으로 증분됩니다. Microsoft Jet 데이터베이스 테이블에만 지원됩니다.

- `dbUpdatableField`필드 값을 변경할 수 있습니다.

- `dbDescending`필드는 내림차순(Z - A 또는 100 - 0) 순서로 정렬됩니다(인덱스 개체의 필드 컬렉션에 필드 개체에만 적용됨; MFC에서 인덱스 개체는 tabledef 개체에 포함됨). 이 상수를 생략하면 필드는 오름차순(A - Z 또는 0 - 100) 순서(기본값)로 정렬됩니다.

이 속성의 설정을 확인할 때 C++ 비트와이즈-AND 연산자 ()를**&** 사용하여 특정 특성을 테스트할 수 있습니다. 여러 특성을 설정할 때 적절한 상수를 비트별** OR(&#124;) **연산자와 결합하여 결합할 수 있습니다. 자세한 내용은 DAO 도움말의 "속성 속성" 항목을 참조하십시오.

*m_nOrdinalPosition*<br/>
DAO 필드 개체로 표시되는 필드를 다른 필드를 기준으로 표시할 숫자 순서를 지정하는 값입니다. [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)을 사용하여 이 속성을 설정할 수 있습니다. 자세한 내용은 DAO 도움말의 "서수 위치 속성" 항목을 참조하십시오.

*m_bRequired*<br/>
DAO 필드 개체에 Null이 아닌 값이 필요한지 여부를 나타냅니다. 이 속성이 TRUE이면 필드는 Null 값을 허용하지 않습니다. 필수가 FALSE로 설정된 경우 필드에Null 값과 AllowZeroLength 및 ValidationRule 속성 설정에서 지정한 조건을 충족하는 값을 포함할 수 있습니다. 자세한 내용은 DAO 도움말의 "필수 속성" 항목을 참조하십시오. [CDaoTableDef::CreateField를](../../mfc/reference/cdaotabledef-class.md#createfield)사용하여 테이블def에 대해 이 속성을 설정할 수 있습니다.

*m_bAllowZeroLength*<br/>
빈 문자열("")이 텍스트 또는 메모 데이터 형식이 있는 DAO 필드 개체의 유효한 값인지 여부를 나타냅니다. 이 속성이 TRUE이면 빈 문자열이 유효한 값입니다. 이 속성을 FALSE로 설정하여 빈 문자열을 사용하여 필드 값을 설정할 수 없도록 할 수 있습니다. 자세한 내용은 DAO 도움말의 "허용 영지 속성" 항목을 참조하십시오. [CDaoTableDef::CreateField를](../../mfc/reference/cdaotabledef-class.md#createfield)사용하여 테이블def에 대해 이 속성을 설정할 수 있습니다.

*m_lCollatingOrder*<br/>
문자열 비교 또는 정렬을 위해 텍스트에서 정렬 순서의 순서를 지정합니다. 자세한 내용은 DAO 도움말의 "데이터 액세스에 대한 Windows 레지스트리 설정 사용자 지정" 항목을 참조하십시오. 반환가능한 값 목록은 `m_lCollatingOrder` [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) 구조의 멤버를 참조하십시오. [CDaoTableDef::CreateField를](../../mfc/reference/cdaotabledef-class.md#createfield)사용하여 테이블def에 대해 이 속성을 설정할 수 있습니다.

*m_strForeignName*<br/>
관계에서 기본 테이블의 필드에 해당하는 외래 테이블의 DAO 필드 개체의 이름을 지정하는 값입니다. 자세한 내용은 DAO 도움말의 "ForeignName 속성" 항목을 참조하십시오.

*m_strSourceField*<br/>
tabledef, 레코드 집합 또는 querydef 개체에 포함된 DAO 필드 개체에 대한 데이터의 원래 원본인 필드 이름을 나타냅니다. 이 속성은 필드 개체와 연결된 원래 필드 이름을 나타냅니다. 예를 들어 이 속성을 사용하여 기본 테이블의 필드 이름과 관련이 없는 이름이 있는 쿼리 필드의 데이터의 원래 원본을 결정할 수 있습니다. 자세한 내용은 DAO 도움말의 "소스필드, 소스테이블 속성" 항목을 참조하십시오. [CDaoTableDef::CreateField를](../../mfc/reference/cdaotabledef-class.md#createfield)사용하여 테이블def에 대해 이 속성을 설정할 수 있습니다.

*m_strSourceTable*<br/>
테이블 def, 레코드 집합 또는 querydef 개체에 포함된 DAO 필드 개체에 대한 데이터의 원래 원본인 테이블 이름을 나타냅니다. 이 속성은 필드 개체와 연결된 원래 테이블 이름을 나타냅니다. 예를 들어 이 속성을 사용하여 기본 테이블의 필드 이름과 관련이 없는 이름이 있는 쿼리 필드의 데이터의 원래 원본을 결정할 수 있습니다. 자세한 내용은 DAO 도움말의 "소스필드, 소스테이블 속성" 항목을 참조하십시오. [CDaoTableDef::CreateField를](../../mfc/reference/cdaotabledef-class.md#createfield)사용하여 테이블def에 대해 이 속성을 설정할 수 있습니다.

*m_strValidationRule*<br/>
필드에 있는 데이터가 변경되었거나 테이블에 추가될 때 데이터의 유효성을 검사하는 값입니다. 자세한 내용은 DAO 도움말의 "유효성 검사규칙 속성" 항목을 참조하십시오. [CDaoTableDef::CreateField를](../../mfc/reference/cdaotabledef-class.md#createfield)사용하여 테이블def에 대해 이 속성을 설정할 수 있습니다.

테이블defs에 대한 관련 정보는 `m_strValidationRule` [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) 구조의 멤버를 참조하십시오.

*m_strValidationText*<br/>
DAO 필드 개체의 값이 ValidateRule 속성 설정에서 지정한 유효성 검사 규칙을 충족하지 않는 경우 응용 프로그램이 표시하는 메시지의 텍스트를 지정하는 값입니다. 자세한 내용은 DAO 도움말의 "유효성 검사텍스트 속성" 항목을 참조하십시오. [CDaoTableDef::CreateField를](../../mfc/reference/cdaotabledef-class.md#createfield)사용하여 테이블def에 대해 이 속성을 설정할 수 있습니다.

*m_strDefaultValue*<br/>
DAO 필드 개체의 기본값입니다. 새 레코드를 만들면 DefaultValue 속성 설정이 필드의 값으로 자동으로 입력됩니다. 자세한 내용은 DAO 도움말의 "DefaultValue 속성" 항목을 참조하십시오. [CDaoTableDef::CreateField를](../../mfc/reference/cdaotabledef-class.md#createfield)사용하여 테이블def에 대해 이 속성을 설정할 수 있습니다.

## <a name="remarks"></a>설명

위의 기본, 보조 및 모든 에 대한 참조는 `GetFieldInfo` [클래스 CDaoTableDef,](../../mfc/reference/cdaotabledef-class.md#getfieldinfo) [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)및 [CDaoRecordset의](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)멤버 함수에 의해 정보가 반환되는 방법을 나타냅니다.

필드 개체는 MFC 클래스로 표시되지 않습니다. 대신 다음 클래스의 MFC 개체의 기본 DAO 개체에는 [CDaoTableDef,](../../mfc/reference/cdaotabledef-class.md) [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)및 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)의 필드 개체 컬렉션이 포함되어 있습니다. 이러한 클래스는 필드 정보의 일부 개별 항목에 액세스하는 멤버 함수를 제공하거나 `CDaoFieldInfo` 포함된 개체의 `GetFieldInfo` 멤버 함수를 호출하여 개체를 사용하여 한 번에 모두 액세스할 수 있습니다.

개체 속성을 `CDaoFieldInfo` 검사하는 데 사용하는 것 외에도 tabledef에서 새 필드를 만들기 위한 입력 매개 변수를 생성할 수도 있습니다. 이 작업에 는 더 간단한 옵션을 사용할 수 있지만 더 세밀한 제어를 원하는 경우 `CDaoFieldInfo` 매개 변수를 사용하는 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) 버전을 사용할 수 있습니다.

`GetFieldInfo` 멤버 함수(필드를 포함하는 클래스)에서 검색한 정보는 구조에 `CDaoFieldInfo` 저장됩니다. 필드 `GetFieldInfo` 개체가 저장되는 필드 컬렉션을 포함하는 개체의 멤버 함수를 호출합니다. `CDaoFieldInfo`또한 디버그 `Dump` 빌드에서 멤버 함수를 정의합니다. 개체의 `Dump` 내용을 덤프하는 데 사용할 수 있습니다. `CDaoFieldInfo`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고 항목

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
