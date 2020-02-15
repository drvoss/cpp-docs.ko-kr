---
title: ARM 어셈블러 명령줄 참조
description: Microsoft ARM 어셈블러 명령줄 옵션에 대 한 참조 가이드입니다.
ms.date: 02/09/2020
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
ms.openlocfilehash: a63273e8d21e7a28574ec79d62c15f29ee59cd50
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257381"
---
# <a name="arm-assembler-command-line-reference"></a>ARM 어셈블러 명령줄 참조

이 문서에서는 Microsoft ARM 어셈블러, **armasm**에 대 한 명령줄 정보를 제공 합니다. **armasm** 는 COFF (Common Object File Format)의 Microsoft 구현에 ARMv7 Thumb assembly 언어를 어셈블합니다. 링커는 ARM 어셈블러와 C 컴파일러 모두에서 생성 된 COFF 코드 개체를 연결할 수 있습니다. 이 클래스는 라이브러리 관리자가 만든 개체 라이브러리와 함께 연결할 수 있습니다.

## <a name="syntax"></a>구문

> **`armasm`** [*options*] *source_file* *object_file*\
> **`armasm`** [*options*] **`-o`** *object_file* *source_file*

### <a name="parameters"></a>매개 변수

*옵션*\
다음 옵션 중 0 개 이상의 조합입니다.

- **`-errors`** *파일 이름*\
   오류 및 경고 메시지를 *파일 이름*으로 리디렉션합니다.

- **`-i`** *dir*[ **`;`** <em>dir</em>] \
   포함 검색 경로에 지정 된 디렉터리를 추가 합니다.

- **`-predefine`** *지시문*\
   기호를 미리 정의할 수 있도록 필요로, SETL 또는 SETS 지시문을 지정 합니다.
   예: `armasm.exe -predefine "COUNT SETA 150" source.asm`\
   자세한 내용은 [ARM 컴파일러 Armasm 참조 가이드](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)를 참조 하세요.

- **`-nowarn`**\
   모든 경고 메시지를 사용 하지 않도록 설정 합니다.

- **`-ignore`** *경고*\
   지정 된 경고를 사용 하지 않도록 설정 합니다. 가능한 값은 경고에 대 한 섹션을 참조 하세요.

- **`-help`**\
   명령줄 도움말 메시지를 인쇄 합니다.

- **`-machine`** *machine*\
   PE 헤더에 설정할 컴퓨터 유형을 지정 합니다.  *컴퓨터* 에 사용할 수 있는 값은 \입니다.
   **ARM**-컴퓨터 유형을 IMAGE_FILE_MACHINE_ARMNT로 설정 합니다. 이 옵션은 기본값입니다. \
   **THUMB**-컴퓨터 유형을 IMAGE_FILE_MACHINE_THUMB로 설정 합니다.

- **`-oldit`**\
   ARMv7 스타일 IT 블록을 생성 합니다.  기본적으로 ARMv8 호환 IT 블록이 생성 됩니다.

- **`-via`** *파일 이름*\
   *파일 이름*에서 추가 명령줄 인수를 읽습니다.

- **`-16`**\
   소스를 16 비트 엄지 명령으로 어셈블합니다.  이 옵션은 기본값입니다.

- **`-32`**\
   소스를 32 비트 ARM 명령으로 어셈블합니다.

- **`-g`**\
   디버깅 정보를 생성 합니다.

- **`-errorReport:`** *옵션*\
   이 옵션은 사용되지 않습니다. Windows Vista부터 오류 보고는 [WER (Windows 오류 보고)](/windows/win32/wer/windows-error-reporting) 설정에 의해 제어 됩니다.

*source_file*\
소스 파일 이름입니다.

*object_file*\
개체 (출력) 파일의 이름입니다.

## <a name="remarks"></a>주의

다음 예제에서는 일반적인 시나리오에서 armasm를 사용 하는 방법을 보여 줍니다. 먼저 armasm를 사용 하 여 개체 (.obj) 파일에 어셈블리 언어 소스 (.asm) 파일을 빌드합니다. 그런 다음, CL 명령줄 C 컴파일러를 사용 하 여 소스 파일 (.c)을 컴파일하고 링커 옵션을 지정 하 여 ARM 개체 파일을 연결 합니다.

```cmd
armasm myasmcode.asm -o myasmcode.obj
cl myccode.c /link myasmcode.obj
```

## <a name="see-also"></a>참고 항목

[ARM 어셈블러 진단 메시지](../../assembler/arm/arm-assembler-diagnostic-messages.md)\
[ARM 어셈블러 지시문](../../assembler/arm/arm-assembler-directives.md)
