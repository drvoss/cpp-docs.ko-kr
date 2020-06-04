---
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: 35a497c273f15c9755d3607e7907a3a48dad8dc8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180565"
---
# <a name="_com_errorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft 전용**

32 비트 HRESULT를 16 비트 `wCode`매핑합니다.

## <a name="syntax"></a>구문

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>매개 변수

*hr*<br/>
16 비트 `wCode`에 매핑될 32 비트 HRESULT입니다.

## <a name="return-value"></a>Return Value

32 비트 HRESULT에서 매핑된 16 비트 `wCode`입니다.

## <a name="remarks"></a>설명

자세한 내용은 [_com_error:: WCode](../cpp/com-error-wcode.md) 를 참조 하세요.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error 클래스](../cpp/com-error-class.md)
