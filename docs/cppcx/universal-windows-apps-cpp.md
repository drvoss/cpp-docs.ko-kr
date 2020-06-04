---
title: 유니버설 Windows 앱(C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.topic: overview
ms.openlocfilehash: 500aa5337382cfb5aca4d4c8d1774d256498d0a0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214280"
---
# <a name="universal-windows-apps-c"></a>유니버설 Windows 앱(C++)

UWP (유니버설 Windows 플랫폼)는 Windows 용 최신 프로그래밍 인터페이스입니다. UWP를 사용 하면 응용 프로그램 또는 구성 요소를 한 번 작성 하 고 Windows 10 장치에 배포할 수 있습니다. 에서 C++ 구성 요소를 작성할 수 있으며, 다른 UWP 호환 언어로 작성 된 응용 프로그램은 사용할 수 있습니다.

대부분의 UWP 설명서는 [유니버설 Windows 플랫폼 설명서](/windows/uwp/)의 Windows 콘텐츠 트리에 있습니다. 여기에서 자습서 및 참조 설명서를 찾을 수 있습니다.

새 UWP 앱 및 구성 요소의 경우 Windows 런타임 api에 대해 새로운 표준 c + + 17 언어 [ C++프로젝션을 사용 하](/windows/uwp/cpp-and-winrt-apis/)는 것이 좋습니다. C++/WinRT는 Windows 10 SDK에서 버전 1803 이후 버전으로 제공 됩니다. C++/WinRT는 헤더 파일에 완전히 구현 되며 최신 Windows API에 대 한 최고 수준의 액세스를 제공 하도록 설계 되었습니다. /Cx 구현과 C++는 다릅니다. C++/WinRT는 비표준 구문이 나 Microsoft 언어 확장을 사용 하지 않으며 컴파일러를 최대한 활용 하 여 최적화 C++ 된 출력을 만듭니다. 자세한 내용은 [/sd에 C++](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)대 한 소개를 참조 하세요.

데스크톱 브리지 앱 변환기를 사용 하 여 Microsoft Store를 통해 배포 하기 위해 기존 데스크톱 응용 프로그램을 패키지할 수 있습니다. 자세한 내용은 Centennial 프로젝트 및 [데스크톱 브리지](/windows/uwp/porting/desktop-to-uwp-root) [에서 C++ Visual Runtime 사용](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) 을 참조 하세요.

## <a name="uwp-apps-that-use-ccx"></a>/Cx를 사용 C++하는 UWP 앱

|||
|-|-|
|[C++/CX 언어 참조](visual-c-language-reference-c-cx.md)|Windows 런타임 Api의 사용을 간소화 C++ 하 고 예외를 기반으로 하는 오류 처리를 사용 하는 확장 집합을 설명 합니다.|
|[앱 및 라이브러리 빌드(C++/CX)](building-apps-and-libraries-c-cx.md)|C++/CX 앱이나 구성 요소에서 액세스할 수 있는 DLL 및 정적 라이브러리를 만드는 방법을 설명합니다.|
|[자습서:/Cx에서 C++UWP "Hello, 세계" 앱 만들기](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|/Cx에서 C++UWP 앱 개발의 기본 개념을 소개 하는 연습입니다. |
|[/Cx에서 C++Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|다른 UWP 앱 및 구성 요소에서 사용할 수 있는 Dll을 만드는 방법을 설명 합니다.|
|[UWP 게임 프로그래밍](/windows/uwp/gaming/)|DirectX 및 C++/cx를 사용 하 여 게임을 만드는 방법을 설명 합니다.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>WRL (Windows 런타임 C++ 템플릿 라이브러리)를 사용 하는 UWP 앱

Windows 런타임 C++ 템플릿 라이브러리는 ISO C++ 코드가 예외 없는 환경에서 Windows 런타임에 액세스할 수 있는 하위 수준 COM 인터페이스를 제공 합니다. 대부분의 경우 UWP 앱 개발용 Windows 런타임 C++ C++ C++ 템플릿 라이브러리 대신/winrt 또는/cx를 사용 하는 것이 좋습니다. Windows 런타임 C++ 템플릿 라이브러리에 대 한 자세한 내용은 [Windows 런타임 C++ 템플릿 라이브러리 (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md)를 참조 하십시오.

## <a name="see-also"></a>참고 항목

[Visual Studio의 C++](../overview/visual-cpp-in-visual-studio.md)<br/>
[C++의 Windows 프로그래밍 개요](../windows/overview-of-windows-programming-in-cpp.md)<br/>
