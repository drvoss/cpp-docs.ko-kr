---
title: BoolStruct 구조체
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
- internal/Microsoft::WRL::Details::BoolStruct::Member
helpviewer_keywords:
- Microsoft::WRL::Details::BoolStruct structure
- Microsoft::WRL::Details::BoolStruct::Member data member
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
ms.openlocfilehash: cdec425e317585abbd9730447e2c4fbb19b8250a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865714"
---
# <a name="boolstruct-structure"></a>BoolStruct 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>설명

`BoolStruct` 구조는 `ComPtr`에서 인터페이스의 개체 수명을 관리 하는지 여부를 정의 합니다. `BoolStruct`는 [BoolType ()](comptr-class.md#operator-microsoft-wrl-details-booltype) 연산자에 의해 내부적으로 사용 됩니다.

## <a name="members"></a>구성원

### <a name="public-data-members"></a>공용 데이터 멤버

속성                          | Description
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[BoolStruct:: Member](#member) | 인터페이스의 개체 수명을 관리 하는 [ComPtr](comptr-class.md) 를 지정 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`BoolStruct`

## <a name="requirements"></a>요구 사항

**헤더:** internal. h

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="member"></a>BoolStruct:: Member

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
int Member;
```

### <a name="remarks"></a>설명

인터페이스의 개체 수명을 관리 하는 [ComPtr](comptr-class.md) 를 지정 합니다.
