---
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: b3c79bb069ef504680e83359d6ec90c803f16d9d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180591"
---
# <a name="_com_errorhelpcontext"></a>_com_error::HelpContext

**Microsoft 전용**

`IErrorInfo::GetHelpContext` 함수를 호출 합니다.

## <a name="syntax"></a>구문

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>Return Value

`_com_error` 개체 내에 기록 된 `IErrorInfo` 개체의 `IErrorInfo::GetHelpContext` 결과를 반환 합니다. 기록 된 `IErrorInfo` 개체가 없으면 0이 반환 됩니다.

## <a name="remarks"></a>설명

`IErrorInfo::GetHelpContext` 메서드를 호출 하는 동안 발생 하는 모든 오류는 무시 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error 클래스](../cpp/com-error-class.md)
