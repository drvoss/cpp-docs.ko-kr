---
title: C /C++ 참조-Visual Studio 빌드
description: C에 대 한 참조 콘텐츠 /C++ 프로젝트 시스템 및 Visual Studio의 도구를 작성 합니다.
ms.date: 05/06/2019
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
ms.openlocfilehash: abe946ce516e915cd597a0f863c5949fed212bfa
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221448"
---
# <a name="cc-building-reference"></a>C/C++ 빌드 참조

Visual Studio에서는 C를 구축 하는 두 가지 /C++ 프로그램입니다. (가장 쉽고 일반적인) 하는 방법은 [Visual Studio IDE 내에서 빌드](../creating-and-managing-visual-cpp-projects.md)합니다. 다른 방법은 [명령줄 도구를 사용 하 여 명령 프롬프트에서 빌드](../building-on-the-command-line.md)합니다. 두 경우 모두 만들 하 고 선택한 타사 편집기나 Visual Studio를 사용 하 여 원본 파일을 편집할 수 있습니다.

## <a name="in-this-section"></a>섹션 내용

[C++ 프로젝트용 MSBuild 참조](msbuild-visual-cpp-overview.md)

[MSVC 컴파일러 참조](compiling-a-c-cpp-program.md)<br/>
기계어 코드로, 링커 지시문, 섹션, 외부 참조 이름과 함수/데이터를 포함 하는 개체 파일을 만드는 MSVC 컴파일러를 설명 합니다.

[MSVC 링커 참조](linking.md)<br/>
정적으로 연결 된 라이브러리 및 컴파일러에 의해 생성 된 개체 파일에서 코드를 결합 하는 링커 설명 이름 참조를 확인 하 고 실행 파일을 만듭니다.

[컴파일러 및 링커에서의 유니코드 지원](unicode-support-in-the-compiler-and-linker.md)

[추가 MSVC 빌드 도구](c-cpp-build-tools.md)<br/>
추가 명령줄 도구에 대 한 C++입니다.

[C++ 빌드 오류](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)<br/>
콘텐츠의 테이블의 빌드 오류 섹션을 소개합니다.

## <a name="related-sections"></a>관련 단원

[ 전처리기 참조](../../preprocessor/c-cpp-preprocessor-reference.md)<br/>
매크로, 연산자 및 지시문을 변환 하 여 컴파일러에 대 한 소스 파일을 준비 하는 전처리기에 설명 합니다.

[사용자 지정 빌드 단계 및 빌드 이벤트 이해](../understanding-custom-build-steps-and-build-events.md)<br/>
빌드 프로세스를 사용자 지정에 대해 설명 합니다.

[C/C++ 프로그램 빌드](../projects-and-build-systems-cpp.md)<br/>
명령줄 또는 Visual Studio의 통합 개발 환경에서 프로그램 빌드를 설명하는 항목에 대한 링크를 제공합니다.

[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
개발 환경에서 또는 명령줄에서 컴파일러 옵션을 설정에 설명합니다.

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
컴파일러 옵션을 사용 하 여 설명 하는 항목에 대 한 링크를 제공 합니다.

[MSVC 링커 참조](linking.md)<br/>
통합된 개발 환경 외부 또는 내부 링커 옵션을 설정에 설명합니다.

[MSVC 링커 옵션](linker-options.md)<br/>
링커 옵션을 사용 하 여 설명 하는 항목에 대 한 링크를 제공 합니다.

[BSCMAKE 참조](bscmake-reference.md)<br/>
Microsoft 찾아보기 Information Maintenance Utility를 (BSCMAKE에 설명합니다. EXE)에 찾아보기 정보 파일 (.bsc)에서 빌드합니다.sbr 파일 컴파일 중에 생성 합니다.

[LIB 참조](lib-reference.md)<br/>
만들고 개체 파일 형식 COFF (공용) 개체 파일의 라이브러리를 관리 하는 Microsoft 라이브러리 관리자 (LIB.exe)에 대해 설명 합니다.

[EDITBIN 참조](editbin-reference.md)<br/>
Microsoft COFF Binary 파일 편집기 (EDITBIN 합니다. 개체 파일 형식 COFF (공용) 이진 파일을 수정 하는 EXE).

[DUMPBIN 참조](dumpbin-reference.md)<br/>
Microsoft COFF Binary File Dumper를 (DUMPBIN에 설명합니다. Exe)에 개체 파일 형식 COFF (공용) 이진 파일에 대 한 정보입니다.

[NMAKE 참조](nmake-reference.md)<br/>
Microsoft Program Maintenance Utility를 (NMAKE에 설명합니다. 프로젝트를 빌드하는 도구는 EXE)을 설명 파일에 포함 된 명령을 기반으로 합니다.
