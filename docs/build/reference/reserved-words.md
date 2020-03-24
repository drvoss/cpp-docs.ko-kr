---
title: 예약어
ms.date: 11/04/2016
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
ms.openlocfilehash: 16caacb77e052eebc8e2cd101990ee373535bd6e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171153"
---
# <a name="reserved-words"></a>예약어

다음 단어는 링커에 예약 되어 있습니다. 이러한 이름은 이름이 큰따옴표 ("")로 묶여 있는 경우에만 [모듈 정의 문에서](module-definition-dot-def-files.md) 인수로 사용할 수 있습니다.

||||
|-|-|-|
|**APPLOADER**<sup>1</sup>|**INITINSTANCE**<sup>2</sup>|**미리 로드**|
|**하단**|**IOPL**|**문자**|
|**CODE**|**라이브러리**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**있지만**|**Loadoncall**<sup>1</sup>|**순수**<sup>1</sup>|
|**데이터로**|**이름**<sup>2</sup>|**READONLY**|
|**설명**|**MOVABLE**이동 가능<sup>1</sup>|**읽기**|
|**DEV386**|**MOVEABLE**이동 가능<sup>1</sup>|**REALMODE**<sup>1</sup>|
|**삭제 가능한**|**배수로**|**상주**|
|**비동적**|**이름**|**RESIDENTNAME**<sup>1</sup>|
|**실행 전용**|**Newfiles**<sup>2</sup>|**섹션이**|
|**EXECUTEONLY**|**NODATA**<sup>1</sup>|**분류**|
|**EXECUTEREAD**|**NOIOPL**<sup>1</sup>|**공유할**|
|**EXETYPE**|**NONAME**|**단**|
|**EXPORTS**|**순응**하지 않는<sup>1</sup>|**STACKSIZE**|
|**수정**됨<sup>1</sup>|**NONDISCARDABLE**|**STUB**|
|**함수**<sup>2</sup>|**NONE**|**VERSION**|
|**HEAPSIZE**|**비공유**|**WINDOWAPI**|
|**가져오도록**|**Notwindowcompat**<sup>1</sup>|**WINDOWCOMPAT**|
|**비 순수형**<sup>1</sup>|**개체가**|**WINDOWS**|
|**포함**<sup>2</sup>|**이전**<sup>1</sup>||

<sup>1</sup> 이 용어를 발견 하면 링커에서 경고 ("무시 됨")를 내보냅니다. 그러나이 단어는 계속 예약 되어 있습니다.

<sup>2</sup> 링커가이 단어를 무시 하지만 경고는 발생 하지 않습니다.

## <a name="see-also"></a>참고 항목

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
