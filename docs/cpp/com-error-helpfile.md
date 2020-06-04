---
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: 775adfa7d5dd5aca098edcd793c2164d65fe7efa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190224"
---
# <a name="_com_errorhelpfile"></a>_com_error::HelpFile

**Microsoft 전용**

`IErrorInfo::GetHelpFile` 함수를 호출 합니다.

## <a name="syntax"></a>구문

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>반환 값

`_com_error` 개체 내에 기록 된 `IErrorInfo` 개체의 `IErrorInfo::GetHelpFile` 결과를 반환 합니다. 결과 BSTR은 `_bstr_t` 개체에 캡슐화됩니다. `IErrorInfo` 기록 되지 않으면 빈 `_bstr_t`을 반환 합니다.

## <a name="remarks"></a>주의

`IErrorInfo::GetHelpFile` 메서드를 호출 하는 동안 발생 하는 모든 오류는 무시 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error 클래스](../cpp/com-error-class.md)
