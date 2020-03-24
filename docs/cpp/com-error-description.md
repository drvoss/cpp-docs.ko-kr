---
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: de2275f096fe2fde96e64cbc3034602a1fde5e88
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180773"
---
# <a name="_com_errordescription"></a>_com_error::Description

**Microsoft 전용**

`IErrorInfo::GetDescription` 함수를 호출 합니다.

## <a name="syntax"></a>구문

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>반환 값

`_com_error` 개체 내에 기록 된 `IErrorInfo` 개체의 `IErrorInfo::GetDescription` 결과를 반환 합니다. 결과 `BSTR`은 `_bstr_t` 개체에 캡슐화됩니다. `IErrorInfo` 기록 되지 않으면 빈 `_bstr_t`을 반환 합니다.

## <a name="remarks"></a>주의

`IErrorInfo::GetDescription` 함수를 호출 하 고 `_com_error` 개체 내에 기록 된 `IErrorInfo`를 검색 합니다. `IErrorInfo::GetDescription` 메서드를 호출 하는 동안 발생 하는 모든 오류는 무시 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error 클래스](../cpp/com-error-class.md)
