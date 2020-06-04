---
title: '방법: WRL을 사용하여 기본 COM 구성 요소 만들기'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
ms.openlocfilehash: a1507a1a980dfd98a235b7456d73add955c02043
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213917"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>방법: WRL을 사용하여 기본 COM 구성 요소 만들기

WRL (Windows 런타임 C++ 템플릿 라이브러리)를 사용 하 여 UWP (유니버설 Windows 플랫폼) 앱에 사용 하는 것 외에 데스크톱 앱에서 사용할 기본 클래식 COM 구성 요소를 만들 수 있습니다. COM 구성 요소를 만들기 위해 Windows 런타임 C++ 템플릿 라이브러리에는 ATL 보다 더 작은 코드가 필요할 수 있습니다. Windows 런타임 C++ 템플릿 라이브러리에서 지 원하는 COM의 하위 집합에 대 한 자세한 내용은 [템플릿 C++ 라이브러리 Windows 런타임 (WRL)](windows-runtime-cpp-template-library-wrl.md)를 참조 하세요.

이 문서에서는 Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 기본적인 COM 구성 요소를 만드는 방법을 보여 줍니다. 사용자 요구에 가장 적합한 배포 메커니즘을 사용할 수 있지만 이 문서에서는 데스크톱 앱에서 COM 구성 요소를 등록 및 사용하는 기본 방법도 보여 줍니다.

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 기본 클래식 COM 구성 요소를 만들려면

1. Visual Studio에서 **빈 솔루션** 프로젝트를 만듭니다. 프로젝트 이름을 `WRLClassicCOM`합니다 (예:).

2. **Win32 프로젝트** 를 솔루션에 추가 합니다. 프로젝트 이름을 `CalculatorComponent`합니다 (예:). **응용 프로그램 설정** 탭에서 **DLL**을 선택 합니다.

3. **Midl 파일 (.idl)** 파일을 프로젝트에 추가 합니다. 파일의 이름을 `CalculatorComponent.idl`합니다 (예:).

4. CalculatorComponent.idl에 다음 코드를 추가합니다.

   [!code-cpp[wrl-classic-com-component#1](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. CalculatorComponent.cpp에서 `CalculatorComponent` 클래스를 정의합니다. `CalculatorComponent` 클래스는 [Microsoft:: WRL:: RuntimeClass](runtimeclass-class.md)에서 상속 됩니다. [Microsoft:: WRL:: RuntimeClassFlags\<ClassicCom >](runtimeclassflags-structure.md) 는 클래스가 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 및 not [IInspectable](/windows/win32/api/inspectable/nn-inspectable-iinspectable)에서 파생 되도록 지정 합니다. `IInspectable` 는 Windows 런타임 앱 구성 요소에만 사용할 수 있습니다. `CoCreatableClass`는 [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)와 같은 함수와 함께 사용할 수 있는 클래스에 대한 팩터리를 만듭니다.

   [!code-cpp[wrl-classic-com-component#2](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. 다음 코드를 사용 하 `dllmain.cpp`코드를 바꿉니다. 이 파일은 DLL 내보내기 함수를 정의합니다. 이러한 함수는 [Microsoft:: WRL:: module](module-class.md) 클래스를 사용 하 여 모듈에 대 한 클래스 팩터리를 관리 합니다.

   [!code-cpp[wrl-classic-com-component#3](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. **모듈 정의 파일 (.def)** 파일을 프로젝트에 추가 합니다. 파일의 이름을 `CalculatorComponent.def`합니다 (예:). 이 파일은 링커에 내보낼 함수의 이름을 제공합니다.

8. CalculatorComponent.def에 다음 코드를 추가합니다.

    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE
    ```

9. 링커 줄에 runtimeobject.lib를 추가합니다. 방법에 대 한 자세한 내용은을 참조 [하세요. 링커 입력 파일로 서의 Lib 파일](../../build/reference/dot-lib-files-as-linker-input.md)입니다.

### <a name="to-consume-the-com-component-from-a-desktop-app"></a>데스크톱 앱에서 COM 구성 요소를 사용하려면

1. Windows 레지스트리에 COM 구성 요소를 등록합니다. 이렇게 하려면 등록 항목 파일을 만들고 이름을 `RegScript.reg`로 하 고 다음 텍스트를 추가 합니다. Dll *경로 >\<* dll 경로 (예: `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll`)로 바꿉니다.

    ```
    Windows Registry Editor Version 5.00

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}]
    @="CalculatorComponent Class"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\InprocServer32]
    @="<dll-path>"
    "ThreadingModel"="Apartment"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Programmable]

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\TypeLib]
    @="{9D3E6826-CB8E-4D86-8B14-89F0D7EFCD01}"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Version]
    @="1.0"
    ```

2. RegScript .reg를 실행 하거나 프로젝트의 **빌드 후 이벤트**에 추가 합니다. 자세한 내용은 [빌드 전 이벤트/빌드 후 이벤트 명령줄 대화 상자](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box)를 참조 하세요.

3. **Win32 콘솔 응용 프로그램** 프로젝트를 솔루션에 추가 합니다. 프로젝트 이름을 `Calculator`합니다 (예:).

4. 이 코드를 사용 하 여 `Calculator.cpp`내용을 바꿉니다.

   [!code-cpp[wrl-classic-com-component#6](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>강력한 프로그래밍

이 문서에서는 표준 COM 함수를 사용 하 여 Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 com 구성 요소를 작성 하 고 com 지원 기술에 사용할 수 있도록 합니다. 데스크톱 앱에서 C++ [MICROSOFT:: WRL:: ComPtr](comptr-class.md) 와 같은 템플릿 라이브러리 형식을 WINDOWS 런타임 사용 하 여 COM 및 기타 개체의 수명을 관리할 수도 있습니다. 다음 코드는 Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 `ICalculatorComponent` 포인터의 수명을 관리 합니다. `CoInitializeWrapper` 클래스는 COM 라이브러리가 해제되도록 보장하고 COM 라이브러리의 수명이 `ComPtr` 스마트 포인터 개체보다 길도록 보장하는 RAII 래퍼입니다.

[!code-cpp[wrl-classic-com-component#7](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>참고 항목

[Windows 런타임 C++ 템플릿 라이브러리(WRL)](windows-runtime-cpp-template-library-wrl.md)
