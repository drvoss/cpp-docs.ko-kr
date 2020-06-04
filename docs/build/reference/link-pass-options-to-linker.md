---
title: /link(옵션을 링커로 전달)
ms.date: 03/25/2019
f1_keywords:
- /link
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
ms.openlocfilehash: 37743e855c933b6236b5e7a837db257f332a3037
ms.sourcegitcommit: bbaf65f8ed1af12828b38f8eacd24f934ac0e538
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2019
ms.locfileid: "67155776"
---
# <a name="link-pass-options-to-linker"></a>/link(옵션을 링커로 전달)

하나 이상의 링커 옵션을 링커에 전달 합니다.

## <a name="syntax"></a>구문

> **/link** *linker-options*

## <a name="arguments"></a>인수

*linker-options*<br/>
링커 옵션 또는 링커로 전달될 옵션입니다.

## <a name="remarks"></a>설명

**/link** 옵션과 및 링커 옵션은 반드시 어떤 파일 이름과 CL 옵션 뒤에 있어야 합니다. **/link**와 `linker-options` 사이에는 공백이 있어야 합니다. 자세한 내용은 [MSVC 링커 참조](linking.md)를 살펴봅니다.


## <a name="example"></a>예제

다음 샘플은 명령줄에서 *hello.cpp*를 컴파일하고 기존 개체 파일 *there.obj*에 링크합니다. 그런 다음 추가 **/VERSION** 명령을 링커에 전달합니다.

`cl /W4 /EHsc hello.cpp there.obj /link /VERSION:3.14`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

IDE에는 일반적으로 컴파일 및 코드를 연결 하려면 별도 명령을 보냅니다. 프로젝트 속성 페이지에 링커 옵션을 설정할 수 있습니다.

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **링커** 폴더를 선택합니다.

1. 하나 이상의 속성을 수정 합니다. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- 이 컴파일러 옵션을 프로그래밍 방식으로 변경할 수 없습니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
