---
title: '&lt;예외 > (C++ 문서 주석)'
ms.date: 11/04/2016
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
ms.openlocfilehash: d56e0ce7c892cfd9fd909b5268043d77929bd43c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439868"
---
# <a name="ltexceptiongt"></a>&lt;exception&gt;

\<exception> 태그를 사용하면 throw할 수 있는 예외를 지정할 수 있습니다. 이 태그는 메서드 정의에 적용됩니다.

## <a name="syntax"></a>구문

```
<exception cref="member">description</exception>
```

#### <a name="parameters"></a>매개 변수

*member*<br/>
현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조입니다. 컴파일러는 이름 조회 규칙을 사용하여 지정된 예외가 있는지 확인하고 `member`를 출력 XML의 표준 요소 이름으로 변환합니다.  `member`가 검색되지 않는 경우 컴파일러에서 경고가 발생합니다.

이름을 단일 또는 이중 따옴표로 묶습니다.

제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see>](see-visual-cpp.md)를 참조하세요.

*description*<br/>
설명

## <a name="remarks"></a>설명

[/doc](doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

MSVC 컴파일러는 문서 주석을 통해 한 번의 cref 참조를 확인 하려고 시도 합니다.  따라서 C++ 조회 규칙을 사용하는 경우 컴파일러에서 기호를 찾을 수 없으며 참조는 확인되지 않음으로 표시됩니다. 자세한 내용은 [\<seealso>](seealso-visual-cpp.md)를 참조하세요.

## <a name="example"></a>예제

```cpp
// xml_exception_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_exception_tag.dll
using namespace System;

/// Text for class EClass.
public ref class EClass : public Exception {
   // class definition ...
};

/// <exception cref="System.Exception">Thrown when... .</exception>
public ref class TestClass {
   void Test() {
      try {
      }
      catch(EClass^) {
      }
   }
};
```

## <a name="see-also"></a>참고 항목

[XML 문서](xml-documentation-visual-cpp.md)
