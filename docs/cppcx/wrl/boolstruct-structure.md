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
ms.openlocfilehash: 4f2a5acf6edb824cff2121c1b6444181b5cfcf98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371846"
---
# <a name="boolstruct-structure"></a>BoolStruct 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>설명

구조는 `BoolStruct` a가 `ComPtr` 인터페이스의 개체 수명을 관리하는지 여부를 정의합니다. `BoolStruct`[은 BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype) 연산자에서 내부적으로 사용됩니다.

## <a name="members"></a>멤버

### <a name="public-data-members"></a>공용 데이터 멤버

속성                          | Description
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[불스트럿::회원](#member) | [ComPtr이](comptr-class.md) 인터페이스의 개체 수명을 관리하는지 또는 그렇지 않은지 지정합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`BoolStruct`

## <a name="requirements"></a>요구 사항

**헤더:** 내부.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="boolstructmember"></a><a name="member"></a>불스트럿::회원

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
int Member;
```

### <a name="remarks"></a>설명

[ComPtr이](comptr-class.md) 인터페이스의 개체 수명을 관리하는지 또는 그렇지 않은지 지정합니다.
