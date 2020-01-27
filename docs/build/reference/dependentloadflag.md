---
title: /DEPENDENTLOADFLAG(기본 종속 로드 플래그 설정)
description: /DEPENDENTLOADFLAG 옵션은이 모듈에서 로드 하는 Dll에 대 한 기본 종속 로드 플래그를 설정 합니다.
ms.date: 01/22/2020
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 5e31a0d747e7186814cba3ae1c4cf243569d87a8
ms.sourcegitcommit: b67b08472b6f1ee8f1c5684bba7056d3e0fc745f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76725710"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG(기본 종속 로드 플래그 설정)

::: moniker range="vs-2015"

**/DEPENDENTLOADFLAG** 옵션을 사용 하려면 Visual Studio 2017 이상이 필요 합니다.

::: moniker-end

::: moniker range=">=vs-2017"

운영 체제에서 정적으로 연결 된 모듈 가져오기를 확인 하는 경우 사용 되는 기본 로드 플래그를 설정 합니다.

## <a name="syntax"></a>구문

> **/DEPENDENTLOADFLAG**[ __:__ *load_flags*]

### <a name="arguments"></a>인수

*load_flags*<br/>
모듈의 정적으로 연결 된 가져오기 종속성을 확인할 때 적용할 로드 플래그를 지정 하는 선택적 정수 값입니다. 기본값은 0입니다. 지원 되는 플래그 값 목록은 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)의 `LOAD_LIBRARY_SEARCH_*` 항목을 참조 하세요.

## <a name="remarks"></a>주의

운영 체제는 모듈의 정적으로 연결 된 가져오기를 확인할 때 [기본 검색 순서](/windows/win32/dlls/dynamic-link-library-search-order)를 사용 합니다. **/DEPENDENTLOADFLAG** 옵션을 사용 하 여 이러한 가져오기를 확인 하는 데 사용 되는 검색 경로를 변경 하는 *load_flags* 값을 지정할 수 있습니다. 지원 되는 운영 체제에서는 `LOAD_LIBRARY_SEARCH` 매개 변수를 사용할 때 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa) 가 수행 하는 작업과 비슷하게 정적 가져오기 해상도 검색 순서를 변경 합니다. *Load_flags*에 의해 설정 된 검색 순서에 대 한 자세한 내용은 [검색 순서를 사용 하 여 LOAD_LIBRARY_SEARCH 플래그](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags)를 참조 하세요.

이 플래그를 사용 하 여 하나의 [DLL 심기 공격](/windows/win32/dlls/dynamic-link-library-security) 벡터를 더 어렵게 만들 수 있습니다. 예를 들어, DLL을 정적으로 연결 하는 앱을 살펴보겠습니다.

- 공격자는 응용 프로그램 디렉터리와 같이 가져오기 확인 검색 경로에서 이름이 같은 DLL을 이전 상태로 만들 수 있습니다. 보호 된 디렉터리는 더 어려워집니다. 하지만 공격자가 변경 하는 경우에는 불가능 합니다.

- 응용 프로그램,%windows%\system32 및% windows% 디렉터리에 DLL이 없으면 가져오기 확인은 현재 디렉터리로 이동 합니다. 공격자가 DLL을 공장에 연결할 수 있습니다.

두 경우 모두 `/DEPENDENTLOADFLAG:0x800` 링크 옵션 (`LOAD_LIBRARY_SEARCH_SYSTEM32`플래그의 값)을 지정 하는 경우 모듈 검색 경로 는%windows%\system32 디렉터리로 제한 됩니다. 다른 디렉터리에 대 한 심기 공격 으로부터 보호를 제공 합니다. 자세한 내용은 [동적 연결 라이브러리 보안](/windows/win32/dlls/dynamic-link-library-security)을 참조 하세요.

모든 DLL에서 **/DEPENDENTLOADFLAG** 옵션에 의해 설정 된 값을 확인 하려면 [/loadconfig](loadconfig.md) 옵션과 함께 [DUMPBIN](dumpbin-reference.md) 명령을 사용 합니다.

**/DEPENDENTLOADFLAG** 옵션은 Visual Studio 2017의 새로운 옵션입니다. Windows 10 RS1 이상 버전에서 실행 되는 앱에만 적용 됩니다. 이 옵션은 앱을 실행 하는 다른 운영 체제에서 무시 됩니다.

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 DEPENDENTLOADFLAG 링커 옵션을 설정 하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **구성 속성** > **링커** > **명령줄** 속성 페이지를 선택 합니다.

1. **추가 옵션**에 옵션을 입력 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하세요.

## <a name="see-also"></a>참조

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
- [DLL에 실행 파일을 암시적으로 연결](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [사용할 링크 방법 결정](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [동적 연결 라이브러리 검색 순서](/windows/win32/Dlls/dynamic-link-library-search-order)
- [동적 연결 라이브러리 보안](/windows/win32/dlls/dynamic-link-library-security)

::: moniker-end
