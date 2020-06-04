---
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: f2194e0e54a93d3227b84d893f9d3f208d972d09
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180513"
---
# <a name="_com_errorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Microsoft 전용**

16 비트 *Wcode* 를 32 비트 HRESULT에 매핑합니다.

## <a name="syntax"></a>구문

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>매개 변수

*wCode*<br/>
32 비트 HRESULT에 매핑할 16 비트 *Wcode* 입니다.

## <a name="return-value"></a>Return Value

16 비트 *Wcode*에서 매핑된 32 비트 HRESULT입니다.

## <a name="remarks"></a>설명

[Wcode](../cpp/com-error-wcode.md) 멤버 함수를 참조 하세요.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error 클래스](../cpp/com-error-class.md)
