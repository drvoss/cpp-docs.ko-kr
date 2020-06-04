---
title: 고정스트링T 클래스
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: fe096185f6f0b71ad45757cd0b75ab13c41e5f5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317823"
---
# <a name="cfixedstringt-class"></a>고정스트링T 클래스

이 클래스는 고정된 문자 버퍼가 있는 문자열 개체를 나타냅니다.

## <a name="syntax"></a>구문

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>매개 변수

*문자열 유형*<br/>
고정 된 문자열 개체에 대 한 기본 `CStringT`클래스로 사용 하 고 모든 기반 형식일 수 있습니다. 몇 가지 `CString`예는 을 `CStringA`다음과 같습니다. `CStringW`

*t_nChars*<br/>
버퍼에 저장된 문자 수입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[고정스트링T::고정스트링T](#cfixedstringt)|문자열 개체의 생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C고정스트링T::연산자 =](#operator_eq)|개체에 새 값을 `CFixedStringT` 할당합니다.|

## <a name="remarks"></a>설명

이 클래스는 `CStringT`을 기반으로 하는 사용자 지정 문자열 클래스의 예입니다. 유사하지만 두 클래스는 구현에서 다릅니다. 주요 `CFixedStringT` 차이점은 다음과 `CStringT` 같습니다.

- 초기 문자 버퍼는 개체의 일부로 할당되며 *크기 t_nChars.* 이렇게 하면 `CFixedString` 개체가 성능을 위해 연속 메모리 청크를 차지할 수 있습니다. 그러나 `CFixedStringT` 개체의 내용이 *t_nChars*이상으로 증가하면 버퍼가 동적으로 할당됩니다.

- `CFixedStringT` 개체의 문자 버퍼는 항상 *길이(t_nChars)와*같습니다. 개체의 버퍼 크기에는 `CStringT` 제한이 없습니다.

- 에 대 `CFixedStringT` 한 메모리 관리자는 두 개 이상의 `CFixedStringT` 개체 간에 [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) 개체의 공유가 허용 되지 않도록 사용자 지정 됩니다. `CStringT`개체에는 이 제한이 없습니다.

일반적으로 문자열 개체에 `CFixedStringT` 대한 사용자 지정 및 메모리 관리에 대한 자세한 내용은 메모리 관리 및 [CStringT를](../../atl-mfc-shared/memory-management-with-cstringt.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>요구 사항

**헤더:** cstringt.h

## <a name="cfixedstringtcfixedstringt"></a><a name="cfixedstringt"></a>고정스트링T::고정스트링T

`CFixedStringT` 개체를 생성합니다.

```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT(const StringType& strSrc);
CFixedStringT(const StringType::XCHAR* pszSrc);
explicit CFixedStringT(const StringType::YCHAR* pszSrc);
explicit CFixedStringT(const unsigned char* pszSrc);
```

### <a name="parameters"></a>매개 변수

*pszSrc*<br/>
이 `CFixedStringT` 개체에 복사할 null 종료된 문자열입니다.

*strSrc*<br/>
이 `CFixedStringT` `CFixedStringT` 개체에 복사할 기존 개체입니다.

*pStringMgr*<br/>
개체의 메모리 관리자에 `CFixedStringT` 대한 포인터입니다. 에 대한 `IAtlStringMgr` 자세한 정보 `CFixedStringT`및 메모리 관리에 대한 자세한 내용은 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)를 참조하십시오.

### <a name="remarks"></a>설명

생성자는 입력 데이터를 새 할당된 저장소에 복사하므로 메모리 예외가 발생할 수 있음을 알고 있어야 합니다. 이러한 생성자 중 일부는 변환 함수역할을 합니다.

## <a name="cfixedstringtoperator-"></a><a name="operator_eq"></a>C고정스트링T::연산자 =

기존 `CFixedStringT` 개체를 새 데이터로 초기화합니다.

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT<StringType, t_nChars>& operator=(const char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& strSrc);
```

### <a name="parameters"></a>매개 변수

*pszSrc*<br/>
이 `CFixedStringT` 개체에 복사할 null 종료된 문자열입니다.

*strSrc*<br/>
이 `CFixedStringT` `CFixedStringT` 개체에 복사할 기존 입니다.

### <a name="remarks"></a>설명

새 저장소가 결과 `CFixedStringT` 개체를 보유하도록 할당되기 때문에 할당 연산자를 사용할 때마다 메모리 예외가 발생할 수 있습니다.

## <a name="see-also"></a>참고 항목

[CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
