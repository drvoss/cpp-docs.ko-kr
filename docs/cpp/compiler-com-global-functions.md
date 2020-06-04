---
title: 컴파일러 COM 전역 함수
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
ms.openlocfilehash: c0a9c742ad9dcbb05ed2d78c954d5a597e3b57cb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189782"
---
# <a name="compiler-com-global-functions"></a>컴파일러 COM 전역 함수

**Microsoft 전용**

다음 루틴을 사용할 수 있습니다.

|함수|설명|
|--------------|-----------------|
|[_com_raise_error](../cpp/com-raise-error.md)|실패에 대 한 응답으로 [_com_error](../cpp/com-error-class.md) 을 throw 합니다.|
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|COM 오류 처리에 사용되는 기본 함수를 대체합니다.|
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|`BSTR` 값을 `char *`으로 변환합니다.|
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|`char *` 값을 `BSTR`으로 변환합니다.|

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)<br/>
[컴파일러 COM 지원](../cpp/compiler-com-support.md)
