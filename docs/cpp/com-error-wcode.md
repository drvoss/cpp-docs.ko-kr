---
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: 92dffbdbe034ef55be04c1b7d204be6880d8d4b2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190198"
---
# <a name="_com_errorwcode"></a>_com_error::WCode

**Microsoft 전용**

캡슐화 된 HRESULT에 매핑된 16 비트 오류 코드를 검색 합니다.

## <a name="syntax"></a>구문

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>반환 값

HRESULT가 0x80040200 범위 내에 있는 경우 `WCode` 메서드는 HRESULT를 0x8004FFFF 0x80040200;를 반환 합니다. 그렇지 않으면 0을 반환 합니다.

## <a name="remarks"></a>주의

`WCode` 메서드는 COM 지원 코드에서 발생 하는 매핑을 실행 취소 하는 데 사용 됩니다. `dispinterface` 속성 또는 메서드에 대 한 래퍼는 인수를 패키지 하 고 `IDispatch::Invoke`를 호출 하는 지원 루틴을 호출 합니다. 반환 시 `DISP_E_EXCEPTION`의 오류 HRESULT가 반환 되 면 `IDispatch::Invoke`전달 된 `EXCEPINFO` 구조에서 오류 정보가 검색 됩니다. 오류 코드는 `EXCEPINFO` 구조의 `wCode` 멤버에 저장 된 16 비트 값 이거나 `EXCEPINFO` 구조의 `scode` 멤버에 있는 전체 32 비트 값일 수 있습니다. 16 비트 `wCode` 반환 되는 경우 먼저 32 비트 오류 HRESULT에 매핑되어야 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error 클래스](../cpp/com-error-class.md)
