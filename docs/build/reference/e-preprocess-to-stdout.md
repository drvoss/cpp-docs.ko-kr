---
title: /E(stdout으로 전처리)
ms.date: 11/04/2016
f1_keywords:
- /e
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
ms.openlocfilehash: 710be7e1dfc4de89bc1eed3e23e4803c561da10c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273263"
---
# <a name="e-preprocess-to-stdout"></a>/E(stdout으로 전처리)

C 및 C++ 소스 파일을 전처리 하 고 표준 출력 장치에 전처리 된 파일을 복사 합니다.

## <a name="syntax"></a>구문

```
/E
```

## <a name="remarks"></a>설명

이 프로세스에서는 모든 전처리기 지시문이 실행 되 하 고 매크로 확장을 수행 하는 주석이 제거 됩니다. 전처리 된 출력에서 메모를 유지 하려면 사용 합니다 [/C (유지 전처리 중에 주석)](c-preserve-comments-during-preprocessing.md) 컴파일러 옵션을 함께 합니다.

**/E** 추가 `#line` 지시문 및 조건부 컴파일 용 전처리기 지시문에 의해 제거 된 줄 및 포함된 된 파일의 끝 부분에서 출력 합니다. 이러한 지시어는 전처리 된 파일의 줄 번호 다시 매기기입니다. 결과적으로, 오류 처리의 이후 단계 중에 생성 된 전처리 된 파일의 줄이 아니라 원래 소스 파일의 줄 번호를 참조 하십시오.

합니다 **/E** 옵션은 컴파일을 억제 합니다. 컴파일에 대 한 전처리 된 파일을 다시 제출 해야 합니다. **/E** 출력 파일을 표시 하지 합니다 **/FA**를 **/Fa**, 및 **/Fm** 옵션입니다. 자세한 내용은 [/FA, /Fa (목록 파일)](fa-fa-listing-file.md) 하 고 [/Fm (맵 파일 이름)](fm-name-mapfile.md)합니다.

표시 하지 않으려면 `#line` 지시문을 사용 합니다 [/EP (#line 지시문 없이 stdout로 전처리)](ep-preprocess-to-stdout-without-hash-line-directives.md) 옵션을 사용 합니다.

대신 파일로 전처리 된 출력을 보내도록 `stdout`를 사용 합니다 [/P (파일로 전처리)](p-preprocess-to-a-file.md) 옵션을 사용 합니다.

표시 하지 않으려면 `#line` 지시문과 송신 전처리 된 출력 파일을 사용 하 여 **/P** 하 고 **/EP** 함께 합니다.

미리 컴파일된 헤더를 사용할 수 없습니다는 **/E** 옵션입니다.

별도 파일을 전처리 하는 경우 공백은 제외 됩니다 토큰 후 note 합니다. 잘못 된 프로그램에서 발생할 수 있는이 의도 하지 않은 부작용입니다. 다음 프로그램을 성공적으로 컴파일됩니다.

```
#define m(x) x
m(int)main( )
{
   return 0;
}
```

그러나로 컴파일하는 경우:

```
cl -E test.cpp > test2.cpp
```

`int main` test2.cpp에서 제대로 되지 `intmain`합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [컴파일러 설정 및 빌드 속성](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. 컴파일러 옵션을 입력 합니다 **추가 옵션**상자입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>을 참조하세요.

## <a name="example"></a>예제

다음 명령줄을 실행 하면 `ADD.C`주석을 유지, 추가 `#line` 지시문을 표준 출력 장치에서 결과 표시 합니다.

```
CL /E /C ADD.C
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
