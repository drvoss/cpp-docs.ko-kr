---
title: 유니코드 및 MBCS
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], Unicode
- MFC [C++], character sets
- character sets [C++], multibyte
- run-time libraries [C++], language portability
- character sets [C++], Unicode
- Unicode [C++], MFC and C run-time functions
- multibyte characters [C++]
- runtime [C++], language portability
ms.assetid: 677baec6-71b4-4579-94df-64f18bc117c4
ms.openlocfilehash: e884dcfaa22bf720e9579bf2d5d866d595501887
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410527"
---
# <a name="unicode-and-mbcs"></a>유니코드 및 MBCS

MFC(Microsoft Foundation Class) 라이브러리, Visual C++의 C 런타임 라이브러리, Visual C++ 개발환경은 프로그래밍에 있어 각국 언어를 다음과 같이 지원할 수 있습니다.

- Windows에서 표준 유니코드를 지원합니다. 유니코드는 현재의 표준이며 가능한 경우 항상 사용해야 합니다.

   유니코드는 모든 언어에 대해 충분한 인코딩을 제공할 수 있도록, 16비트로 문자 인코딩이 됩니다. 모든 ASCII 문자는 유니코드에서 와이드 문자로 포함됩니다.

- 모든 플랫폼에서 더블 바이트 문자 집합(Double-byte character set, DBCS)이라고도 부르는 멀티 바이트 문자 집합(MBCS, Multibyte character set)의 한 형태를 지원합니다.

   DBCS 문자는 1 바이트 또는 2 바이트로 구성됩니다. 일부 범위의 바이트는 선행 바이트로 사용되기 때문에 따로 둡니다. 선행 바이트에 따라 선행 바이트와 뒤따르는 바이트가 하나의 2 바이트 문자를 구성합니다. 어떤 바이트가 선행 바이트인지 알고 있어야 합니다. 특정 멀티바이트 문자 집합에서 선행 바이트는 후행 바이트와 마찬가지로 특정 범위 내의 값을 가집니다. 이러한 범위가 겹치는 경우 컨텍스트를 평가하여 해당 바이트가 선행 바이트로 또는 후행 바이트로 기능하는지 여부를 판단해야 할 수 있습니다.

- 해외 시장에 응용 프로그램을 출시하기 위해 MBCS 프로그래밍을 단순화하는 도구를 지원합니다.

   Windows 운영체제에서 실행되는 MBCS 지원 버전 애플리케이션을 위해 Visual C++은 소스코드 에디터, 디버거, 명렬줄 도구를 포함한 완전한 MVCS를 지원해주는 개발환경을 제공해 줍니다. 자세한 내용은 [Visual C++에서의 MBCS 지원](../text/mbcs-support-in-visual-cpp.md)을 참조합니다.

> [!NOTE]
>  이 설명서에서 MBCS는 멀티바이트 문자를 위한 모든 유니코드를 사용하지 않는 지원을 설명하는 데 사용됩니다. Visual C++에서 MBCS는 항상 DBCS를 의미하며. 2바이트보다 큰 문자 집합은 지원하지 않습니다.

ASCII 문자 집합은 모든 멀티바이트 문자 집합의 부분 집합으로 정의됩니다. 많은 멀티바이트 문자 집합에서 0x00 - 0x7F 범위의 각 문자는 ASCII 문자 집합 내의 동일한 값을 가진 문자와 같습니다. 예를 들어, ASCII 및 MBCS 문자열 모두에서 1바이트 NULL 문자('\0')는 0x00 값을 가지며 종료 null 문자를 가리킵니다.

## <a name="see-also"></a>참고자료

[텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)<br/>
[국가별 사용](../text/international-enabling.md)
