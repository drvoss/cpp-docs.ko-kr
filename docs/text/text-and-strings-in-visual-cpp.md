---
title: Visual C++의 텍스트 및 문자열
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- programming [C++], international
- multiple language support [C++]
- Unicode [C++]
- international applications [C++], about international applications
- portability [C++]
- translation [C++], character sets
- non-European characters [C++]
- character sets [C++]
- globalization [C++]
- Japanese characters [C++]
- Kanji character support [C++]
- local character sets [C++]
- ASCII characters [C++]
- character sets [C++], about character sets
- localization [C++], character sets
- translating code [C++]
- localization [C++]
- character sets [C++], non-European
- portability [C++], character sets
- MBCS [C++], international programming
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
ms.openlocfilehash: 80b7139996fddc82b206828d4a036922fa1446d5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167604"
---
# <a name="text-and-strings-in-visual-c"></a>Visual C++의 텍스트 및 문자열

세계 시장에 애플리케이션을 출시하기 위한 중요한 부분중 하나는 로컬 문자 집합을 올바르게 표현하는 것입니다. ASCII 문자 집합은 0x00에서 0x7F 범위 값으로 정의됩니다. 주로 유럽 ASCII 문자 집합과 동일하게 0x00-0x7F 범위의 문자를 정의하고 0x80에서 0xFF까지의 확장 문자 집합을 정의하는 별도의 문자 집합이 있습니다. 이에 따라 8비트 단일인 싱글 바이트 문자 집합(SBCS, Single-byte-character set)은 많은 유럽 언어의 문자 집합뿐만 아니라 ASCII 문자 집합을 표현하기에 충분합니다. 그러나 한국어와 같은 일부 비유럽 문자 집합 유형의 문자는 싱글 바이트 문자 집합 이상이 필요하여 멀티 바이트 문자 집합(MBCS, Multibyte-character set)이 필요합니다.

## <a name="in-this-section"></a>섹션 내용

[유니코드 및 멀티바이트 문자 집합(MBCS)](../text/unicode-and-mbcs.md)<br/>
Visual C++이 지원하는 유니코드 및 MBCS 프로그래밍 관련 내용을 설명합니다.

[유니코드 지원](../text/support-for-unicode.md)<br/>
단일 바이트로 표현할 수 없는 문자 집합을 포함한 모든 문자 집합을 지원하는 사양인 유니코드에 대해 설명합니다.

[MBCS (멀티 바이트 문자 집합) 지원](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
유니코드에 대한 대안으로, 단일 바이트로 표현할 수 없는 일본어, 중국어 등과 같은 문자 집합을 지원하는 멀티 바이트 문자 집합(MBCS)에 대해 설명합니다.

[tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)<br/>
다양한 데이터 형식, 루틴 및 기타 개체에 대해 Microsoft가 제공하는 일반 텍스트 매핑을 설명합니다.

[방법: 다양한 문자열 형식 간 변환](../text/how-to-convert-between-various-string-types.md)<br/>
Visual C++에서 다양한 문자열 형식을 다른 문자열로 변환하는 방법에 대해 설명합니다.

## <a name="related-sections"></a>관련 섹션

[국제화](../c-runtime-library/internationalization.md)<br/>
C 런타임 라이브러리의 국가별 지원에 대해 설명 합니다.

[국가별 샘플](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/International)<br/>
Visual C++에서 국제화에 대한 예제의 링크를 제공합니다.

[언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
C 런타임 라이브러리의 언어 및 국가/지역 문자열을 제공 합니다.
