---
title: FILE_TYPE_CODE 열거형
description: C++ 빌드 인사이트 SDK FILE_TYPE_CODE 열거형 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dea603a072d7b2f472112a75b2e9ccded78399a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325558"
---
# <a name="file_type_code-enum"></a>FILE_TYPE_CODE 열거형

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

열거형은 `FILE_TYPE_CODE` 파일의 형식을 설명합니다.

## <a name="members"></a>멤버

| 이름 | 값 | Description |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x00000000) | 이 열거형에 나열되지 않은 파일 형식입니다. |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | 개체(.obj)\*파일입니다. |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | 실행 파일(.exe)\*또는 DLL(.dll)\*파일입니다. |
| `FILE_TYPE_CODE_LIB` | 3 (0x000000003) | 정적 라이브러리(*.lib) 파일입니다. |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x000000004) | 가져오기 라이브러리(*.lib) |
| `FILE_TYPE_CODE_EXP` | 5 (0x00000005) | 내보내기(*.exp) 파일입니다. |

## <a name="remarks"></a>설명

::: moniker-end
