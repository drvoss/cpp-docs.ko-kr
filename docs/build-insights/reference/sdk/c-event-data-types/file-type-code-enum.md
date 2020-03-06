---
title: FILE_TYPE_CODE 열거형
description: C++ BUILD Insights SDK FILE_TYPE_CODE 열거형 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e64f9315c62ce40c436032d6c96fdfa725847a7f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335167"
---
# <a name="file_type_code-enum"></a>FILE_TYPE_CODE 열거형

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`FILE_TYPE_CODE` 열거형은 파일의 형식을 설명 합니다.

## <a name="members"></a>멤버

| 이름 | 값 | 설명 |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x00000000) | 이 열거형에 나열 되지 않은 파일 형식입니다. |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | 개체 (\*.obj) 파일입니다. |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | 실행 파일 (\*.exe) 또는 DLL (\*.dll) 파일입니다. |
| `FILE_TYPE_CODE_LIB` | 3 (0x00000003) | 정적 라이브러리 (* .lib) 파일입니다. |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x00000004) | 가져오기 라이브러리 (* .lib) |
| `FILE_TYPE_CODE_EXP` | 5 (0x00000005) | 내보내기 (* .exp) 파일입니다. |

## <a name="remarks"></a>주의

::: moniker-end
