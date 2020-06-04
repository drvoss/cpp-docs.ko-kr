---
title: /SOURCELINK(PDB에 Sourcelink 파일 포함)
description: Microsoft C++의 /SOURCELINK 링커 옵션에 대한 참조 가이드입니다.
ms.date: 03/31/2020
f1_keywords:
- /sourcelink
helpviewer_keywords:
- /SOURCELINK linker option
- /SOURCELINK
ms.openlocfilehash: bde55c401e17f7b3c84ffcdad29dda2badcc260b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336062"
---
# <a name="sourcelink-include-source-link-file-in-pdb"></a>/SOURCELINK(PDB에 소스 링크 파일 포함)

링커에서 생성된 PDB 파일에 포함하도록 소스 링크 구성 파일을 지정합니다.

## <a name="syntax"></a>구문

> **`/SOURCELINK:`**_`filename`_

## <a name="arguments"></a>인수

*파일*<br/>
디버거에 표시할 소스 파일에 대한 URL에 로컬 파일 경로의 간단한 매핑이 포함된 JSON 형식의 구성 파일을 지정합니다. 이 파일의 형식에 대한 자세한 내용은 [소스 링크 JSON 스키마](https://github.com/dotnet/designs/blob/master/accepted/2020/diagnostics/source-link.md#source-link-json-schema)를 참조하십시오.

## <a name="remarks"></a>설명

소스 링크는 바이너리에 대한 소스 디버깅을 제공하기 위한 언어 및 소스 제어 불가지론 시스템입니다. 소스 링크는 Visual Studio 2017 버전 15.8에서 시작하는 기본 C++ 바이너리에 대해 지원됩니다. 소스 링크에 대한 개요는 [소스 링크를](https://github.com/dotnet/designs/blob/master/accepted/2020/diagnostics/source-link.md)참조하십시오. 프로젝트에서 소스 링크를 사용하는 방법과 프로젝트의 일부로 SourceLink 파일을 생성하는 방법에 대한 자세한 내용은 [소스 링크 사용을](https://github.com/dotnet/sourcelink#using-source-link-in-c-projects)참조하십시오.

### <a name="to-set-the-sourcelink-linker-option-in-visual-studio"></a>비주얼 스튜디오에서 /SOURCELINK 링커 옵션을 설정하려면

1. 프로젝트에 대한 **속성 페이지** 대화 상자를 엽니다. 자세한 정보는 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. 구성 **속성** > **링커** > 명령줄 속성 페이지를**선택합니다.**

1. 추가 **옵션** **`/SOURCELINK:`** _`filename`_ 상자에서 확인 **또는** **적용을** 추가하여 변경 내용을 저장합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- 이 옵션에는 프로그래밍 방식과 동등한 것이 없습니다.

## <a name="see-also"></a>참고 항목

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
