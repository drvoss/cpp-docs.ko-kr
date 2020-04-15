---
title: CComPtr 클래스
description: Microsoft C++ 활성 템플릿 라이브러리(ATL) 클래스 CComPtr에 대한 참조 가이드입니다.
ms.date: 02/07/2020
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 855466225db2672755658dcbbc9a266d09e0e7be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327521"
---
# <a name="ccomptr-class"></a>CComPtr 클래스

COM 인터페이스 포인터를 관리하기 위한 스마트 포인터 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template<class T>
class CComPtr
```

### <a name="parameters"></a>매개 변수

*T*<br/>
저장할 포인터 유형을 지정하는 COM 인터페이스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComPtr:::CComPtr](#ccomptr)|생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CComPtr::연산자 =](#operator_eq)|멤버 포인터에 포인터를 할당합니다.|

## <a name="remarks"></a>설명

ATL은 `CComPtr` COM 인터페이스 포인터를 관리하기 위해 [CComQIPtr을](../../atl/reference/ccomqiptr-class.md) 사용합니다. 둘 다 [CComPtrBase에서](../../atl/reference/ccomptrbase-class.md)파생되며 둘 다 자동 참조 계산을 수행합니다.

및 `CComPtr` [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 클래스는 자동 참조 계수를 수행하여 메모리 누수를 제거하는 데 도움이 될 수 있습니다.  다음 함수는 모두 동일한 논리 작업을 수행합니다. 그러나 두 번째 버전은 `CComPtr` 클래스를 사용하기 때문에 오류가 발생할 가능성이 적을 수 있습니다.

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

디버그 빌드에서 코드 추적을 위해 atlsd.lib를 연결합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomptrccomptr"></a><a name="ccomptr"></a>CComPtr:::CComPtr

생성자입니다.

```cpp
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>매개 변수

*Lp 로*<br/>
인터페이스 포인터를 초기화하는 데 사용됩니다.

*T*<br/>
COM 인터페이스입니다.

### <a name="remarks"></a>설명

null 포인터가 아닌 경우 `AddRef` *lp에*대한 인수 호출을 하는 생성자입니다. null이 아닌 개체는 `Release` CComPtr 개체의 소멸또는 새 개체가 CComPtr 개체에 할당된 경우 호출됩니다.

## <a name="ccomptroperator-"></a><a name="operator_eq"></a>CComPtr::연산자 =

대입 연산자입니다.

```cpp
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>Return Value

업데이트된 `CComPtr` 개체에 대한 포인터 반환

### <a name="remarks"></a>설명

이 작업은 새 개체AddRefs 및 기존 개체(있는 경우)를 해제합니다.

## <a name="see-also"></a>참고 항목

[CComPtr:::CComPtr](#ccomptr)<br/>
[CComQIPtr:::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
