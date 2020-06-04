---
title: CHandle 클래스
ms.date: 07/09/2019
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
ms.openlocfilehash: 4b883bdf3159c40f8d74866f04f655ae73d82a8a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747703"
---
# <a name="chandle-class"></a>CHandle 클래스

이 클래스는 핸들 개체를 만들고 사용하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
class CHandle
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C핸들::C핸들](#chandle)|생성자입니다.|
|[C핸들::~C핸들](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C핸들:::연결](#attach)|이 메서드를 호출하여 개체를 `CHandle` 기존 핸들에 연결합니다.|
|[C핸들::닫기](#close)|이 메서드를 호출하여 개체를 `CHandle` 닫습니다.|
|[C핸들::D에타치](#detach)|이 메서드를 호출하여 개체에서 `CHandle` 핸들을 분리합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C핸들::연산자 핸들](#operator_handle)|저장된 핸들의 값을 반환합니다.|
|[C핸들::연산자 =](#operator_eq)|대입 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C핸들:m_h](#m_h)|핸들을 저장하는 멤버 변수입니다.|

## <a name="remarks"></a>설명

핸들이 `CHandle` 필요할 때마다 개체를 `CHandle` 사용할 수 있습니다.

> [!NOTE]
> 일부 API 함수는 NULL을 비어 있거나 잘못된 핸들로 사용하고 다른 함수는 INVALID_HANDLE_VALUE 사용합니다. `CHandle`NULL만 사용하고 INVALID_HANDLE_VALUE 실제 핸들로 처리합니다. INVALID_HANDLE_VALUE 반환할 수 있는 API를 호출하는 경우 [CHandle:::Attach를](#attach) 호출하거나 `CHandle` 생성자에게 전달하기 전에 이 값을 확인하고 NULL을 전달해야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="chandleattach"></a><a name="attach"></a>C핸들:::연결

이 메서드를 호출하여 개체를 `CHandle` 기존 핸들에 연결합니다.

```cpp
void Attach(HANDLE h) throw();
```

### <a name="parameters"></a>매개 변수

*H*<br/>
`CHandle`핸들 *h의*소유권을 취할 것입니다.

### <a name="remarks"></a>설명

`CHandle` *h* 핸들에 개체를 할당한 다음 **h.Detach()를**호출합니다. 디버그 빌드에서 *h가* NULL이면 ATLASSERT가 발생합니다. 핸들의 유효성에 대한 다른 검사는 이루어지지 않습니다.

## <a name="chandlechandle"></a><a name="chandle"></a>C핸들::C핸들

생성자입니다.

```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```

### <a name="parameters"></a>매개 변수

*H*<br/>
기존 핸들 `CHandle`또는 .

### <a name="remarks"></a>설명

선택적으로 `CHandle` 기존 핸들 또는 `CHandle` 개체를 사용하여 새 개체를 만듭니다.

## <a name="chandlechandle"></a><a name="dtor"></a>C핸들::~C핸들

소멸자입니다.

```
~CHandle() throw();
```

### <a name="remarks"></a>설명

`CHandle` [CHandle ::Close](#close)를 호출하여 개체를 해제합니다.

## <a name="chandleclose"></a><a name="close"></a>C핸들::닫기

이 메서드를 호출하여 개체를 `CHandle` 닫습니다.

```cpp
void Close() throw();
```

### <a name="remarks"></a>설명

열린 개체 핸들을 닫습니다. 핸들이 NULL인 경우 이미 호출된 `Close` 경우 디버그 빌드에서 ATLASSERT가 발생합니다.

## <a name="chandledetach"></a><a name="detach"></a>C핸들::D에타치

이 메서드를 호출하여 개체에서 `CHandle` 핸들을 분리합니다.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Return Value

분리중인 핸들을 반환합니다.

### <a name="remarks"></a>설명

핸들의 소유권을 해제합니다.

## <a name="chandlem_h"></a><a name="m_h"></a>C핸들:m_h

핸들을 저장하는 멤버 변수입니다.

```
HANDLE m_h;
```

## <a name="chandleoperator-"></a><a name="operator_eq"></a>C핸들::연산자 =

할당 연산자입니다.

```
CHandle& operator=(CHandle& h) throw();
```

### <a name="parameters"></a>매개 변수

*H*<br/>
`CHandle`핸들 *h의*소유권을 취할 것입니다.

### <a name="return-value"></a>Return Value

새 `CHandle` 개체에 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

개체에 `CHandle` 현재 핸들이 포함되어 있으면 닫힙싸게 됩니다. 전달되는 개체에는 `CHandle` 핸들 참조가 NULL로 설정됩니다. 이렇게 하면 두 `CHandle` 개체에 동일한 활성 핸들이 포함되지 않습니다.

## <a name="chandleoperator-handle"></a><a name="operator_handle"></a>C핸들::연산자 핸들

저장된 핸들의 값을 반환합니다.

```
operator HANDLE() const throw();
```

### <a name="remarks"></a>설명

[CHandle::m_h에](#m_h)저장된 값을 반환합니다.

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)
