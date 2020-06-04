---
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: cedb9ccadc63166c43d980333d93a195254700d8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180708"
---
# <a name="_com_errorerrorinfo"></a>_com_error::ErrorInfo

**Microsoft 전용**

생성자에 전달 된 `IErrorInfo` 개체를 검색 합니다.

## <a name="syntax"></a>구문

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>반환 값

생성자에 전달된 원시 `IErrorInfo` 항목입니다.

## <a name="remarks"></a>주의

`_com_error` 개체에서 캡슐화 된 `IErrorInfo` 항목을 검색 하거나, 기록 된 `IErrorInfo` 항목이 없으면 NULL을 검색 합니다. 호출자는 반환 된 개체의 사용을 마치면 반환 된 개체에서 `Release`를 호출 해야 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error 클래스](../cpp/com-error-class.md)
