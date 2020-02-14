---
title: CComPtr 클래스
description: Microsoft C++ ATL (Active Template Library) 클래스 CComPtr에 대 한 참조 가이드입니다.
ms.date: 02/07/2020
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 74a12b460f55a782fa2747b02f7d00287786fae6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127407"
---
# <a name="ccomptr-class"></a>CComPtr 클래스

COM 인터페이스 포인터를 관리 하기 위한 스마트 포인터 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template<class T>
class CComPtr
```

### <a name="parameters"></a>매개 변수

*T*<br/>
저장할 포인터의 형식을 지정 하는 COM 인터페이스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[CComPtr:: CComPtr](#ccomptr)|생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|name|설명|
|----------|-----------------|
|[CComPtr:: operator =](#operator_eq)|멤버 포인터에 대 한 포인터를 할당 합니다.|

## <a name="remarks"></a>설명

ATL은 `CComPtr` 및 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 를 사용 하 여 COM 인터페이스 포인터를 관리 합니다. 둘 다 [Ccomptrbase](../../atl/reference/ccomptrbase-class.md)에서 파생 되며, 둘 다 자동 참조 계산을 수행 합니다.

`CComPtr` 및 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 클래스는 자동 참조 계산을 수행 하 여 메모리 누수를 제거 하는 데 도움이 됩니다.  다음 함수는 모두 동일한 논리 작업을 수행 합니다. 그러나 두 번째 버전은 `CComPtr` 클래스를 사용 하기 때문에 오류가 발생할 수 있습니다.

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

디버그 빌드에서 코드 추적을 위해 코드 추적을 링크 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

## <a name="ccomptr"></a>CComPtr:: CComPtr

생성자입니다.

```cpp
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>매개 변수

*lp*<br/>
인터페이스 포인터를 초기화 하는 데 사용 됩니다.

*T*<br/>
COM 인터페이스입니다.

### <a name="remarks"></a>설명

인수 호출을 사용 하는 생성자가 null 포인터가 아닌 경우 *lp*에서 `AddRef`. Null이 아닌 소유 된 개체는 CComPtr 개체의 소멸에 대 한 `Release` 호출을 가져오거나 새 개체가 CComPtr 개체에 할당 된 경우에는를 호출 합니다.

## <a name="operator_eq"></a>CComPtr:: operator =

대입 연산자입니다.

```cpp
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>Return Value

업데이트 된 `CComPtr` 개체에 대 한 포인터를 반환 합니다.

### <a name="remarks"></a>설명

이 작업은 새 개체를 추가 하 고 기존 개체 (있는 경우)를 해제 합니다.

## <a name="see-also"></a>참고 항목

[CComPtr:: CComPtr](#ccomptr)<br/>
[CComQIPtr:: CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
