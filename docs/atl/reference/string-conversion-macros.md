---
title: 문자열 변환 매크로
ms.date: 11/04/2016
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
ms.openlocfilehash: 8df496b78334d26e7d3664642b2e9d93d6149843
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325847"
---
# <a name="string-conversion-macros"></a>문자열 변환 매크로

이러한 매크로는 문자열 변환 기능을 제공합니다.

## <a name="atl-and-mfc-string-conversion-macros"></a><a name="atl_and_mfc_string_conversion_macros"></a>ATL 및 MFC 문자열 변환 매크로

이 항목에서 설명하는 문자열 변환 매크로는 ATL과 MFC에 모두 사용 가능합니다. MFC 문자열 변환에 대한 자세한 내용은 [TN059: MFC MBCS/유니코드 변환 매크로](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) 및 [MFC 매크로 및 글로벌](../../mfc/reference/mfc-macros-and-globals.md)사용 참조.

## <a name="devmode-and-textmetric-string-conversion-macros"></a><a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE 및 텍스트 메트릭 문자열 변환 매크로

이러한 매크로는 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 또는 [TEXTMETRIC](/windows/win32/api/wingdi/ns-wingdi-textmetricw) 구조의 복사본을 만들고 새 구조내의 문자열을 새 문자열 유형으로 변환합니다. 매크로는 새 구조에 대한 스택에 메모리를 할당하고 포인터를 새 구조로 반환합니다.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>설명

다음은 그 예입니다.

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

and:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

매크로 이름에서 소스 구조의 문자열 형식은 왼쪽(예: **A)이고**대상 구조의 문자열 형식은 오른쪽(예: **W)에**있습니다. **LPSTR의** 약자, **OLE는** LPOLESTR, **T는** LPTSTR을 의미하며 **W는** LPWSTR을 의미합니다.

따라서 DEVMODEA2W는 LPSTR 문자열이 `DEVMODE` 있는 `DEVMODE` 구조를 LPWSTR 문자열이 있는 구조로 복사하고 `TEXTMETRIC` TEXTMETRICOLE2T는 LPOLESTR 문자열이 있는 `TEXTMETRIC` 구조를 LPTSTR 문자열이 있는 구조로 복사합니다.

`DEVMODE` 구조에서 변환된 두 문자열은 장치 이름()`dmDeviceName`및 양식 이름()입니다.`dmFormName` `DEVMODE` 문자열 변환 매크로도 구조 크기()를`dmSize`업데이트합니다.

`TEXTMETRIC` 구조에서 변환된 네 개의 문자열은 첫`tmFirstChar`번째 문자`tmLastChar`(), 마지막`tmDefaultChar`문자 (), 기본`tmBreakChar`문자 (), 및 break 문자 ()입니다.

`DEVMODE` 문자열 `TEXTMETRIC` 변환 매크로의 동작은 컴파일러 지시문(있는 경우)에 따라 달라집니다. 소스와 대상 형식이 같으면 변환이 수행되지 않습니다. 컴파일러 지시문은 다음과 같이 **T와** **OLE를** 변경합니다.

|적용되는 컴파일러 지시문|T의 변경 결과|OLE의 변경 결과|
|----------------------------------|---------------|-----------------|
|없음|**A**|**W**|
|**\_유니코드**|**W**|**W**|
|**올레2안시**|**A**|**A**|
|유니코드 및 **올레2ANSI** ** \_**|**W**|**A**|

다음 표에는 `DEVMODE` 및 `TEXTMETRIC` 문자열 변환 매크로가 나열되어 있습니다.

|||
|-|-|
|데브모데아2W|텍스트 메트릭A2W|
|데브모데올레2T|텍스트 메트릭올레2T|
|데브모드2올레|텍스트 메트릭T2OLE|
|데브모드W2A|텍스트 메트릭W2A|

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
