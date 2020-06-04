---
title: CDaoException 클래스
ms.date: 09/17/2019
f1_keywords:
- CDaoException
- AFXDAO/CDaoException
- AFXDAO/CDaoException::CDaoException
- AFXDAO/CDaoException::GetErrorCount
- AFXDAO/CDaoException::GetErrorInfo
- AFXDAO/CDaoException::m_nAfxDaoError
- AFXDAO/CDaoException::m_pErrorInfo
- AFXDAO/CDaoException::m_scode
helpviewer_keywords:
- CDaoException [MFC], CDaoException
- CDaoException [MFC], GetErrorCount
- CDaoException [MFC], GetErrorInfo
- CDaoException [MFC], m_nAfxDaoError
- CDaoException [MFC], m_pErrorInfo
- CDaoException [MFC], m_scode
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
ms.openlocfilehash: 935d7870d68554d702e2ad762e83343cb518b2b8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754733"
---
# <a name="cdaoexception-class"></a>CDaoException 클래스

DAO(Data Access Objects)를 기반으로 하는 MFC 데이터베이스 클래스에서 발생하는 예외 상태를 나타냅니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다.

## <a name="syntax"></a>구문

```
class CDaoException : public CException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDao예외::CDao예외](#cdaoexception)|`CDaoException` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDaoException::GetErrorCount](#geterrorcount)|데이터베이스 엔진의 오류 컬렉션에서 오류 수를 반환합니다.|
|[CDaoException::GetErrorInfo](#geterrorinfo)|오류 컬렉션의 특정 오류 개체에 대한 오류 정보를 반환합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO 클래스의 오류에 대한 확장된 오류 코드가 포함되어 있습니다.|
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|하나의 DAO 오류 개체에 대한 정보를 포함하는 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 개체에 대한 포인터입니다.|
|[CDao예외::m_scode](#m_scode)|오류와 연결된 [SCODE](#m_scode) 값입니다.|

## <a name="remarks"></a>설명

클래스에는 예외의 원인을 확인하는 데 사용할 수 있는 공용 데이터 멤버가 포함됩니다. `CDaoException`개체는 DAO 데이터베이스 클래스의 멤버 함수에 의해 생성되고 throw됩니다.

> [!NOTE]
> DAO 데이터베이스 클래스는 ODBC(개방형 데이터베이스 연결)를 기반으로 하는 MFC 데이터베이스 클래스와 구별됩니다. 모든 DAO 데이터베이스 클래스 이름에는 "CDao" 접두사가 있습니다. DAO 클래스를 사용하여 ODBC 데이터 원본에 계속 액세스할 수 있습니다. 일반적으로 DAO를 기반으로 하는 MFC 클래스는 ODBC를 기반으로 하는 MFC 클래스보다 더 유능합니다. DAO 기반 클래스는 자체 데이터베이스 엔진을 통해 ODBC 드라이버를 통해 데이터에 액세스할 수 있습니다. 또한 DAO 기반 클래스는 DAO를 직접 호출하지 않고도 클래스를 통해 테이블을 추가하는 것과 같은 DDL(데이터 정의 언어) 작업을 지원합니다. ODBC 클래스에서 throw된 예외에 대한 자세한 내용은 [CDBException](../../mfc/reference/cdbexception-class.md)을 참조하십시오.

[CATCH](../../mfc/reference/exception-processing.md#catch) 식의 범위 내에서 예외 개체에 액세스할 수 있습니다. [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) global 함수를 사용하여 사용자 고유의 코드에서 `CDaoException` 개체를 throw할 수도 있습니다.

MFC에서 모든 DAO 오류는 형식의 `CDaoException`예외로 표시됩니다. 이 형식의 예외를 Catch하면 멤버 `CDaoException` 함수를 사용하여 데이터베이스 엔진의 오류 컬렉션에 저장된 DAO 오류 개체에서 정보를 검색할 수 있습니다. 각 오류가 발생하면 하나 이상의 오류 개체가 오류 컬렉션에 배치됩니다. 일반적으로 컬렉션에는 오류 개체가 하나만 포함되어 있습니다. ODBC 데이터 원본을 사용하는 경우 여러 오류 개체를 얻을 가능성이 높습니다. 다른 DAO 작업이 오류를 생성하면 오류 컬렉션이 지워지고 새 오류 개체가 오류 컬렉션에 배치됩니다. 오류를 생성하지 않는 DAO 작업은 오류 컬렉션에 영향을 주지 않습니다.

DAO 오류 코드의 경우 DAOERR 파일을 참조하십시오. H. 관련 정보는 DAO 도움말의 "트래핑 가능한 데이터 액세스 오류" 항목을 참조하십시오.

일반적으로 예외 처리 또는 개체에 `CDaoException` 대한 자세한 내용은 [MFC(예외 처리)](../../mfc/exception-handling-in-mfc.md) 및 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)문서를 참조하십시오. 두 번째 문서에는 DAO의 예외 처리를 보여 주는 예제 코드가 포함되어 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDaoException`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="cdaoexceptioncdaoexception"></a><a name="cdaoexception"></a>CDao예외::CDao예외

`CDaoException` 개체를 생성합니다.

```
CDaoException();
```

### <a name="remarks"></a>설명

일반적으로 프레임워크는 코드에서 예외를 throw할 때 예외 개체를 만듭니다. 예외 개체를 명시적으로 생성할 필요가 거의 없습니다. 사용자 고유의 코드에서 를 `CDaoException` throw하려면 전역 함수 [AfxThrowDaoException을](../../mfc/reference/exception-processing.md#afxthrowdaoexception)호출합니다.

그러나 MFC 클래스가 캡슐화하는 DAO 인터페이스 포인터를 통해 DAO를 직접 호출하는 경우 예외 개체를 명시적으로 만들 수 있습니다. 이 경우 DAO에서 오류 정보를 검색해야 할 수 있습니다. DAODatabases 인터페이스를 통해 DAO 메서드를 작업 영역의 데이터베이스 컬렉션에 호출할 때 DAO에서 오류가 발생한다고 가정합니다.

##### <a name="to-retrieve-the-dao-error-information"></a>DAO 오류 정보를 검색하려면

1. 개체를 `CDaoException` 생성합니다.

1. 예외 개체의 [GetErrorCount](#geterrorcount) 멤버 함수를 호출하여 데이터베이스 엔진의 오류 컬렉션에 있는 오류 개체 수를 확인합니다. (일반적으로 ODBC 데이터 원본을 사용하지 않는 한 하나만 사용됩니다.)

1. 예외 개체의 [GetErrorInfo](#geterrorinfo) 멤버 함수를 호출하여 예외 개체를 통해 컬렉션의 인덱스별로 한 번에 하나의 특정 오류 개체를 검색합니다. 예외 개체를 하나의 DAO 오류 개체에 대한 프록시로 간주합니다.

1. [m_pErrorInfo](#m_perrorinfo) 데이터 멤버에서 반환되는 `GetErrorInfo` 현재 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 구조를 검사합니다. 해당 멤버는 DAO 오류에 대한 정보를 제공합니다.

1. ODBC 데이터 원본의 경우 필요에 따라 3단계와 4단계를 반복하여 오류 개체를 더 많이 사용하십시오.

1. 힙에 예외 객체를 생성한 경우 완료할 때 **delete** 연산자로 삭제합니다.

MFC DAO 클래스의 오류 처리에 대한 자세한 내용은 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)문서를 참조하십시오.

## <a name="cdaoexceptiongeterrorcount"></a><a name="geterrorcount"></a>CDao예외::GetErrorCount

이 멤버 함수를 호출하여 데이터베이스 엔진의 오류 컬렉션에서 DAO 오류 개체 수를 검색합니다.

```
short GetErrorCount();
```

### <a name="return-value"></a>Return Value

데이터베이스 엔진의 오류 컬렉션에 있는 DAO 오류 개체 수입니다.

### <a name="remarks"></a>설명

이 정보는 오류 컬렉션을 반복하여 컬렉션에서 하나 이상의 DAO 오류 개체를 각각 검색하는 데 유용합니다. 인덱스 또는 DAO 오류 번호로 오류 개체를 검색하려면 [GetErrorInfo](#geterrorinfo) 멤버 함수를 호출합니다.

> [!NOTE]
> 일반적으로 오류 컬렉션에는 오류 개체가 하나만 있습니다. 그러나 ODBC 데이터 원본으로 작업하는 경우 둘 이상의 데이터가 있을 수 있습니다.

## <a name="cdaoexceptiongeterrorinfo"></a><a name="geterrorinfo"></a>CDao예외::GetErrorInfo

오류 컬렉션의 특정 오류 개체에 대한 오류 정보를 반환합니다.

```cpp
void GetErrorInfo(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스별 조회를 위한 데이터베이스 엔진의 오류 컬렉션의 오류 정보 인덱스입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하여 예외에 대한 다음과 같은 종류의 정보를 얻습니다.

- 오류 코드

- 원본

- Description

- 도움말 파일

- 도움말 컨텍스트

`GetErrorInfo`은 예외 개체의 데이터 `m_pErrorInfo` 멤버에 정보를 저장합니다. 반환된 정보에 대한 간략한 설명은 [m_pErrorInfo](#m_perrorinfo)를 참조하십시오. MFC에서 throw된 `CDaoException` 형식의 예외를 Catch하면 멤버가 `m_pErrorInfo` 이미 채워집니다. DAO를 직접 호출하도록 선택한 경우 예외 개체의 `GetErrorInfo` 멤버 함수를 `m_pErrorInfo`직접 호출하여 채워야 합니다. 자세한 설명은 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 구조를 참조하십시오.

DAO 예외 및 예제 코드에 대한 자세한 내용은 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)문서를 참조하십시오.

## <a name="cdaoexceptionm_nafxdaoerror"></a><a name="m_nafxdaoerror"></a>CDao예외::m_nAfxDaoError

MFC 확장 오류 코드가 포함되어 있습니다.

### <a name="remarks"></a>설명

이 코드는 MFC DAO 클래스의 특정 구성 요소가 잘못된 경우에 제공됩니다.

가능한 값은 다음과 같습니다.

- NO_AFX_DAO_ERROR 가장 최근의 작업으로 인해 MFC 확장 오류가 발생하지 않았습니다. 그러나 이 작업으로 인해 DAO 또는 OLE에서 다른 오류가 발생했을 수 있으므로 [m_pErrorInfo](#m_perrorinfo) 확인하고 [m_scode.](#m_scode)

- AFX_DAO_ERROR_ENGINE_INITIALIZATION MFC는 Microsoft Jet 데이터베이스 엔진을 초기화할 수 없습니다. OLE가 초기화하지 못했거나 DAO 데이터베이스 엔진 개체의 인스턴스를 만드는 것이 불가능했을 수 있습니다. 이러한 문제는 일반적으로 DAO 또는 OLE의 잘못된 설치를 제안합니다.

- AFX_DAO_ERROR_DFX_BIND DFx(레코드 필드 교환) 함수 호출에 사용된 주소가 없거나 유효하지 않습니다(주소가 데이터를 바인딩하는 데 사용되지 않음). DFX 호출에서 잘못된 주소를 전달했거나 DFX 작업 간에 주소가 유효하지 않을 수 있습니다.

- AFX_DAO_ERROR_OBJECT_NOT_OPEN querydef 또는 열려 있는 상태가 아닌 tabledef 개체를 기반으로 레코드 집합을 열려 있는 것으로 설정했습니다.

## <a name="cdaoexceptionm_perrorinfo"></a><a name="m_perrorinfo"></a>CDao예외:m_pErrorInfo

[GetErrorInfo](#geterrorinfo)를 `CDaoErrorInfo` 호출하여 마지막으로 검색한 DAO 오류 개체에 대한 정보를 제공하는 구조체에 대한 포인터가 포함되어 있습니다.

### <a name="remarks"></a>설명

이 개체에는 다음 정보가 포함되어 있습니다.

|CDaoErrorInfo 회원|정보|의미|
|--------------------------|-----------------|-------------|
|`m_lErrorCode`|오류 코드|DAO 오류 코드|
|`m_strSource`|원본|원래 오류를 생성한 개체 또는 응용 프로그램의 이름입니다.|
|`m_strDescription`|Description|오류와 관련된 설명 문자열|
|`m_strHelpFile`|도움말 파일|사용자가 문제에 대한 정보를 얻을 수 있는 Windows 도움말 파일에 대한 경로|
|`m_lHelpContext`|도움말 컨텍스트|DAO 도움말 파일의 토픽에 대한 컨텍스트 ID|

`CDaoErrorInfo` 개체에 포함된 정보에 대한 자세한 내용은 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 구조를 참조하십시오.

## <a name="cdaoexceptionm_scode"></a><a name="m_scode"></a>CDao예외::m_scode

오류를 설명하는 형식 `SCODE` 값을 포함합니다.

### <a name="remarks"></a>설명

OLE 코드입니다. 거의 모든 경우에 다른 `CDaoException` 데이터 멤버에서 보다 구체적인 MFC 또는 DAO 오류 정보를 사용할 수 있으므로 이 값을 거의 사용할 필요가 없습니다.

SCODE에 대한 자세한 내용은 Windows SDK에서 [OLE 오류 코드의 구성](/windows/win32/com/structure-of-com-error-codes) 항목을 참조하십시오. SCODE 데이터 형식은 HRESULT 데이터 형식에 매핑됩니다.

## <a name="see-also"></a>참조

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)
