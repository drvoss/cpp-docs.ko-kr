---
title: '방법: -clr로 마이그레이션.'
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- upgrading Visual C++ applications, /clr compiler option
- compiling native code [C++]
- interoperability [C++], /clr compiler option
- interop [C++], /clr compiler option
- migration [C++], /clr compiler option
- /clr compiler option [C++], porting to
ms.assetid: c9290b8b-436a-4510-8b56-eae51f4a9afc
ms.openlocfilehash: 339b1f3172d8b82ece3e98f117f53ed399cbd4e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376075"
---
# <a name="how-to-migrate-to-clr"></a>방법: /clr로 마이그레이션

이 항목에서는 기본 코드를 /clr(/clr(일반 [언어 런타임 컴파일 참조)로](../build/reference/clr-common-language-runtime-compilation.md) 컴파일할 때 발생하는 문제에 대해 자세히 설명합니다. **/clr** **/clr를** 사용하면 네이티브 C++ 코드를 호출하고 다른 네이티브 C++ 코드 외에 .NET 어셈블리에서 호출할 수 있습니다. **/clr로**컴파일하는 이점에 대한 자세한 내용은 [혼합(네이티브 및 관리되는) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md) 및 [네이티브 및 .NET 상호 운용성을](../dotnet/native-and-dotnet-interoperability.md) 참조하십시오.

## <a name="known-issues-compiling-library-projects-with-clr"></a>/clr를 가진 라이브러리 프로젝트를 컴파일하는 알려진 문제

Visual Studio에는 **/clr로**라이브러리 프로젝트를 컴파일할 때 알려진 몇 가지 문제가 포함되어 있습니다.

- 코드는 [CRuntimeClass::FromName](../mfc/reference/cruntimeclass-structure.md#fromname)을 통해 런타임시 형식을 쿼리할 수 있습니다. 그러나 형식이 MSIL .dll **(/clr로**컴파일됨)에 있는 `FromName` 경우 정적 생성자가 관리되는 .dll에서 실행되기 전에 호출이 실패할 수 있습니다(관리되는 .dll에서 코드가 실행된 후 FromName 호출이 발생하는 경우 이 문제가 표시되지 않습니다). 이 문제를 해결하려면 관리되는 .dll의 함수를 정의하고 내보내고 네이티브 MFC 응용 프로그램에서 호출하여 관리되는 정적 생성자의 생성을 강제할 수 있습니다. 다음은 그 예입니다.

    ```
    // MFC extension DLL Header file:
    __declspec( dllexport ) void EnsureManagedInitialization () {
       // managed code that won't be optimized away
       System::GC::KeepAlive(System::Int32::MaxValue);
    }
    ```

## <a name="compile-with-visual-c"></a>비주얼 C ++ 컴파일

프로젝트의 모든 모듈에서 **/clr를** 사용하기 전에 먼저 네이티브 프로젝트를 Visual Studio 2010과 컴파일하고 연결합니다.

다음 단계는 **순서대로 /clr** 컴파일에 대한 가장 쉬운 경로를 제공합니다. 이러한 각 단계를 수행한 후 프로젝트를 컴파일하고 실행하는 것이 중요합니다.

### <a name="versions-prior-to-visual-studio-2003"></a>비주얼 스튜디오 2003 이전 버전

Visual Studio 2003 이전 버전에서 Visual Studio 2010으로 업그레이드하는 경우 Visual Studio 2003의 향상된 C++ 표준 준수와 관련된 컴파일러 오류가 표시될 수 있습니다.

### <a name="upgrading-from-visual-studio-2003"></a>비주얼 스튜디오 2003에서 업그레이드

Visual Studio 2003으로 이전에 구축된 프로젝트도 먼저 **/clr** 없이 컴파일해야 합니다. 가장 주의를 기울여야 할 변경 사항은 [CRT의 보안 기능입니다.](../c-runtime-library/security-features-in-the-crt.md) CRT를 사용하는 코드는 사용 중단 경고를 생성할 가능성이 높습니다. 이러한 경고는 억제할 수 있지만 더 나은 보안을 제공하고 코드에서 보안 문제를 나타낼 수 있으므로 새 [보안 강화 버전의 CRT 함수로](../c-runtime-library/security-enhanced-versions-of-crt-functions.md) 마이그레이션하는 것이 좋습니다.

### <a name="upgrading-from-managed-extensions-for-c"></a>C++ 관리형 확장에서 업그레이드

Visual Studio 2005에서 시작하여 C++에 대해 관리되는 확장으로 작성된 코드는 **/clr**에서 컴파일되지 않습니다.

## <a name="convert-c-code-to-c"></a>C 코드를 C++로 변환

Visual Studio는 C 파일을 컴파일하지만 **/clr** 컴파일을 위해 C++로 변환해야 합니다. 실제 파일 이름은 변경할 필요가 없습니다. [/Tp(/Tc, /Tp, /TC, /TP, /TP(소스 파일 유형 지정)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md)를 사용할 수 있습니다.) **/Tp** **/clr에는**C++ 소스 코드 파일이 필요하지만 개체 지향 패러다임을 사용하기 위해 코드를 다시 팩터링할 필요는 없습니다.

C 코드는 C++ 파일로 컴파일될 때 변경이 필요할 가능성이 높습니다. C++ 형식 안전 규칙은 엄격하므로 캐스트를 사용하여 형식 변환을 명시적으로 만들어야 합니다. 예를 들어 malloc은 void 포인터를 반환하지만 캐스트를 사용하여 C의 모든 형식에 포인터에 할당할 수 있습니다.

```
int* a = malloc(sizeof(int));   // C code
int* b = (int*)malloc(sizeof(int));   // C++ equivalent
```

함수 포인터는 C++에서 엄격하게 형식이 안전하므로 다음 C 코드를 수정해야 합니다. C++에서는 함수 포인터 유형을 `typedef` 정의하는 a를 만든 다음 해당 형식을 사용하여 함수 포인터를 캐스팅하는 것이 가장 좋습니다.

```
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code
typedef int(*MYPROC)(int);   // C++ equivalent
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );
```

또한 C++는 함수를 참조하거나 호출하기 전에 프로토타입을 만들거나 완전히 정의해야 합니다.

C 코드에서 사용되는 식별자(예: **가상,** **새, 새,** **삭제,** **bool**, **true,** **false**등)의 키워드로 이름을 바여야 합니다. 이 작업은 일반적으로 간단한 검색 및 바꾸기 작업으로 수행할 수 있습니다.

```
COMObj1->lpVtbl->Method(COMObj, args);  // C code
COMObj2->Method(args);  // C++ equivalent
```

## <a name="reconfigure-project-settings"></a>프로젝트 설정 다시 구성

프로젝트가 Visual Studio 2010에서 컴파일되고 실행된 후에는 기본 구성을 수정하는 대신 **/clr에** 대한 새 프로젝트 구성을 만들어야 합니다. **/clr는** 일부 컴파일러 옵션과 호환되지 않으며 별도의 구성을 만들면 프로젝트를 네이티브 또는 관리로 빌드할 수 있습니다. 속성 페이지 대화 상자에서 **/clr를** 선택하면 **/clr와** 호환되지 않는 프로젝트 설정이 비활성화됩니다(/clr이 나중에 선택되지 않은 경우 비활성화된 옵션은 자동으로 복원되지 않음). **/clr**

### <a name="create-new-project-configurations"></a>새 프로젝트 구성 만들기

**새 프로젝트 구성 대화 상자(빌드** **Build** > 구성**관리자** > **활성 솔루션 구성** > **새)에서** **설정 복사** 옵션을 사용하여 기존 프로젝트 설정에 따라 프로젝트 구성을 만들 수 있습니다. 디버그 구성에 대해 한 번, 릴리스 구성에 대해 한 번 이 작업을 수행합니다. 그런 다음 **/clr-specific** 구성에만 후속 변경 내용을 적용할 수 있으며 원래 프로젝트 구성은 그대로 유지됩니다.

사용자 지정 빌드 규칙을 사용하는 프로젝트에는 추가 주의가 필요할 수 있습니다.

이 단계는 makefiles를 사용하는 프로젝트에 대해 다른 의미를 가합니다. 이 경우 별도의 빌드 대상을 구성하거나 **/clr** 컴파일과 관련된 버전을 원본 복사본에서 만들 수 있습니다.

### <a name="change-project-settings"></a>프로젝트 설정 변경

**/clr는** [/clr(공통 언어 런타임 컴파일)의](../build/reference/clr-common-language-runtime-compilation.md)지침에 따라 개발 환경에서 선택할 수 있습니다. 앞에서 설명한 것처럼 이 단계는 충돌하는 프로젝트 설정을 자동으로 비활성화합니다.

> [!NOTE]
> Visual Studio 2003에서 관리되는 라이브러리 또는 웹 서비스 프로젝트를 업그레이드할 때 **/Zl** 컴파일러 옵션이 **Command Line** 속성 페이지에 추가됩니다. 이로 인해 LNK2001이 발생합니다. 해결하려면 **명령줄** 속성 페이지에서 **/Zl을** 제거합니다. 자세한 내용은 [/Zl(기본 라이브러리 이름 생략)](../build/reference/zl-omit-default-library-name.md) 및 [컴파일러 설정 및 빌드 속성을](../build/working-with-project-properties.md) 참조하십시오. 또는 링커의 **추가 종속성** 속성에 msvcrt.lib 및 msvcmrt.lib를 추가합니다.

makefiles로 빌드된 프로젝트의 경우 **/clr가** 추가되면 호환되지 않는 컴파일러 옵션을 수동으로 사용하지 않도록 설정해야 합니다. **/clr**와 호환되지 않는 컴파일러 옵션에 대한 정보는[/clr 제한을](../build/reference/clr-restrictions.md) 참조하십시오.

### <a name="precompiled-headers"></a>미리 컴파일된 헤더

미리 컴파일된 헤더는 **/clr**에서 지원됩니다. 그러나 **/clr** (나머지는 네이티브로 컴파일)로 CPP 파일 중 일부만 컴파일하는 경우 **/clr로** 생성 된 미리 컴파일 된 헤더가 **/clr**없이 생성 된 헤더와 호환되지 않기 때문에 일부 변경이 필요합니다. 이 비호환성은 **/clr가** 메타데이터를 생성하고 필요로 하기 때문입니다. **따라서 /clr** 컴파일된 모듈은 메타데이터를 포함하지 않는 미리 컴파일된 헤더를 사용할 수 **없으며/clr 모듈이** 아닌 모듈은 메타 데이터를 포함하는 미리 컴파일된 헤더 파일을 사용할 수 없습니다.

일부 모듈이 **컴파일되는** 프로젝트를 컴파일하는 가장 쉬운 방법은 미리 컴파일된 헤더를 완전히 사용하지 않도록 설정하는 것입니다. (프로젝트 속성 페이지 대화 상자에서 C/C++ 노드를 열고 미리 컴파일된 헤더를 선택합니다. 그런 다음 미리 컴파일된 헤더 만들기/사용 속성을 "미리 컴파일된 헤더를 사용하지 않음"으로 변경합니다.

그러나 특히 대규모 프로젝트의 경우 미리 컴파일된 헤더가 훨씬 더 나은 컴파일 속도를 제공하므로 이 기능을 사용하지 않도록 설정하는 것은 바람직하지 않습니다. 이 경우 별도의 미리 컴파일된 헤더를 사용하도록 **/clr** 및 non **/clr** 파일을 구성하는 것이 가장 좋습니다. 이 작업은 **솔루션 탐색기를**사용하여 **컴파일할 모듈/clr를** 다중 선택하고 그룹을 마우스 오른쪽 단추로 클릭하고 속성을 선택하여 한 단계로 수행할 수 있습니다. 그런 다음 PCH 를 통해 파일 만들기/사용 파일 및 미리 컴파일된 헤더 파일 속성을 모두 변경하여 각각 다른 헤더 파일 이름과 PCH 파일을 사용합니다.

## <a name="fixing-errors"></a>오류 수정

**/clr로** 컴파일하면 컴파일러, 링커 또는 런타임 오류가 발생할 수 있습니다. 이 섹션에서는 가장 일반적인 문제에 대해 설명합니다.

### <a name="metadata-merge"></a>메타데이터 병합

데이터 형식의 버전이 다르면 두 형식에 대해 생성된 메타데이터가 일치하지 않기 때문에 링커가 실패할 수 있습니다. 일반적으로 형식의 멤버가 조건부로 정의되지만 형식을 사용하는 모든 CPP 파일에 대한 조건이 동일하지 는 않습니다. 이 경우 링커가 실패하여 기호 이름과 형식이 정의된 두 번째 OBJ 파일의 이름만 보고합니다. OBJ 파일이 링커로 전송되는 순서를 회전하여 다른 버전의 데이터 형식의 위치를 검색하는 것이 유용한 경우가 많습니다.

### <a name="loader-lock-deadlock"></a>로더 잠금 교착 상태

"로더 잠금 교착 상태"가 발생할 수 있지만 결정적이며 런타임에 감지되고 보고됩니다. 자세한 배경, 지침 및 솔루션은 [혼합 어셈블리 초기화를](../dotnet/initialization-of-mixed-assemblies.md) 참조하십시오.

### <a name="data-exports"></a>데이터 내보내기

DLL 데이터를 내보내는 것은 오류가 발생하기 쉽기 때문에 권장되지 않습니다. 이는 DLL의 일부 관리되는 부분이 실행될 때까지 DLL의 데이터 섹션이 초기화되지 않을 수 있기 때문입니다. [#using 지시문](../preprocessor/hash-using-directive-cpp.md).

### <a name="type-visibility"></a>형식 표시 유형

네이티브 형식은 기본적으로 비공개입니다. 이로 인해 네이티브 형식이 DLL 외부에 표시되지 않을 수 있습니다. 이러한 형식에 `public` 추가하여 이 오류를 해결합니다.

### <a name="floating-point-and-alignment-issues"></a>부동점 및 선형 문제

`__controlfp`일반적인 언어 런타임에서는 지원되지 않습니다(자세한 내용은 [_control87, _controlfp, \__control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) 참조). CLR은 [정렬도](../cpp/align-cpp.md)존중하지 않습니다.

### <a name="com-initialization"></a>COM 초기화

공통 언어 런타임은 모듈이 초기화될 때(COM이 자동으로 초기화되면 MTA로 수행될 때) COM을 자동으로 초기화합니다. 결과적으로 COM을 명시적으로 초기화하면 COM이 이미 초기화되었음을 나타내는 반환 코드가 생성됩니다. CLR이 이미 COM을 다른 스레딩 모델로 초기화한 경우 하나의 스레딩 모델로 COM을 명시적으로 초기화하려고 하면 응용 프로그램이 실패할 수 있습니다.

공통 언어 런타임은 기본적으로 COM을 MTA로 시작합니다. [/CLRTHREADATTRIBUTE(CLR 스레드 특성 설정)를](../build/reference/clrthreadattribute-set-clr-thread-attribute.md) 사용하여 이를 수정합니다.

### <a name="performance-issues"></a>성능 이슈

MSIL에 생성된 기본 C++ 메서드가 간접적으로 호출될 때(가상 함수 호출 또는 함수 포인터 사용). 이에 대한 자세한 내용은 [더블 툰킹](../dotnet/double-thunking-cpp.md)을 참조하십시오.

네이티브에서 MSIL로 이동할 때 작업 집합의 크기가 증가합니다. 이는 공통 언어 런타임이 프로그램이 올바르게 실행되도록 하는 많은 기능을 제공하기 때문입니다. **/clr** 응용 프로그램이 제대로 실행되지 않는 경우 C4793(기본적으로 꺼져 있음)을 사용하도록 설정하고 자세한 내용은 [컴파일러 경고(수준 1 및 3) C4793을](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md) 참조할 수 있습니다.

### <a name="program-crashes-on-shutdown"></a>종료 시 프로그램 충돌

경우에 따라 관리 코드 실행이 완료되기 전에 CLR이 종료될 수 있습니다. 사용 `std::set_terminate` `SIGTERM` 하 고이 문제를 일으킬 수 있습니다. 자세한 내용은 [신호 상수](../c-runtime-library/signal-constants.md) 및 [set_terminate](../c-runtime-library/abnormal-termination.md) 참조하십시오.

## <a name="using-new-visual-c-features"></a>새로운 비주얼 C++ 기능 사용

응용 프로그램이 컴파일, 링크 및 실행된 후 **/clr로**컴파일된 모든 모듈에서 .NET 기능을 사용할 수 있습니다. 자세한 내용은 [런타임 플랫폼의 구성 요소 확장](../extensions/component-extensions-for-runtime-platforms.md)을 참조하세요.

Visual C++의 .NET 프로그래밍에 대한 자세한 내용은 다음을 참조하십시오.

- [C++/CLI를 갖춘 .NET 프로그래밍(시각적 C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

- [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)

- [런타임 플랫폼용 구성 요소 확장](../extensions/component-extensions-for-runtime-platforms.md)

## <a name="see-also"></a>참고 항목

[혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)
