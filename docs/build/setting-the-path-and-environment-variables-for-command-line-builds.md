---
title: 명령줄 빌드에 맞는 경로 및 환경 변수 설정
ms.custom: conceptual
ms.date: 07/24/2019
helpviewer_keywords:
- environment variables [C++]
- VCVARS32.bat file
- cl.exe compiler [C++], environment variables
- LINK tool [C++], environment variables
- PATH reserved word
- INCLUDE reserved word
- LINK tool [C++], path
- LIB environment variable
- compiling source code [C++], from command line
- environment variables [C++], CL compiler
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
ms.openlocfilehash: aeafe806e5d29b89c243586974814aa7cfc16d1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335581"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>명령줄 빌드에 맞는 경로 및 환경 변수 설정

MSVC(Microsoft C++) 명령줄 빌드 도구에는 설치 및 빌드 구성에 맞게 사용자 지정된 여러 환경 변수가 필요합니다. Visual Studio 설치 관리자에서 C++ 워크로드를 설치하면 필요한 환경 변수를 설정하는 사용자 지정된 명령 파일 또는 일괄 처리 파일을 만듭니다. 그런 다음 설치 관리자는 이러한 명령 파일을 사용하여 Windows 시작 메뉴에 대한 바로 가기를 만들어 개발자 명령 프롬프트 창을 엽니다. 이러한 바로 가기는 특정 빌드 구성에 대한 환경 변수를 설정합니다. 명령줄 도구를 사용하려는 경우 이러한 바로 가기 중 하나를 실행하거나 일반 명령 프롬프트 창을 연 다음 사용자 지정 명령 파일 중 하나를 실행하여 빌드 구성 환경을 직접 설정할 수 있습니다. 자세한 내용은 [명령줄에서 MSVC 도구 집합 사용을](building-on-the-command-line.md)참조하십시오. 일반 명령 프롬프트가 있는 명령 파일을 사용하려면 [개발자 명령 파일 위치라는](building-on-the-command-line.md#developer_command_file_locations)섹션을 참조하십시오.

MSVC 명령줄 도구는 PATH, TMP, INCLUDE, LIB 및 LIBPATH 환경 변수를 사용하고 설치된 도구, 플랫폼 및 SDK와 관련된 다른 환경 변수도 사용합니다. 간단한 Visual Studio 설치도 20개 이상의 환경 변수를 설정할 수 있습니다. 이러한 환경 변수의 값은 설치 및 빌드 구성 선택에 따라 다르며 제품 업데이트 또는 업그레이드에 따라 변경할 수 있으므로 Windows 환경에서 직접 설정하는 대신 개발자 명령 프롬프트 바로 가기 또는 사용자 지정된 명령 파일 중 하나를 사용하여 설정하는 것이 좋습니다.

개발자 명령 프롬프트 바로 가기에서 설정한 환경 변수를 보려면 SET 명령을 사용할 수 있습니다. 일반 명령 프롬프트 창을 열고 기준선에 대한 SET 명령의 출력을 캡처합니다. 개발자 명령 프롬프트 창을 열고 비교를 위해 SET 명령의 출력을 캡처합니다. Visual Studio IDE에 내장된 것과 같은 diff 도구는 환경 변수를 비교하고 개발자 명령 프롬프트에 의해 설정된 내용을 확인하는 데 유용할 수 있습니다. 컴파일러 및 링커에서 사용하는 특정 환경 변수에 대한 자세한 내용은 [CL 환경 변수를](reference/cl-environment-variables.md)참조하십시오.

> [!NOTE]
> 몇 가지 명령줄 도구 또는 도구 옵션에는 관리자 권한이 필요할 수 있습니다. 사용 시 사용 권한 문제가 있는 경우 **관리자로 실행** 옵션을 사용하여 개발자 명령 프롬프트 창을 여는 것이 좋습니다. Windows 10에서 마우스 오른쪽 단추를 클릭하여 명령 프롬프트 창의 **Run as administrator**바로 가기 메뉴를 연 다음 **[관리자로 실행 하기]**

## <a name="see-also"></a>참고 항목

[명령줄에서 MSVC 도구 집합 사용](building-on-the-command-line.md)<br/>
[MSVC 링커 참조](reference/linking.md)<br/>
[MSVC 링커 옵션](reference/linker-options.md)<br/>
[MSVC 컴파일러 참조](reference/compiling-a-c-cpp-program.md)<br/>
[MSVC 컴파일러 옵션](reference/compiler-options.md)
