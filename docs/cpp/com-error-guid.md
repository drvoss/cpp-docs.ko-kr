---
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: d5b05cd4e26f89d42ea23b605f5e6560795a0cfa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180643"
---
# <a name="_com_errorguid"></a>_com_error::GUID

**Microsoft 전용**

`IErrorInfo::GetGUID` 함수를 호출 합니다.

## <a name="syntax"></a>구문

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>반환 값

`_com_error` 개체 내에 기록 된 `IErrorInfo` 개체의 `IErrorInfo::GetGUID` 결과를 반환 합니다. `IErrorInfo` 개체가 기록 되지 않으면 `GUID_NULL`을 반환 합니다.

## <a name="remarks"></a>주의

`IErrorInfo::GetGUID` 메서드를 호출 하는 동안 발생 하는 모든 오류는 무시 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error 클래스](../cpp/com-error-class.md)
