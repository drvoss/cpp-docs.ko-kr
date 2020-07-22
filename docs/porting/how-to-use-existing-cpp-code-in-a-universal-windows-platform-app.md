---
title: '방법: 유니버설 Windows 플랫폼 앱에서 기존 C++ 코드 사용'
ms.date: 04/08/2019
ms.assetid: 87e5818c-3081-42f3-a30d-3dca2cf0645c
ms.openlocfilehash: 511bf07950cfb50f67a2027b9051c3efd7cc3b45
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86405054"
---
# <a name="how-to-use-existing-c-code-in-a-universal-windows-platform-app"></a>방법: 유니버설 Windows 플랫폼 앱에서 기존 C++ 코드 사용

데스크톱 프로그램을 UWP(유니버설 Windows 플랫폼) 환경에서 실행되게 하는 가장 쉬운 방법은 데스크톱 브리지 기술을 사용하는 것일 수 있습니다. 여기에는 코드를 변경할 필요 없이 기존 애플리케이션을 UWP 앱으로 패키징하는 데스크톱 앱 변환기가 포함됩니다. 자세한 내용은 [데스크톱 브리지](/windows/uwp/porting/desktop-to-uwp-root)를 참조하세요.

이 항목의 나머지 부분에서는 C++ 라이브러리(DLL 및 정적 라이브러리)를 유니버설 Windows 플랫폼으로 포팅하는 방법을 설명합니다. 여러 UWP 앱에서 핵심 C++ 논리를 사용할 수 있도록 이 작업을 수행하는 것이 좋습니다.

UWP 앱은 보호된 환경에서 실행되며 이에 따라 플랫폼의 보안을 손상시킬 수 있는 많은 Win32, COM 및 CRT API 호출이 허용되지 않습니다. `/ZW` 옵션을 사용하는 경우 컴파일러는 이러한 호출을 검색하고 오류를 생성할 수 있습니다. 애플리케이션에서 앱 인증 키트를 사용하여 금지된 API를 호출하는 코드를 검색할 수 있습니다. 자세한 내용은 [Windows 앱 인증 키트](/windows/uwp/debug-test-perf/windows-app-certification-kit)를 참조하세요.

라이브러리의 소스 코드를 사용할 수 있는 경우 금지된 API 호출을 제거할 수 있습니다. 허용되거나 금지되는 API 목록을 비롯한 자세한 내용은 [UWP 앱용 Win32 및 COM API](/uwp/win32-and-com/win32-and-com-for-uwp-apps) 및 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요. 일부 대안은 [UWP 앱에서 Windows API의 대안](/uwp/win32-and-com/alternatives-to-windows-apis-uwp)에서 찾을 수 있습니다.

유니버설 Windows 프로젝트의 참조를 클래식 데스크톱 라이브러리에 추가하려고 하면 라이브러리가 호환되지 않는다는 오류 메시지가 표시됩니다. 정적 라이브러리의 경우 클래식 Win32 애플리케이션에서와 마찬가지로 라이브러리(.lib 파일)를 링커 입력에 추가하기만 하여 라이브러리에 링크할 수 있습니다. 바이너리만 사용할 수 있는 라이브러리의 경우 이것이 유일한 옵션입니다. 정적 라이브러리는 앱의 실행 파일에 링크되지만 UWP 앱에서 사용하는 Win32 DLL은 프로젝트에 포함하고 콘텐츠로 표시하여 앱에 패키지해야 합니다. UWP 앱에서 Win32 DLL을 로드하려면 `LoadLibrary` 또는 `LoadLibraryEx` 대신 [LoadPackagedLibrary](/windows/win32/api/winbase/nf-winbase-loadpackagedlibrary)도 호출해야 합니다.

DLL 또는 정적 라이브러리의 소스 코드가 있는 경우 `/ZW`를 사용하여 UWP 프로젝트로 다시 컴파일할 수 있습니다. 이렇게 하면 **솔루션 탐색기**를 사용하여 참조를 추가하고 C++ UWP 앱에서 사용할 수 있습니다. DLL의 경우 내보내기 라이브러리에 링크합니다.

다른 언어로 호출자에게 기능을 노출하기 위해 라이브러리를 Windows 런타임 구성 요소로 변환할 수 있습니다. Windows 런타임 구성 요소는 .NET 및 JavaScript 소비자가 요구하는 방식으로 콘텐츠를 설명하는 .winmd 파일의 형태로 메타데이터를 포함한다는 점에서 일반적인 DLL과 다릅니다. API 요소를 다른 언어에 노출하기 위해 ref 클래스와 같은 C++/CX 구문을 추가하고 클래스를 공용으로 만들거나 [WRL(Windows 런타임 C++ 템플릿 라이브러리)](../windows/windows-runtime-cpp-template-library-wrl.md)을 사용할 수 있습니다.  Windows 10 이상 버전에서는 C++/CX 대신 [C++/WinRT 라이브러리](https://github.com/microsoft/cppwinrt)를 사용할 수 있습니다.

앞의 설명은 다르게 처리되어야 하는 COM 구성 요소의 경우에는 적용되지 않습니다. EXE 또는 DLL에 COM 서버가 있는 경우 [등록이 필요하지 않은 COM 구성 요소](/windows/win32/sbscs/creating-registration-free-com-objects)로 패키지하는 한 유니버설 Windows 프로젝트에서 사용할 수 있으며 콘텐츠 파일로 프로젝트에 추가하고 [CoCreateInstanceFromApp](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstancefromapp)을 사용하여 인스턴스화할 수 있습니다. 자세한 내용은 [Windows 스토어 C++ 프로젝트에서 Free-COM DLL 사용](/archive/blogs/win8devsupport/using-free-com-dll-in-windows-store-c-project)을 참조하세요.

UWP로 포팅하려는 기존 COM 라이브러리가 있는 경우 [WRL(Windows 런타임 C++ 템플릿 라이브러리)](../windows/windows-runtime-cpp-template-library-wrl.md)을 사용하여 Windows 런타임 구성 요소로 변환할 수 있습니다. WRL은 ATL 및 OLE의 모든 기능을 지원하지 않으므로 이러한 포트가 적합한지 여부는 COM 코드가 구성 요소에 필요한 COM, ATL 및 OLE의 어떤 기능에 얼마나 많이 의존하는지에 따라 달라집니다.

이들은 UWP 프로젝트에서 기존 C++ 코드를 사용할 수 있는 다양한 방법입니다. 구성 요소 확장(C++/CX)을 사용하도록 설정하여(즉, `/ZW` 옵션을 사용하여) 코드를 다시 컴파일할 필요가 없는 방법도 있지만 그렇지 않은 방법도 있으므로 표준 C++로 코드를 유지해야 하거나 일부 코드의 경우 클래식 Win32 컴파일 환경을 보존해야 하는 경우 적절한 아키텍처를 선택하여 그렇게 할 수 있습니다. 예를 들어 C#, Visual Basic 및 JavaScript 호출자에게 노출될 UWP UI 및 형식을 포함하는 모든 코드는 Windows 앱 프로젝트와 Windows 런타임 구성 요소 프로젝트에 있어야 합니다. C++(C++/CX 포함) 코드에서만 소비되어야 하는 코드는 `/WX` 옵션을 사용하여 컴파일되는 프로젝트나 표준 C++ 프로젝트에 있을 수 있습니다. 바이너리 전용 코드는 금지된 API를 사용하지 않는 경우에만 정적 라이브러리로 링크하여 사용하거나 콘텐츠로 앱과 함께 패키지하고 DLL에서 로드할 수 있습니다.

이러한 개발 시나리오 중 어느 것을 선택하든 간에 클래식 데스크톱 Win32와 UWP 모두에서 조건부로 코드를 컴파일할 수 있도록 하기 위해 코드에서 사용할 수 있는 많은 매크로 정의를 알고 있어야 합니다.

```cpp
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)
```

이러한 문은 각각 UWP 앱, Windows Phone 스토어 앱 중 하나 또는 둘 다에 적용되거나 적용되지 않습니다(클래식 Win32 데스크톱만 해당). 이러한 매크로는 Windows SDK 8.1 이상에서만 사용할 수 있으므로 이전 버전의 Windows SDK 또는 Windows 이외의 다른 플랫폼 용으로 코드를 컴파일해야 하면 이러한 매크로가 정의되지 않은 경우도 고려해야 합니다.

이 항목에는 다음 절차가 포함됩니다.

- [UWP 앱에서 Win32 DLL 사용](#BK_Win32DLL)

- [UWP 앱에서 네이티브 c + + 정적 라이브러리 사용](#BK_StaticLib)

- [Windows 런타임 구성 요소로 c + + 라이브러리 포팅](#BK_WinRTComponent)

## <a name="using-a-win32-dll-in-a-uwp-app"></a><a name="BK_Win32DLL"></a>UWP 앱에서 Win32 DLL 사용

보안과 안정성을 높이기 위해 유니버설 Windows 앱은 제한된 런타임 환경에서 실행되므로 클래식 Windows 데스크톱 애플리케이션에서 사용하듯이 네이티브 DLL을 사용할 수 없습니다. DLL의 소스 코드가 있는 경우 UWP에서 실행되도록 코드를 이식할 수 있습니다. 먼저 프로젝트를 UWP 프로젝트로 식별하기 위해 몇 가지 프로젝트 설정과 프로젝트 파일 메타데이터를 변경합니다. C++/CX를 사용하도록 설정하는 `/ZW` 옵션을 사용하여 라이브러리 코드를 컴파일해야 합니다. 특정 API 코드는 해당 환경과 관련된 더 엄격한 제어 때문에 UWP 앱에서 허용되지 않습니다. [UWP 앱용 Win32 및 COM API](/uwp/win32-and-com/win32-and-com-for-uwp-apps)를 참조하세요.

`__declspec(dllexport)`을 사용하여 함수를 노출하는 네이티브 DLL이 있는 경우에는 다음 절차가 적용됩니다.

### <a name="to-port-a-native-dll-to-the-uwp-without-creating-a-new-project"></a>새 프로젝트를 만들지 않고 네이티브 DLL을 UWP로 이식하려면

1. `__declspec(dllexport)`을 사용하여 함수를 내보내는 네이티브 DLL이 있는 경우 DLL을 UWP 프로젝트로 다시 컴파일하여 UWP 앱에서 해당 함수를 호출할 수 있습니다. 예를 들어 다음 헤더 파일과 같은 코드를 사용하며 몇 가지 클래스와 해당 메서드를 내보내는 DLL이 있으며

    ```cpp
    // giraffe.h
    #pragma once

    #ifdef _DLL
    #define GIRAFFE_API __declspec(dllexport)
    #else
    #define GIRAFFE_API
    #endif

    GIRAFFE_API int giraffeFunction();

    class Giraffe
    {
        int id;
            Giraffe(int id_in);
        friend class GiraffeFactory;

    public:
        GIRAFFE_API int GetID();
    };

    class GiraffeFactory
    {
        static int nextID;

    public:
        GIRAFFE_API GiraffeFactory();
        GIRAFFE_API static int GetNextID();
        GIRAFFE_API static Giraffe* Create();
    };
    ```

   다음 코드 파일이 있다고 가정합니다.

    ```cpp
    // giraffe.cpp
    #include "stdafx.h"
    #include "giraffe.h"

    Giraffe::Giraffe(int id_in) : id(id_in)
    {
    }

    int Giraffe::GetID()
    {
      return id;
    }

    int GiraffeFactory::nextID = 0;

    GiraffeFactory::GiraffeFactory()
    {
        nextID = 0;
    }

    int GiraffeFactory::GetNextID()
    {
        return nextID;
    }

    Giraffe* GiraffeFactory::Create()
    {
        return new Giraffe(nextID++);
    }

    int giraffeFunction();
    ```

   프로젝트의 모든 항목(stdafx.h, dllmain.cpp)은 표준 Win32 프로젝트 템플릿의 일부입니다. 자체 DLL을 사용하지 않고 이 작업을 진행하려면 Win32 프로젝트를 만들고, 프로젝트 마법사에서 DLL을 선택한 다음 헤더 파일 giraffe.h 및 코드 파일 giraffe.cpp를 추가하고 이 단계의 코드 내용을 해당 파일로 복사합니다.

   이 코드는 `_DLL`이 정의될 때(즉, 프로젝트가 DLL로 빌드될 때) `__declspec(dllexport)`으로 확인되는 매크로 `GIRAFFE_API`를 정의합니다.

2. DLL 프로젝트에 대한 **프로젝트 속성**을 열고 **구성**을 **모든 구성**으로 설정합니다.

3. **프로젝트 속성**의 **C/C++** > **일반** 탭에서 **Windows 런타임 확장 사용**을 **예(/ZW)** 로 설정합니다. 이렇게 하면 구성 요소 확장명(C++/CX)이 활성화됩니다.

4. **솔루션 탐색기**에서 프로젝트 노드를 선택하고 바로 가기 메뉴를 연 다음 **프로젝트 언로드**를 선택합니다. 그런 다음 언로드된 프로젝트 노드에서 바로 가기 메뉴를 열고 프로젝트 파일을 편집하도록 선택합니다. `WindowsTargetPlatformVersion` 요소를 찾아서 다음 요소로 바꿉니다.

    ```xml
    <AppContainerApplication>true</AppContainerApplication>
    <ApplicationType>Windows Store</ApplicationType>
    <WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>
    <WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>
    <ApplicationTypeRevision>10.0</ApplicationTypeRevision>
    ```

   .vcxproj 파일을 닫고 바로 가기 메뉴를 다시 연 다음 **프로젝트 다시 로드**를 선택합니다.

   이제 **솔루션 탐색기**는 프로젝트를 유니버설 Windows 프로젝트로 식별합니다.

5. 미리 컴파일된 헤더 파일 이름이 올바른지 확인합니다. **미리 컴파일된** 헤더 섹션에서 **미리 컴파일된 헤더 파일** 을 *pch* 에서 *stdafx.h*로 변경 합니다. 이렇게 하지 않으면 다음과 같은 오류가 표시됩니다.

   > error C2857: '#include' statement specified with the /Ycpch.h command-line option was not found in the source file(오류 C2857: /Ycpch.h 명령줄 옵션과 함께 지정된 '#include' 문을 소스 파일에서 찾을 수 없습니다.)

   문제는 유니버설 Windows 프로젝트가 미리 컴파일된 헤더 파일에 다른 명명 규칙을 사용한다는 것입니다.

6. 프로젝트를 빌드합니다. 호환되지 않는 명령줄 옵션에 대한 몇 가지 오류가 발생할 수도 있습니다. 예를 들어 현재 더 이상 사용되지 않지만 자주 사용되는 옵션인 **최소 다시 빌드 가능(/Gm)** 은 기본적으로 많은 이전 C++ 프로젝트에서 설정되며 `/ZW`와 호환되지 않습니다.

   유니버설 Windows 플랫폼용으로 컴파일할 경우 일부 기능을 사용할 수 없습니다. 모든 문제에 대한 컴파일러 오류가 표시됩니다. 클린 빌드를 수행할 때까지 이러한 문제를 해결하세요.

7. 동일한 솔루션의 uwp 앱에서 DLL을 사용 하려면 uwp 프로젝트 노드에 대 한 바로 가기 메뉴를 열고 참조 **추가**를 선택  >  **Reference**합니다.

   **프로젝트**  >  **솔루션**아래에서 DLL 프로젝트 옆에 있는 확인란을 선택 하 고 **확인** 단추를 선택 합니다.

8. UWP 앱의 *.pch .h* 파일에 라이브러리의 헤더 파일을 포함 합니다.

    ```cpp
    #include "..\MyNativeDLL\giraffe.h"
    ```

9. 함수를 호출하고 DLL에서 형식을 만드는 코드를 UWP 프로젝트에서 일반적인 방식으로 추가합니다.

    ```cpp
    MainPage::MainPage()
    {
        InitializeComponent();
        GiraffeFactory gf;
        Giraffe* g = gf.Create();
        int id = g->GetID();
    }
    ```

## <a name="using-a-native-c-static-library-in-a-uwp-app"></a><a name="BK_StaticLib"></a> UWP 앱에서 네이티브 C++ 정적 라이브러리 사용

UWP 프로젝트에서 네이티브 C++ 정적 라이브러리를 사용할 수 있지만 알아두어야 할 몇 가지 제한 사항이 있습니다. [C++/CX의 정적 라이브러리](../cppcx/static-libraries-c-cx.md)에 대한 내용을 읽고 시작합니다. UWP 앱에서 정적 라이브러리의 네이티브 코드에 액세스할 수 있지만 이러한 정적 라이브러리에서는 공용 ref 형식을 만들지 않는 것이 좋습니다. `/ZW` 옵션을 사용하여 정적 라이브러리를 컴파일하는 경우 라이브러리 관리자(실제로는 가장된 링커)는 다음과 같이 경고합니다.

> LNK4264: /ZW로 컴파일된 개체 파일을 정적 라이브러리에 보관합니다. Windows 런타임 형식을 작성할 때는 Windows 런타임 메타데이터를 포함하는 정적 라이브러리와 연결하지 않는 것이 좋습니다.

그러나 `/ZW`를 사용하여 다시 컴파일하지 않고 UWP에서 정적 라이브러리를 사용할 수 있습니다. ref 형식을 선언하거나 C++/CX 구문을 사용할 수 없게 되지만, 네이티브 코드의 라이브러리를 사용하기만 하면 되는 경우에는 다음 단계를 수행하여 사용할 수 있습니다.

### <a name="to-use-a-native-c-static-library-in-a-uwp-project"></a>UWP 프로젝트에서 네이티브 C++ 정적 라이브러리를 사용하려면

1. UWP 프로젝트에 대 한 프로젝트 속성의 왼쪽 창에서 **구성 속성**  >  **링커**  >  **입력** 을 선택 합니다. 오른쪽 창에서 **추가 종속성** 속성의 라이브러리에 경로를 추가합니다. 예를 들어 출력을 *SolutionFolder*\Debug\MyNativeLibrary\MyNativeLibrary.lib에 배치하는 프로젝트 라이브러리의 경우 상대 경로 `Debug\MyNativeLibrary\MyNativeLibrary.lib`를 추가합니다.

2. Include 문을 추가 하 *여 파일 (* 있는 경우) 또는 필요한 .cpp 파일에 헤더 파일을 참조 하 고 라이브러리를 사용 하는 코드를 추가 하기 시작 합니다.

   ```cpp
   #include "..\MyNativeLibrary\giraffe.h"
   ```

   **솔루션 탐색기**의 **참조** 노드에서 참조를 추가하지 마세요. 해당 메커니즘은 Windows 런타임 구성 요소에만 적용됩니다.

## <a name="porting-a-c-library-to-a-windows-runtime-component"></a><a name="BK_WinRTComponent"></a> Windows 런타임 구성 요소로 C++ 라이브러리 포팅

UWP 앱의 정적 라이브러리에서 네이티브 API를 사용하려는 경우 네이티브 라이브러리의 소스 코드가 있으면 해당 코드를 Windows 런타임 구성 요소로 이식할 수 있습니다. 이 라이브러리는 더 이상 정적 라이브러리가 아니며 DLL이 됩니다. 모든 C++ UWP 앱에서 이 라이브러리를 사용할 수 있지만, 정적 라이브러리의 경우와 달리 언어에 관계없이 모든 UWP 앱 코드에서 클라이언트가 사용할 수 있는 ref 형식 및 다른 C++/CX 구문을 추가할 수 있습니다. 따라서 C#, Visual Basic 또는 JavaScript에서 이러한 형식에 액세스할 수 있습니다.  기본 절차는 Windows 런타임 구성 요소 프로젝트를 만들고 여기에 정적 라이브러리에 대한 코드를 추가한 다음, 표준 C++ 컴파일에서 `/ZW` 컴파일로 코드를 이동할 때 발생하는 모든 오류를 해결하는 것입니다.

### <a name="to-port-a-c-library-to-a-windows-runtime-component"></a>Windows 런타임 구성 요소로 C++ 라이브러리를 이식하려면

1. Windows 런타임 구성 요소 프로젝트를 만듭니다.

2. 프로젝트를 닫습니다.

3. **Windows 파일 탐색기**에서 프로젝트를 찾습니다. 기본적으로 Visual Studio에서는 문서 폴더에서 Visual Studio 2017\Projects 폴더를 사용합니다. 이식하려는 코드가 포함된 C++ 라이브러리 프로젝트를 찾습니다. C++ 라이브러리에서 소스 파일(하위 디렉터리에 포함된 헤더 파일, 코드 파일 및 다른 모든 리소스)을 복사하여 프로젝트 폴더에 붙여 넣습니다. 이때 동일한 폴더 구조를 유지해야 합니다.

4. Windows 런타임 구성 요소 프로젝트를 다시 열고 **솔루션 탐색기**에서 프로젝트 노드에 대한 바로 가기 메뉴를 연 다음, **추가** > **기존 항목**을 선택합니다.

5. 원래 프로젝트에서 추가할 모든 파일을 선택하고 **확인**을 선택합니다. 필요한 경우 하위 폴더를 대상으로 반복합니다.

6. 이제 중복된 일부 코드가 있을 수도 있습니다. 미리 컴파일된 헤더 (예를 들어 *stdafx.h* 및 *.pch .h*)가 두 개 이상 있는 경우 유지할 헤더를 하나 선택 합니다. 유지할 헤더에 include 문과 같은 필요한 코드를 복사합니다. 그런 다음 다른 헤더를 삭제하고 프로젝트 속성의 **미리 컴파일된 헤더**에서 헤더 파일의 이름이 올바른지 확인합니다.

   미리 컴파일된 헤더로 사용할 파일을 변경한 경우 각 파일에 대한 미리 컴파일된 헤더 옵션이 올바른지 확인합니다. 각 .cpp 파일을 차례로 선택하고 속성 창을 연 다음 **만들기(/Yc)** 로 설정되어야 하는 원하는 미리 컴파일된 헤더를 제외하고 모두 **사용(/Yu)** 으로 설정되어 있는지 확인합니다.

7. 프로젝트를 빌드하고 모든 오류를 해결합니다. 이러한 오류는 `/ZW` 옵션을 사용하기 때문에 발생하거나 새로운 버전의 Windows SDK로 인해 발생할 수 있습니다. 또는 라이브러리가 종속된 헤더 파일과 같은 종속성이나 이전 프로젝트와 새 프로젝트 간의 프로젝트 설정 차이를 반영할 수도 있습니다.

8. 공용 ref 형식을 프로젝트에 추가하거나 일반 형식을 ref 형식으로 변환하여 UWP 앱에서 호출하려는 기능에 대한 진입점을 노출합니다.

9. UWP 앱 프로젝트에서 구성 요소에 대한 참조를 추가하여 구성 요소를 테스트하고 만든 공용 API를 호출하는 코드를 추가합니다.

## <a name="see-also"></a>참고 항목

[유니버설 Windows 플랫폼으로 포팅](../porting/porting-to-the-universal-windows-platform-cpp.md)
