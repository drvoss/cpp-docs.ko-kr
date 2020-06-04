---
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 43dd21297ddd54863d535402dddd59243d589eec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180526"
---
# <a name="_com_errorsource"></a>_com_error::Source

**Microsoft 전용**

`IErrorInfo::GetSource` 함수를 호출 합니다.

## <a name="syntax"></a>구문

```
_bstr_t Source() const;
```

## <a name="return-value"></a>Return Value

`_com_error` 개체 내에 기록 된 `IErrorInfo` 개체의 `IErrorInfo::GetSource` 결과를 반환 합니다. 결과 `BSTR`은 `_bstr_t` 개체에 캡슐화됩니다. `IErrorInfo` 기록 되지 않으면 빈 `_bstr_t`을 반환 합니다.

## <a name="remarks"></a>설명

`IErrorInfo::GetSource` 메서드를 호출 하는 동안 발생 하는 모든 오류는 무시 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error 클래스](../cpp/com-error-class.md)
