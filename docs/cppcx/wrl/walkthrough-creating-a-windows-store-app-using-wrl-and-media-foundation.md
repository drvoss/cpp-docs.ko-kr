---
title: '연습: WRL 및 미디어 파운데이션을 사용하여 UWP 앱 만들기'
ms.date: 04/23/2019
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: 272092982c5e9cc57f52043e08c8bd384c43ea96
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031513"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>연습: WRL 및 미디어 파운데이션을 사용하여 UWP 앱 만들기

> [!NOTE]
> 새 UWP 앱 및 구성 요소의 경우 Windows 런타임 API에 대한 새로운 표준 C++17 언어 프로젝션인 [C++/WinRT를](/windows/uwp/cpp-and-winrt-apis/)사용하는 것이 좋습니다. C ++/WinRT는 버전 1803이후의 Windows 10 SDK에서 사용할 수 있습니다. C++/WinRT는 헤더 파일에 전적으로 구현되며 최신 Windows API에 대한 일류 액세스를 제공하도록 설계되었습니다.

이 자습서에서는 Windows 런타임 C++ 템플릿 라이브러리(WRL)를 사용하여 [Microsoft 미디어 재단을](/windows/win32/medfound/microsoft-media-foundation-sdk)사용하는 UWP(유니버설 Windows 플랫폼) 앱을 만드는 방법을 배웁니다.

이 예제에서는 웹캠에서 캡처된 이미지에 회색조 효과를 적용하는 사용자 지정 Media Foundation 변형을 만듭니다. 앱에서는 C++를 사용하여 사용자 지정 변환을 정의하고, C#을 사용하여 구성 요소를 통해 캡처된 이미지를 변환합니다.

> [!NOTE]
> C# 대신 JavaScript, Visual Basic 또는 C++를 사용하여 사용자 지정 변환 구성 요소를 사용할 수도 있습니다.

대부분의 경우 C++/CX를 사용하여 Windows 런타임을 만들 수 있습니다. 그러나 때로는 WRL을 사용해야 합니다. 예를 들어 Microsoft 미디어 재단에 대한 미디어 확장을 만들 때 COM 및 Windows 런타임 인터페이스를 모두 구현하는 구성 요소를 만들어야 합니다. C++/CX는 Windows 런타임 개체만 만들 수 있으므로 COM 및 Windows 런타임 인터페이스를 모두 구현할 수 있으므로 WRL을 사용해야 합니다.

> [!NOTE]
> 이 코드 예제는 길지만, 유용한 Media Foundation 변환을 만드는 데 필요한 최소한의 코드를 보여 줍니다. 이를 사용자 지정 변형의 시작점으로 사용할 수 있습니다. 이 예제는 미디어 확장 을 사용하여 비디오에 효과를 적용하고, 비디오를 디코딩하고, 미디어 스트림을 생성하는 구성표 처리기를 만드는 [Media 확장 샘플에서](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)조정됩니다.

## <a name="prerequisites"></a>전제 조건

- Visual Studio 2017 이상에서 UWP 지원은 선택적 구성 요소입니다. 설치하려면 Windows 시작 메뉴에서 Visual Studio 설치 관리자를 열고 Visual Studio 버전을 찾습니다. **수정을** 선택한 다음 **범용 Windows 플랫폼 개발** 타일이 선택되어 있는지 확인합니다. **선택적 구성 요소에서** Visual Studio 2017의 **UWP(v141)** 및 Visual Studio 2019의 **UWP용 C++ 도구(v142)에 대한 C++ 도구를** 확인합니다. 그런 다음 사용하려는 Windows SDK 버전을 확인합니다.

- [Windows 런타임을](/uwp/api/)경험해 보세요.

- COM 경험

- 웹캠.

## <a name="key-points"></a>주요 사항

- 사용자 지정 Media Foundation 구성 요소를 만들려면 MIDL(Microsoft Interface Definition Language) 정의 파일을 사용하여 인터페이스를 정의하고 해당 인터페이스를 구현한 후 다른 구성 요소에서 활성화할 수 있도록 합니다.

- `namespace` 및 `runtimeclass` 속성 및 `NTDDI_WIN8` [버전](/windows/win32/Midl/version) 특성 값은 WRL을 사용하는 미디어 파운데이션 구성 요소에 대한 MIDL 정의의 중요한 부분입니다.

- [Microsoft:WRL::RuntimeClass는](runtimeclass-class.md) 사용자 지정 미디어 파운데이션 구성 요소의 기본 클래스입니다. [Microsoft:WRL:RuntimeClassType::WinRtClassicComMix](runtimeclasstype-enumeration.md) 열거형 값은 템플릿 인수로 제공되며 Windows 런타임 클래스와 클래식 COM 런타임 클래스로 모두 사용할 클래스를 표시합니다.

- [InspectableClass](inspectableclass-macro.md) 매크로는 참조 계산 및 `QueryInterface` 메서드와 같은 기본 COM 기능을 구현하고 런타임 클래스 이름 및 신뢰 수준을 설정합니다.

- Microsoft::WRL::[모듈 클래스를](module-class.md) 사용하여 [DllGetActivationFactory,](/windows/win32/winrt/functions) [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)및 [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject)와 같은 DLL 진입점 함수를 구현합니다.

- 구성 요소 DLL을 runtimeobject.lib에 연결합니다. 또한 링커 줄에 [/WINMD를](../../cppcx/compiler-and-linker-options-c-cx.md) 지정하여 Windows 메타데이터를 생성합니다.

- 프로젝트 참조를 사용하여 UWP 앱에서 WRL 구성 요소에 액세스할 수 있도록 합니다.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>WRL을 사용하여 미디어 파운데이션 그레이스케일 변환 구성 요소를 만들려면

1. Visual Studio에서 **빈 솔루션** 프로젝트를 만듭니다. 프로젝트 이름(예: *MediaCapture.*

1. 솔루션에 **DLL(범용 Windows)** 프로젝트를 추가합니다. 프로젝트의 이름을 지정하는 예: *그레이스케일변환*.

1. 프로젝트에 **Midl 파일(.idl)** 파일을 추가합니다. 파일 이름(예: *GrayscaleTransform.idl)*

1. 이 코드를 그레이스케일Transform.idl에 추가합니다.

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. 다음 코드를 사용하여 다음 의 `pch.h`내용을 대체합니다.

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. 프로젝트에 새 헤더 파일을 추가하고 이름을 `BufferLock.h`지정한 다음 내용을 이 코드로 바꿉니다.

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. `GrayscaleTransform.h`이 예제에서는 사용되지 않습니다. 원하는 경우 프로젝트에서 제거할 수 있습니다.

1. 다음 코드를 사용하여 다음 의 `GrayscaleTransform.cpp`내용을 대체합니다.

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. 프로젝트에 새 모듈 정의 파일을 추가하고 이름을 `GrayscaleTransform.def`지정한 다음 이 코드를 추가합니다.

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. 다음 코드를 사용하여 다음 의 `dllmain.cpp`내용을 대체합니다.

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. 프로젝트의 **속성 페이지** 대화 상자에서 다음 **Linker** 속성을 설정합니다.

   1. 모듈 **정의 파일에**대한 **입력** `GrayScaleTransform.def`에서 를 지정합니다.

   1. 또한 **Input**에서 `runtimeobject.lib` `mfuuid.lib`" `mfplat.lib` 및 **추가 종속성** 속성에 추가합니다.

   1. **Windows 메타데이터에서**Windows **메타데이터 생성을** **예(/WINMD)로**설정합니다.

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>C# 앱에서 WRL 사용자 지정 미디어 파운데이션 구성 요소를 사용하려면

1. 솔루션에 새 **C# 빈 앱(유니버설 Windows)** 프로젝트를 추가합니다. `MediaCapture` 프로젝트 이름(예: *MediaCapture.*

1. **MediaCapture** 프로젝트에서 프로젝트에 대한 참조를 `GrayscaleTransform` 추가합니다. 방법을 알아보려면 [참조 관리자를 사용하여 참조 추가 또는 제거 방법을 참조합니다.](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)

1. 기능 `Package.appxmanifest` **탭에서** **마이크** 및 **웹캠을**선택합니다. 두 기능 모두 웹캠에서 사진을 캡처하는 데 필요합니다.

1. 에서 `MainPage.xaml`루트 [그리드](/uwp/api/windows.ui.xaml.controls.grid) 요소에 이 코드를 추가합니다.

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. 다음 코드를 사용하여 다음 의 `MainPage.xaml.cs`내용을 대체합니다.

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

다음 그림에서는 `MediaCapture app`을 보여 주며 있습니다.

![사진을 캡처하는 MediaCapture 앱](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>다음 단계

이 예제에서는 기본 웹캠에서 한 번에 하나씩 사진을 캡처하는 방법을 보여 줍니다. 미디어 확장 샘플은 더 많은 작업을 [수행합니다.](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) 웹캠 디바이스를 열거하고 로컬 스키마 처리기를 사용하는 방법을 보여 주며, 개별 사진과 비디오 스트림 모두에서 작동하는 추가 미디어 효과를 보여 줍니다.

## <a name="see-also"></a>참조

[Windows 런타임 C++ 템플릿 라이브러리(WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[마이크로소프트 미디어 재단](/windows/win32/medfound/microsoft-media-foundation-sdk)<br/>
[미디어 확장 샘플](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)
