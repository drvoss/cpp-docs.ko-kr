---
title: 유니코드 및 멀티바이트 문자 집합(MBCS)
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
ms.openlocfilehash: 063c8b39ee0d29403b382b57a236f2a3e8759e3f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375751"
---
# <a name="unicode-and-mbcs"></a>유니코드 및 멀티바이트 문자 집합(MBCS)

Microsoft 파운데이션 클래스(MFC) 라이브러리, Visual C++에 대한 C 런타임 라이브러리 및 Visual C++ 개발 환경은 국제 프로그래밍을 지원할 수 있도록 활성화되어 있습니다. DSVM에서 제공하는 기능은 다음과 같습니다.

- Windows의 유니코드 표준 지원. 유니코드는 현재의 표준이며 어디에서든 항상 사용 가능해야 합니다.

   유니코드는 모든 언어에 충분한 인코딩을 제공하는 16비트 문자 인코딩입니다. 모든 ASCII 문자는 유니코드에 확대된 문자로 포함됩니다.

- 모든 플랫폼에서 이중 바이트 문자 집합(DBCS)이라고 하는 복중문자 집합(MBCS)의 형태를 지원합니다.

   DBCS 문자는 1바이트 또는 2바이트로 구성됩니다. 일부 바이트 범위는 납 바이트로 사용하기 위해 따로 설정됩니다. 잠재 고객 바이트는 해당 바이트와 다음 추적 바이트가 단일 2바이트 너비 문자를 구성되도록 지정합니다. 어떤 바이트가 리드 바이트인지 추적해야 합니다. 특정 멀티바이트 문자 집합에서 선행 바이트는 후행 바이트와 마찬가지로 특정 범위 내에 속합니다. 이러한 범위가 겹치는 경우 컨텍스트를 평가하여 지정된 바이트가 리드 바이트 또는 추적 바이트로 작동하는지 확인해야 할 수 있습니다.

- 국제 시장을 위해 작성된 애플리케이션의 MBCS 프로그래밍을 간소화하는 도구 지원

   MBCS 지원 Windows 운영 체제 버전에서 실행되는 경우 통합 소스 코드 편집기, 디버거 및 명령줄 도구를 포함한 Visual C++ 개발 시스템이 완전히 MBCS지원됩니다. 자세한 내용은 [시각적 C++에서 MBCS 지원을](../text/mbcs-support-in-visual-cpp.md)참조하십시오.

> [!NOTE]
> 이 설명서에서 MBCS는 다중 바이트 문자에 대한 유니코드가 아닌 모든 지원을 설명하는 데 사용됩니다. 시각적 C++에서 MBCS는 항상 DBCS를 의미합니다. 2바이트보다 넓은 문자 집합은 지원되지 않습니다.

정의에 따르면 ASCII 문자 집합은 모든 멀티바이트 문자 집합의 하위 집합입니다. 많은 멀티바이트 문자 집합에서 0x00 - 0x7F 범위의 각 문자는 ASCII 문자 집합에 동일한 값을 가진 문자와 같습니다. 예를 들어 ASCII 및 MBCS 문자 문자열 모두에서 1바이트 NULL 문자('\0')는 값 0x00을 가지며 null 문자 종료를 나타냅니다.

## <a name="see-also"></a>참고 항목

[텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)<br/>
[국제 사용](../text/international-enabling.md)
