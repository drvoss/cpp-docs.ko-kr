---
title: 문서 주석에 권장태그(C++ 문서 주석)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 1648d0eb019a3aad25641d7f6a7edd1ba26acf7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336168"
---
# <a name="recommended-tags-for-documentation-comments"></a>문서 주석에 대한 권장 태그

MSVC 컴파일러는 코드에서 문서 주석을 처리하고 각 컴파일랜드에 대해 .xdc 파일을 만들고 xdcmake.exe는 .xml 파일로 .xdc 파일을 처리합니다. 문서를 만들기 위해 .xml 파일을 처리하는 것은 사이트에서 구현해야 하는 세부 사항입니다.

태그는 형식, 형식 멤버와 같은 구문에서 처리됩니다.

태그는 형식 또는 멤버 바로 앞에 와야 합니다.

> [!NOTE]
> 문서 주석은 속성 및 이벤트에 대한 네임스페이스 또는 라인 외부 정의에 적용할 수 없습니다. 문서 주석은 클래스 내 선언에 있어야 합니다.

컴파일러는 유효한 XML인 태그를 모두 처리합니다. 다음 태그는 사용자 문서에서 일반적으로 사용되는 기능을 제공합니다.

||||
|-|-|-|
|[\<c>](c-visual-cpp.md)|[\<코드>](code-visual-cpp.md)|[\<예제>](example-visual-cpp.md)|
|예외>1 [ \< ](exception-visual-cpp.md)|>1 포함 [ \< ](include-visual-cpp.md)|[\<목록>](list-visual-cpp.md)|
|[\<파라>](para-visual-cpp.md)|파라임>1 [ \< ](param-visual-cpp.md)|파라임프>1 [ \< ](paramref-visual-cpp.md)|
|권한>1 [ \< ](permission-visual-cpp.md)|[\<발언>](remarks-visual-cpp.md)|[\<>반환](returns-visual-cpp.md)|
|>1 참조 [ \< ](see-visual-cpp.md)|[ \<참조>](seealso-visual-cpp.md)1|[\<요약>](summary-visual-cpp.md)|
|[\<값>](value-visual-cpp.md)|||

1. 컴파일러가 구문을 확인합니다.

현재 릴리스에서 MSVC 컴파일러는 다른 `<paramref>`Visual Studio 컴파일러에서 지원하는 태그를 지원하지 않습니다. Visual C++는 이후 릴리스에서 `<paramref>`를 지원할 수 있습니다.

## <a name="see-also"></a>참고 항목

[XML 문서](xml-documentation-visual-cpp.md)
