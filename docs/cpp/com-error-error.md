---
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 8e2c52d10b15822703329dcea18944773f5784ea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180760"
---
# <a name="_com_errorerror"></a>_com_error::Error

**Microsoft 전용**

생성자에 전달 된 HRESULT를 검색 합니다.

## <a name="syntax"></a>구문

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>반환 값

생성자에 전달 된 원시 HRESULT 항목입니다.

## <a name="remarks"></a>주의

`_com_error` 개체의 캡슐화 된 HRESULT 항목을 검색 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error 클래스](../cpp/com-error-class.md)
