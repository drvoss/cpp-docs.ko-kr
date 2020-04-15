---
title: XDCMake 참조
ms.date: 11/04/2016
f1_keywords:
- xdcmake
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
ms.openlocfilehash: 9970470d1feb471f9e0b8c9284a08337dac7ef0f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335853"
---
# <a name="xdcmake-reference"></a>XDCMake 참조

xdcmake.exe는 .xdc 파일을 .xml 파일로 컴파일하는 프로그램입니다. .xdc 파일은 소스 코드가 [/doc으로](doc-process-documentation-comments-c-cpp.md) 컴파일되고 소스 코드 파일에 XML 태그로 표시된 문서 주석이 포함되어 있을 때 각 소스 코드 파일에 대한 MSVC 컴파일러에서 만들어집니다.

### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 xdcmake.exe를 사용하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **구성 속성** 폴더를 엽니다.

1. **XML 문서 주석** 속성 페이지를 클릭합니다.

> [!NOTE]
> 명령줄의 xdcmake.exe 옵션은 xdcmake.exe가 개발 환경(속성 페이지)에서 사용되는 경우의 옵션과 다릅니다. 개발 환경에서 xdcmake.exe를 사용하는 방법은 [XML 문서 생성기 도구 속성 페이지](xml-document-generator-tool-property-pages.md)를 참조하세요.

## <a name="syntax"></a>구문

xdcmake `input_filename options`

## <a name="parameters"></a>매개 변수

*input_filename*<br/>
xdcmake.exe에 대한 입력으로 사용되는 .xdc 파일의 파일 이름입니다. 하나 이상의 .xdc 파일을 지정하거나 *.xdc를 사용하여 현재 디렉터리에서 모든 .xdc 파일을 사용합니다.

*옵션*<br/>
다음 중 0개 이상:

|옵션|Description|
|------------|-----------------|
|/?, /help|xdcmake.exe에 대한 도움말을 표시합니다.|
|/assembly:*filename*|.xml 파일에서 \<어셈블리> 태그의 값을 지정할 수 있습니다.  기본적으로 \<어셈블리> 태그의 값은 .xml 파일의 파일 이름과 동일합니다.|
|/nologo|저작권 메시지를 표시하지 않습니다.|
|/out:*filename*|.xml 파일의 이름을 지정할 수 있습니다.  기본적으로 .xml 파일의 이름은 xdcmake.exe에서 처리하는 첫 번째 .xdc 파일의 파일 이름입니다.|

## <a name="remarks"></a>설명

Visual Studio는 프로젝트를 빌드할 때 xdcmake.exe를 자동으로 호출합니다. 명령줄에서 xdcmake.exe를 호출할 수도 있습니다.

문서 주석을 소스 코드 파일에 추가하는 방법에 대한 자세한 내용은 [문서 주석에 권장되는 태그](recommended-tags-for-documentation-comments-visual-cpp.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

[XML 문서](xml-documentation-visual-cpp.md)
