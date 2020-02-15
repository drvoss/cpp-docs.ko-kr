---
title: ML 및 ML64 명령줄 참조
description: Microsoft MASM ML 및 ML64.EXE 어셈블러 명령줄 옵션에 대 한 참조 가이드입니다.
ms.date: 02/09/2020
f1_keywords:
- ML
helpviewer_keywords:
- /W* MASM compiler option
- /c MASM compiler option
- /EP MASM compiler option
- /Fe MASM compiler option
- /Zp MASM compiler option
- /AT MASM compiler option
- /Zm MASM compiler option
- /Sf MASM compiler option
- /Sp MASM compiler option
- /w MASM compiler option
- /Fl MASM compiler option
- /coff MASM compiler option
- /St MASM compiler option
- /Cx MASM compiler option
- /Sl MASM compiler option
- /Cu MASM compiler option
- MASM (Microsoft Macro Assembler), ML command-line reference
- /FPi MASM compiler option
- /Zf MASM compiler option
- ML environment variable
- /Fr MASM compiler option
- /help MASM compiler option
- /Sa MASM compiler option
- /Zd MASM compiler option
- /I MASM compiler option
- /? MASM compiler option
- /Bl MASM compiler option
- /Fm MASM compiler option
- /Fo MASM compiler option
- command-line reference [ML]
- /Sn MASM compiler option
- /Gd MASM compiler option
- /D* MASM compiler option
- environment variables, ML
- /Gc MASM compiler option
- /F* MASM compiler option
- /Sc MASM compiler option
- /H MASM compiler option
- /Zs MASM compiler option
- /omf MASM compiler option
- /Sg MASM compiler option
- /Cp MASM compiler option
- /Zi MASM compiler option
- /nologo MASM compiler option
- /Sx MASM compiler option
- /WX MASM compiler option
- /Ss MASM compiler option
- command line, reference [ML]
- /Ta MASM compiler option
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
ms.openlocfilehash: b5c5a79417cb141da3d5cfe1c08aa39e02a9c7c2
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257366"
---
# <a name="ml-and-ml64-command-line-reference"></a>ML 및 ML64 명령줄 참조

하나 이상의 어셈블리 언어 소스 파일을 조합 하 여 연결 합니다. 명령줄 옵션은 대/소문자를 구분 합니다.

Ml64.exe에 대 한 자세한 내용은 x [64 for x64 (ml64.exe)](masm-for-x64-ml64-exe.md)를 참조 하세요.

## <a name="syntax"></a>구문

> ML \[*옵션*] *파일 이름* \[ \[*옵션*] *파일 이름*]
>
> ML64.EXE \[*options*] *filename* \[ \[*options*] *filename*] ... \[/link *link_options*]

### <a name="parameters"></a>매개 변수

*옵션*\
다음 표에 나열 된 옵션을 설명 합니다.

|옵션|작업|
|------------|------------|
|**/AT**|메모리 모델을 약간 지원할 수 있습니다. .Com 서식 파일에 대 한 요구 사항을 위반 하는 코드 구문에 대해 오류 메시지를 사용 합니다. 이 옵션은와 동일 하지 않습니다 [. MODEL](dot-model.md) **작은** 지시문입니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Bl** *파일 이름*|대체 링커를 선택 합니다.|
|**/c**|어셈블 전용입니다. 연결 하지 않습니다.|
|**/coff**|COFF (common object file format) 형식 개체 모듈을 생성 합니다. Win32 어셈블리 언어 개발에 필요 합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Cp**|모든 사용자 식별자의 대/소문자를 유지 합니다.|
|**/Cu**|모든 식별자를 대문자 (기본값)로 매핑합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Cx**|공용 및 extern 기호에서 대/소문자를 유지 합니다.|
|**/D** *symbol*⟦ =*value*⟧|지정 된 이름을 사용 하 여 텍스트 매크로를 정의 합니다. *값* 이 없는 경우 비어 있습니다. 공백으로 구분 된 여러 토큰은 따옴표로 묶어야 합니다.|
|**/EP**|STDOUT으로 전송 되는 전처리 된 소스 목록을 생성 합니다. **/Sf**를 참조 하세요.|
|**/ERRORREPORT** [ **없음** &#124; **메시지** &#124; 큐 &#124; **송신** ]| 사용되지 않음. 오류 보고는 [WER (Windows 오류 보고)](/windows/win32/wer/windows-error-reporting) 설정에 의해 제어 됩니다. |
|**/F** *hexnum*|스택 크기를 *hexnum* 바이트 ( **/link/STACK**:*number*)로 설정 합니다. 값은 16 진수 표기법으로 표현 해야 합니다. **/F** 와 *hexnum*사이에 공백이 있어야 합니다.|
|**/Fe** *파일 이름*|실행 파일의 이름을로 합니다.|
|**/Sfl**⟦*파일 이름*⟧|어셈블된 코드 목록을 생성 합니다. **/Sf**를 참조 하세요.|
|**/Fm**⟦*filename*⟧|링커 맵 파일을 만듭니다.|
|**/Fo** *파일 이름*|개체 파일의 이름을로 합니다. 자세한 내용은 [설명](#remarks)을 참조하세요.|
|**/FPi**|부동 소수점 산술 연산에 대 한 에뮬레이터 수정 (혼합 언어 전용)을 생성 합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Fr**⟦*filename*⟧|소스 브라우저 .sbr 파일을 생성 합니다.|
|**/Fr**⟦*filename*⟧|소스 브라우저 .sbr 파일의 확장 된 형식을 생성 합니다.|
|**/Gc**|포트란 또는 파스칼 스타일 함수 호출 및 명명 규칙을 사용 하도록 지정 합니다. **옵션 언어**와 같습니다. 파스칼.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Gd**|C 스타일 함수 호출 및 명명 규칙을 사용 하도록 지정 합니다. **옵션 언어와 같습니다. C**.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/GZ**|__Stdcall 함수 호출 및 명명 규칙을 사용 하도록 지정 합니다.  옵션 언어와 동일 합니다. **STCALL**.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/H** *번호*|외부 이름을 유효 문자 수로 제한 합니다. 기본값은 31 자입니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/help**|ML에 대 한 도움말을 위한 QuickHelp를 호출 합니다.|
|**/I** *경로 이름*|포함 파일에 대 한 경로를 설정 합니다. 최대 10 개의 **/i** 옵션을 사용할 수 있습니다.|
|**/nologo**|성공적인 어셈블리에 대 한 메시지를 표시 하지 않습니다.|
|**/omf**|개체 모듈의 OMF (개체 모듈 파일 형식) 유형을 생성 합니다.  **/omf** 는 **/c**를 의미 합니다. ML은 OMF 개체 연결을 지원 하지 않습니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Sa**|사용 가능한 모든 정보 목록을 설정 합니다.|
|**/safeseh**|개체를 예외 처리기를 포함 하거나 모두로 선언 된 예외 처리기를 포함 하지 않는 것으로 표시 [합니다. SAFESEH](dot-safeseh.md).<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Sf**|목록 파일에 첫 번째 패스 목록을 추가 합니다.|
|**/Sl** *너비*|소스 목록의 줄 너비를 줄 당 문자 수로 설정 합니다. 범위는 60 ~ 255 또는 0입니다. 기본값은 0입니다. [페이지](page.md) 너비와 동일 합니다.|
|**/Sn**|목록을 생성할 때 기호 테이블을 끕니다.|
|**/Sp** *길이*|페이지 마다 줄 단위로 소스 목록의 페이지 길이를 설정 합니다. 범위는 10에서 255 또는 0입니다. 기본값은 0입니다. [페이지](page.md) 길이와 동일 합니다.|
|**/Ss** *텍스트*|소스 목록에 대 한 텍스트를 지정 합니다. [부제목](subtitle.md) 텍스트와 동일 합니다.|
|**/St** *텍스트*|원본 목록의 제목을 지정 합니다. [제목](title.md) 텍스트와 동일 합니다.|
|**/Sx**|목록에서 false 조건을 설정 합니다.|
|**/Ta** *파일 이름*|이름이 .asm 확장명으로 끝나지 않는 소스 파일을 어셈블합니다.|
|**/w**|**/W0/WX**와 동일 합니다.|
|**/W** *수준*|경고 수준을 설정 합니다. 여기서 *level* 은 0, 1, 2 또는 3입니다.|
|**/WX**|경고가 생성 되는 경우 오류 코드를 반환 합니다.|
|**/X**|포함 환경 경로를 무시 합니다.|
|**/Zd**|개체 파일에 줄 번호 정보를 생성 합니다.|
|**/Zf**|모든 기호를 공용으로 만듭니다.|
|**/Zi**|개체 파일에서 CodeView 정보를 생성 합니다.|
|**/Zm**|MASM 5.1의 최대 호환성을 위해**M510** 옵션을 사용 하도록 설정 합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Zp**⟦*alignment*⟧|지정 된 바이트 경계에서 구조체를 압축 합니다. *맞춤* 은 1, 2 또는 4 일 수 있습니다.|
|**/Zs**|구문 검사만 수행 합니다.|
|**/?**|ML 명령줄 구문에 대 한 요약 정보를 표시 합니다.|

*파일 이름*\
파일 이름입니다.

*link_options*\
링크 옵션입니다. 자세한 내용은 [링커 옵션](../../build/reference/linker-options.md)을 참조하세요.

## <a name="remarks"></a>주의

ML 및 ML64.EXE에 대 한 일부 명령줄 옵션은 배치를 구분 합니다. 예를 들어 ML 및 ML64.EXE는 몇 가지 **/c** 옵션을 허용할 수 있으므로 **/c**이전에 해당 하는 **/fo** 옵션을 지정 해야 합니다. 다음 명령줄 예제에서는 각 어셈블리 파일 사양의 개체 파일 사양에 대해 설명 합니다.

```cmd
ml.exe /Fo a1.obj /c a.asm /Fo b1.obj /c b.asm
```

## <a name="environment-variables"></a>환경 변수

|Variable|설명|
|--------------|-----------------|
|INCLUDE|포함 파일의 검색 경로를 지정 합니다.|
|ML|기본 명령줄 옵션을 지정 합니다.|
|TMP|임시 파일의 경로를 지정 합니다.|

## <a name="see-also"></a>참고 항목

[ML 오류 메시지](ml-error-messages.md)\
[Microsoft 매크로 어셈블러 참조](microsoft-macro-assembler-reference.md)
