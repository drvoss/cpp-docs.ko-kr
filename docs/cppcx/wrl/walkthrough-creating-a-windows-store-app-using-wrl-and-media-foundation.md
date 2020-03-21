---
title: '연습: WRL 및 미디어 파운데이션를 사용 하 여 UWP 앱 만들기'
ms.date: 04/23/2019
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: 5c6fd2613c34fdecdf9128ed6a5d22d563961939
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079884"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>연습: WRL 및 미디어 파운데이션를 사용 하 여 UWP 앱 만들기

> [!NOTE]
> 새 UWP 앱 및 구성 요소의 경우 Windows 런타임 api에 대해 새로운 표준 c + + 17 언어 [ C++프로젝션을 사용 하](/windows/uwp/cpp-and-winrt-apis/)는 것이 좋습니다. C++/WinRT는 Windows 10 SDK에서 버전 1803 이후 버전으로 제공 됩니다. C++/WinRT는 헤더 파일에 완전히 구현 되며 최신 Windows API에 대 한 최고 수준의 액세스를 제공 하도록 설계 되었습니다.

이 자습서에서는 WRL (Windows 런타임 C++ 템플릿 라이브러리)를 사용 하 여 [Microsoft 미디어 파운데이션](/windows/win32/medfound/microsoft-media-foundation-sdk)를 사용 하는 UWP (유니버설 Windows 플랫폼) 앱을 만드는 방법에 대해 설명 합니다.

이 예제에서는 웹캠에서 캡처된 이미지에 회색조 효과를 적용하는 사용자 지정 Media Foundation 변형을 만듭니다. 앱에서는 C++를 사용하여 사용자 지정 변환을 정의하고, C#을 사용하여 구성 요소를 통해 캡처된 이미지를 변환합니다.

> [!NOTE]
> C# 대신 JavaScript, Visual Basic 또는 C++를 사용하여 사용자 지정 변환 구성 요소를 사용할 수도 있습니다.

대부분의 경우에는/Cx를 C++사용 하 여 Windows 런타임를 만들 수 있습니다. 그러나 경우에 따라 WRL를 사용 해야 합니다. 예를 들어 Microsoft 미디어 파운데이션 용 미디어 확장을 만드는 경우 COM 및 Windows 런타임 인터페이스를 모두 구현 하는 구성 요소를 만들어야 합니다. /Cx C++는 Windows 런타임 개체만 만들 수 있으므로 미디어 확장을 만들려면 COM 및 Windows 런타임 인터페이스를 모두 구현할 수 있으므로 WRL를 사용 해야 합니다.

> [!NOTE]
> 이 코드 예제는 길지만, 유용한 Media Foundation 변환을 만드는 데 필요한 최소한의 코드를 보여 줍니다. 이를 사용자 지정 변형의 시작점으로 사용할 수 있습니다. 이 예제는 미디어 확장을 사용 하 여 비디오에 효과를 적용 하 고, 비디오를 디코딩하고, 미디어 스트림을 생성 하는 스키마 처리기를 만드는 [미디어 확장 샘플](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)에서 적용 됩니다.

## <a name="prerequisites"></a>필수 조건

- Visual Studio 2017 이상에서 UWP 지원은 선택적 구성 요소입니다. 설치 하려면 Windows 시작 메뉴에서 Visual Studio 설치 관리자을 열고 Visual Studio의 버전을 찾습니다. **수정** 을 선택 하 고 **유니버설 Windows 플랫폼 개발** 타일이 선택 되어 있는지 확인 합니다. **선택적 구성 요소** 에서 visual studio 2017 용  **C++ v141 (uwp 용 도구)** 또는  **C++ visual studio 2019 용 도구 (v142)** 를 참조 하세요. 그런 다음 사용 하려는 Windows SDK 버전을 확인 합니다.

- [Windows 런타임](/uwp/api/)사용 경험

- COM 경험

- 웹캠.

## <a name="key-points"></a>주요 사항

- 사용자 지정 Media Foundation 구성 요소를 만들려면 MIDL(Microsoft Interface Definition Language) 정의 파일을 사용하여 인터페이스를 정의하고 해당 인터페이스를 구현한 후 다른 구성 요소에서 활성화할 수 있도록 합니다.

- `namespace` 및 `runtimeclass` 특성과 `NTDDI_WIN8`[version](/windows/win32/Midl/version) 특성 값은 WRL를 사용 하는 미디어 파운데이션 구성 요소에 대 한 MIDL 정의의 중요 한 부분입니다.

- [Microsoft:: WRL:: RuntimeClass](runtimeclass-class.md) 은 사용자 지정 미디어 파운데이션 구성 요소의 기본 클래스입니다. 템플릿 인수로 제공 되는 [Microsoft:: WRL:: RuntimeClassType:: WinRtClassicComMix](runtimeclasstype-enumeration.md) enum 값은 클래스를 Windows 런타임 클래스 및 클래식 COM 런타임 클래스로 사용 하도록 표시 합니다.

- [InspectableClass](inspectableclass-macro.md) 매크로는 참조 횟수 및 `QueryInterface` 메서드와 같은 기본 COM 기능을 구현 하 고 런타임 클래스 이름 및 신뢰 수준을 설정 합니다.

- Microsoft:: WRL::[Module 클래스](module-class.md) 를 사용 하 여 [DllGetActivationFactory](/windows/win32/winrt/functions), [DLLCANUNLOADNOW](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)및 [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject)와 같은 DLL 진입점 함수를 구현 합니다.

- 구성 요소 DLL을 runtimeobject.lib에 연결합니다. 또한 Windows 메타 데이터를 생성 하려면 링커 줄에서 [/Winmd](../../cppcx/compiler-and-linker-options-c-cx.md) 를 지정 합니다.

- 프로젝트 참조를 사용 하 여 UWP 앱에서 WRL 구성 요소에 액세스할 수 있도록 합니다.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>WRL를 사용 하 여 미디어 파운데이션 회색조 변환 구성 요소를 만들려면

1. Visual Studio에서 **빈 솔루션** 프로젝트를 만듭니다. 프로젝트 이름을 *MediaCapture*로 합니다 (예:).

1. **DLL (유니버설 Windows)** 프로젝트를 솔루션에 추가 합니다. 프로젝트 이름을 *grayscaletransform.def*로 합니다 (예:).

1. **Midl 파일 (.idl)** 파일을 프로젝트에 추가 합니다. 파일 이름을 *grayscaletransform.def*와 같이 합니다.

1. Grayscaletransform.def에 다음 코드를 추가 합니다.

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. 다음 코드를 사용 하 여 `pch.h`내용을 바꿉니다.

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. 프로젝트에 새 헤더 파일을 추가 하 고 `BufferLock.h`이름을로 지정한 다음 내용을 다음 코드로 바꿉니다.

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. 이 예제에서는 `GrayscaleTransform.h` 사용 되지 않습니다. 원하는 경우 프로젝트에서 제거할 수 있습니다.

1. 다음 코드를 사용 하 여 `GrayscaleTransform.cpp`내용을 바꿉니다.

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. 프로젝트에 새 모듈 정의 파일을 추가 하 고 `GrayscaleTransform.def`이름을로 지정한 후 다음 코드를 추가 합니다.

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. 다음 코드를 사용 하 여 `dllmain.cpp`내용을 바꿉니다.

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. 프로젝트의 **속성 페이지** 대화 상자에서 다음 **링커** 속성을 설정 합니다.

   1. **입력**에서 **모듈 정의 파일**에 대해 `GrayScaleTransform.def`를 지정 합니다.

   1. 또한 **입력**에서 **추가 종속성** 속성에 `runtimeobject.lib`, `mfuuid.lib`및 `mfplat.lib`를 추가 합니다.

   1. **Windows 메타 데이터**에서 **Windows 메타 데이터 생성** 을 **예**로 설정 합니다.

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>WRL를 사용 하 여 C# 앱에서 사용자 지정 미디어 파운데이션 구성 요소를 사용 하려면

1. 새  **C# 빈 앱 (유니버설 Windows)** 프로젝트를 `MediaCapture` 솔루션에 추가 합니다. 프로젝트 이름을 *MediaCapture*로 합니다 (예:).

1. **MediaCapture** 프로젝트에서 `GrayscaleTransform` 프로젝트에 대 한 참조를 추가 합니다. 방법에 대 한 자세한 내용은 [방법: 참조 관리자를 사용 하 여 참조 추가 또는 제거](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)를 참조 하세요.

1. `Package.appxmanifest`의 **기능** 탭에서 **마이크** 및 **웹캠**를 선택 합니다. 두 기능 모두 웹캠에서 사진을 캡처하는 데 필요합니다.

1. `MainPage.xaml`에서 루트 [그리드](/uwp/api/Windows.UI.Xaml.Controls.Grid) 요소에 다음 코드를 추가 합니다.

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. 다음 코드를 사용 하 여 `MainPage.xaml.cs`내용을 바꿉니다.

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

다음 그림은 `MediaCapture app`를 보여 줍니다.

![사진을 캡처하는 MediaCapture 앱](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>다음 단계

이 예제에서는 기본 웹캠에서 한 번에 하나씩 사진을 캡처하는 방법을 보여 줍니다. [미디어 확장 샘플](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) 에서 더 많은 기능을 수행 합니다. 웹캠 디바이스를 열거하고 로컬 스키마 처리기를 사용하는 방법을 보여 주며, 개별 사진과 비디오 스트림 모두에서 작동하는 추가 미디어 효과를 보여 줍니다.

## <a name="see-also"></a>참고 항목

[Windows 런타임 C++ 템플릿 라이브러리(WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft 미디어 파운데이션](/windows/win32/medfound/microsoft-media-foundation-sdk)<br/>
[미디어 확장 샘플](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)
