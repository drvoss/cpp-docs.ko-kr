---
title: 정적 라이브러리(C++/CX)
ms.date: 02/03/2017
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
ms.openlocfilehash: 3c4bfd28b805903a2e596ef6d648ff31b0b8261c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358105"
---
# <a name="static-libraries-ccx"></a>정적 라이브러리(C++/CX)

유니버설 Windows 플랫폼(UWP) 앱에서 사용되는 정적 라이브러리에는 STL 유형을 비롯한 ISO 표준 C++ 코드와 Windows 런타임 앱 플랫폼에서 제외되지 않은 Win32 API를 호출할 수 있습니다. 정적 라이브러리는 Windows 런타임 구성 요소를 사용하고 특정 제한 사항이 있는 Windows 런타임 구성 요소를 만들 수 있습니다.

## <a name="creating-static-libraries"></a>정적 라이브러리 만들기

새 프로젝트를 만드는 방법은 설치한 Visual Studio 버전에 따라 다릅니다. 선호하는 버전의 Visual Studio에 대한 설명서를 보려면 **버전** 선택기 컨트롤을 사용합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker range="vs-2019"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2019"></a>Visual Studio 2019에서 UWP 정적 라이브러리를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트 만들기** 대화 상자를 엽니다.

1. 대화 상자 맨 위에 **있는 언어를** **C++로**설정하고 **플랫폼을** **Windows로**설정하고 **프로젝트 유형을** **UWP로**설정합니다.

1. 필터링된 프로젝트 유형 목록에서 **정적 라이브러리(유니버설 윈도우 - C++/CX)를** 선택한 다음 **다음**을 선택합니다. 다음 페이지에서 프로젝트에 이름을 지정하고 원하는 경우 프로젝트 위치를 지정합니다.

1. **만들기** 단추를 선택하여 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2017-or-visual-studio-2015"></a>Visual Studio 2017 또는 Visual Studio 2015에서 UWP 정적 라이브러리를 만들려면

1. 메뉴 모음에서**새** > **프로젝트** **파일** > 을 선택합니다. **비주얼 C ++** > **윈도우 유니버설** 에서 정적 **라이브러리 (유니버설 윈도우)를**선택합니다.

1. **솔루션 탐색기에서**프로젝트의 바로 가기 메뉴를 열고 **속성을**선택합니다. **속성** 대화 상자에서 구성 **속성** > **C/C++** 페이지에서 **Windows 런타임 확장 사용(예)을** 설정합니다. **Yes (/ZW)**

::: moniker-end

새 정적 라이브러리를 컴파일할 때 UWP 앱에 대해 제외된 Win32 API를 호출하면 컴파일러에서 "식별자를 찾을 수 없습니다"라는 오류 C3861이 발생합니다. Windows 런타임에 지원되는 대체 방법을 찾으려면 [UWP 앱의 Windows API](/uwp/win32-and-com/alternatives-to-windows-apis-uwp)대체 를 참조하십시오.

UWP 앱 솔루션에 C++ 정적 라이브러리 프로젝트를 추가하는 경우 UWP 지원 속성이 **예로**설정되도록 라이브러리 프로젝트의 속성 설정을 업데이트해야 할 수 있습니다. 이 설정이 없으면 코드가 빌드되고 링크되지만 Microsoft Store용 앱을 확인하려고 할 때 오류가 발생합니다. 정적 lib는 해당 lib를 사용하는 프로젝트와 동일한 컴파일러 설정을 사용하여 컴파일해야 합니다.

public `ref` 클래스, 공용 인터페이스 클래스 또는 공용 값 클래스를 만드는 정적 라이브러리를 사용하면 링커가 다음과 같은 경고를 발생시킵니다.

> **경고 LNK4264:** /ZW로 컴파일된 개체 파일을 정적 라이브러리에 보관합니다. Windows 런타임 유형을 작성할 때는 Windows 런타임 메타데이터가 포함된 정적 라이브러리와 연결하지 않는 것이 좋습니다.

정적 라이브러리가 라이브러리 자체 외부에서 사용되는 Windows 런타임 구성 요소를 생성하지 않는 경우에만 경고를 무시해도 안전합니다. 라이브러리에 정의된 구성 요소가 라이브러리에 사용되지 않는 경우 링커는 공용 메타 데이터에 형식 정보가 있는 경우에도 구현을 최적화할 수 있습니다. 즉, 정적 라이브러리의 공용 구성 요소는 컴파일되지만 런타임에 활성화되지 않습니다. 이러한 이유로 다른 구성 요소 나 앱에서 사용하기위한 Windows 런타임 구성 요소는 동적 링크 라이브러리 (DLL)에서 구현해야합니다.

## <a name="see-also"></a>참고 항목

[스레딩 및 마샬링](../cppcx/threading-and-marshaling-c-cx.md)
