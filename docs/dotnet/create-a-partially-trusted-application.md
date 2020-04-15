---
title: '방법: 부분적으로 신뢰할 수 있는 응용 프로그램 만들기(C++/CLI)'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
ms.openlocfilehash: 9df3a751f4073472b9495425599aaf43878db99a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364397"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>방법: CRT 라이브러리 DLL에 대한 종속성을 제거하여 부분적으로 신뢰할 수 있는 애플리케이션 만들기

이 항목에서는 msvcm90.dll에 대한 종속성을 제거하여 Visual C++를 사용하여 부분적으로 신뢰할 수 있는 공통 언어 런타임 응용 프로그램을 만드는 방법에 대해 설명합니다.

**/clr로** 빌드된 Visual C++ 응용 프로그램은 C-런타임 라이브러리의 일부인 msvcm90.dll에 대한 종속성을 갖습니다. 응용 프로그램을 부분 신뢰 환경에서 사용하려는 경우 CLR은 DLL에 특정 코드 액세스 보안 규칙을 적용합니다. 따라서 msvcm90.dll 네이티브 코드를 포함 하 고 코드 액세스 보안 정책을 적용할 수 없습니다 때문에이 종속성을 제거 해야 합니다.

응용 프로그램이 C-런타임 라이브러리의 기능을 사용하지 않고 코드에서 이 라이브러리에 대한 종속성을 제거하려면 **/NODEFAULTLIB:msvcmrt.lib** 링커 옵션을 사용하고 ptrustm.lib 또는 ptrustmd.lib중 하나와 연결해야 합니다. 이러한 라이브러리에는 응용 프로그램의 초기화 및 초기화를 위한 개체 파일, 초기화 코드에서 사용하는 예외 클래스 및 관리되는 예외 처리 코드가 포함되어 있습니다. 이러한 라이브러리 중 하나에 연결하면 msvcm90.dll에 대한 종속성이 제거됩니다.

> [!NOTE]
> ptrust 라이브러리를 사용하는 응용 프로그램에 따라 어셈블리 초기화 순서가 다를 수 있습니다. 일반 응용 프로그램의 경우 어셈블리는 일반적으로 로드되는 역순으로 언로드되지만 이는 보장되지 않습니다. 부분 신뢰 응용 프로그램의 경우 어셈블리는 일반적으로 로드되는 순서와 동일한 순서로 언로드됩니다. 이것은 또한 보장되지 않습니다.

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>부분적으로 신뢰할 수 있는 혼합(/clr) 응용 프로그램을 만들려면

1. msvcm90.dll에 대한 종속성을 제거하려면 **/NODEFAULTLIB:msvcmrt.lib** 링커 옵션을 사용하여 이 라이브러리를 포함하지 않도록 링커에 지정해야 합니다. Visual Studio 개발 환경을 사용하거나 프로그래밍 방식으로 이 작업을 수행하는 방법에 대한 자세한 내용은 [/NODEFAULTLIB(라이브러리 무시)를](../build/reference/nodefaultlib-ignore-libraries.md)참조하십시오.

1. ptrustm 라이브러리 중 하나를 링커 입력 종속성에 추가합니다. 릴리스 모드에서 응용 프로그램을 빌드하는 경우 ptrustm.lib를 사용합니다. 디버그 모드의 경우 ptrustmd.lib를 사용합니다. Visual Studio 개발 환경을 사용하거나 프로그래밍 방식으로 이 작업을 수행하는 방법에 대한 자세한 내용은 [을 참조하십시오. Lib 파일을 링커 입력으로](../build/reference/dot-lib-files-as-linker-input.md).

## <a name="see-also"></a>참고 항목

[혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[혼합형 어셈블리 초기화](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[혼합형 어셈블리에 대한 라이브러리 지원](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/link(옵션을 링커로 전달)](../build/reference/link-pass-options-to-linker.md)
