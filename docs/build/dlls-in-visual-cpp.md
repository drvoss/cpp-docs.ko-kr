---
title: Visual Studio에서 C/C++ DLL 만들기
description: Visual Studio에서 C++로 DLL을 만들고 사용하는 이유와 방법의 개요입니다.
ms.date: 01/27/2020
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
ms.openlocfilehash: 7083924f137fa9283da40404c7d15183e59c0b1c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422831"
---
# <a name="create-cc-dlls-in-visual-studio"></a>Visual Studio에서 C/C++ DLL 만들기

Windows에서 DLL(동적 연결 라이브러리)은 함수 및 리소스의 공유 라이브러리로 사용되는 일종의 실행 파일입니다. 동적 링크는 운영 체제 기능입니다. 동적 연결을 사용하면 실행 파일이 함수를 호출하거나 별도 파일에 저장된 리소스를 사용할 수 있습니다. 이러한 함수 및 리소스는 사용하는 실행 파일과 별도로 컴파일 및 배포할 수 있습니다.

DLL은 독립 실행형 실행 파일이 아닙니다. DLL은 DLL을 호출하는 애플리케이션의 컨텍스트에서 실행됩니다. 운영 체제는 DLL을 애플리케이션의 메모리 공간에 로드합니다. 이 작업은 애플리케이션이 로드될 때(*암시적 연결*) 또는 런타임에 요청 시(*명시적 연결*) 수행됩니다. DLL을 통해 실행 파일 간에 함수 및 리소스를 쉽게 공유할 수 있습니다. 즉, 여러 개의 애플리케이션이 메모리에 있는 하나의 DLL 복사본 내용을 동시에 액세스할 수 있습니다.

## <a name="differences-between-dynamic-linking-and-static-linking"></a>동적 링크와 정적 링크의 차이점

정적 링크는 정적 라이브러리의 모든 개체 코드를, 빌드될 때 이 코드를 사용하는 실행 파일에 복사합니다. 동적 연결에는 Windows가 런타임에 데이터 항목이나 함수를 포함하는 DLL을 찾아서 로드하는 데 필요한 정보만 포함됩니다. DLL을 만들 때 이 정보를 포함하는 가져오기 라이브러리도 만듭니다. DLL을 호출하는 실행 파일을 빌드하는 경우 링커는 가져오기 라이브러리의 내보낸 기호를 사용하여 Windows 로더를 위해 이 정보를 저장합니다. 로더가 DLL을 로드하면 DLL이 애플리케이션의 메모리 공간에 매핑됩니다. DLL에 특수 함수 `DllMain`이 있는 경우 이 함수는 DLL에 필요한 초기화를 수행하기 위해 호출됩니다.

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>애플리케이션과 DLL의 차이점

DLL과 애플리케이션은 모두 실행 가능한 모듈이지만 여러 가지 면에서 차이가 있습니다. 가장 확실한 차이점은 DLL을 실행할 수 없다는 것입니다. 시스템의 관점에서 볼 때 애플리케이션과 DLL 간에는 다음과 같은 두 가지 기본적인 차이점이 있습니다.

- 애플리케이션에는 시스템에서 동시에 실행되는 자신의 인스턴스가 여러 개 있을 수 있습니다. DLL에는 하나의 인스턴스만 있을 수 있습니다.

- 애플리케이션은 프로세스로 로드할 수 있습니다. 또한 스택, 실행 스레드, 전역 메모리, 파일 핸들 및 메시지 큐와 같은 작업을 소유할 수 있습니다. DLL은 이러한 것들을 소유할 수 없습니다.

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>DLL 사용의 장점

코드 및 리소스에 대한 동적 링크를 사용할 경우, 정적 링크에 비해 다음과 같은 몇 가지 장점이 있습니다.

- 동적 링크를 사용하면 메모리가 절약되고 스와핑이 감소합니다. 여러 프로세스에서 DLL을 동시에 사용하여 메모리에서 DLL의 읽기 전용 부분에 대한 단일 복사본을 공유할 수 있습니다. 반면, 정적으로 연결된 라이브러리를 사용하여 빌드된 모든 애플리케이션에는 Windows에서 메모리로 로드해야 하는 라이브러리 코드의 전체 복사본이 있습니다.

- 동적 링크을 사용하면 디스크 공간 및 대역폭이 절약됩니다. 여러 애플리케이션이 디스크에 있는 DLL의 단일 복사본을 공유할 수 있습니다. 반면, 정적 링크 라이브러리를 사용하여 빌드된 각 애플리케이션에는 실행 가능 이미지로 연결된 라이브러리 코드가 있습니다. 이 코드는 더 많은 디스크 공간을 사용하고 전송될 때 더 많은 대역폭을 사용합니다.

- 유지 관리, 보안 수정 및 업그레이드를 더 쉽게 수행할 수 있습니다. 애플리케이션에서 DLL의 일반 함수를 사용하는 경우 버그 수정을 구현하고 DLL에 업데이트를 배포할 수 있습니다. DLL이 업데이트되었다면 이 DLL을 사용하는 애플리케이션을 다시 컴파일하거나 연결할 필요가 없습니다. 이 애플리케이션은 새 DLL이 배포되자마자 즉시 사용할 수 있습니다. 반면, 정적으로 연결된 개체 코드에서 수정하는 경우 이를 사용하는 모든 애플리케이션을 다시 연결하고 배포해야 합니다.

- DLL을 사용하여 출시 후 지원을 제공할 수 있습니다. 예를 들어 애플리케이션이 배송되었을 때는 사용할 수 없었던 디스플레이를 지원하도록 디스플레이 드라이버 DLL을 수정할 수 있습니다.

- 명시적 링크를 사용하여 런타임에 DLL을 검색하고 로드할 수 있습니다. 앱을 다시 빌드하거나 배포하지 않고 새 기능을 앱에 추가하는 애플리케이션 확장을 예로 들 수 있습니다.

- 동적 링크를 사용하면 다양한 프로그래밍 언어로 작성된 애플리케이션을 쉽게 지원할 수 있습니다. 다양한 프로그래밍 언어로 작성된 프로그램은 프로그램이 함수의 호출 규칙을 따르는 한 동일한 DLL 함수를 호출할 수 있습니다. 이 프로그램과 DLL 함수는 다음과 같은 방식으로 호환되어야 합니다. 인수가 스택에 푸시될 때 따를 것으로 함수가 예상하는 순서. 함수 또는 애플리케이션이 스택 정리를 담당하는지 여부. 그리고 모든 인수가 레지스터에 전달되는지 여부.

- 동적 링크는 MFC(Microsoft Foundation Class) 라이브러리 클래스를 확장하는 메커니즘을 제공합니다. 기존 MFC 클래스에서 클래스를 파생시켜 MFC 애플리케이션에서 사용할 수 있도록 MFC 확장 DLL에 배치할 수 있습니다.

- 동적 링크를 사용하면 애플리케이션의 국제 버전을 더 쉽게 만들 수 있습니다. DLL은 로캘별 리소스를 편리하게 제공할 수 있는 방법으로, 이를 통해 애플리케이션의 국제 버전을 훨씬 더 쉽게 만들 수 있습니다. 애플리케이션의 지역화 버전을 여러 개 제공하는 대신 각 언어의 문자열과 이미지를 별도의 리소스 DLL에 배치할 수 있습니다. 그러면 애플리케이션에서 런타임에 해당 로캘에 적절한 리소스를 로드할 수 있습니다.

DLL 사용 시 있을 수 있는 단점은 애플리케이션이 자체 포함되어 있지 않다는 것입니다. 이는 설치 과정의 일부로 자신을 배포하거나 확인해야 하는 별도의 DLL 모듈이 있는지 여부에 따라 달라집니다.

## <a name="more-information-on-how-to-create-and-use-dlls"></a>DLL을 만들고 사용하는 방법에 관한 추가 정보

다음 문서에서는 Visual Studio에서 C/C++ DLL을 만드는 방법에 관한 자세한 정보를 제공합니다.

[연습: 동적 연결 라이브러리 만들기 및 사용(C++)](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)\
Visual Studio를 사용하여 DLL을 만들고 사용하는 방법에 대해 설명합니다.

[DLL의 종류](kinds-of-dlls.md)\
빌드할 수 있는 다양한 종류의 DLL에 대한 정보를 제공합니다.

[DLL 관련 질문과 대답](dll-frequently-asked-questions.md)\
DLL 관련 질문과 대답을 제공합니다.

[DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md)\
DLL에 대한 명시적 및 암시적 링크에 대해 설명합니다.

[DLL 초기화](run-time-library-behavior.md#initializing-a-dll)\
DLL이 로드될 때 실행되어야 하는 메모리 DLL 초기화 코드에 대해 설명합니다.

[DLL 및 Visual C++ 런타임 라이브러리 동작](run-time-library-behavior.md)\
런타임 라이브러리 DLL 시작 시퀀스를 설명합니다.

[LoadLibrary 및 AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)\
`LoadLibrary` 및 `AfxLoadLibrary`를 사용하여 런타임에 명시적으로 DLL에 연결하는 방법을 설명합니다.

[GetProcAddress](getprocaddress.md)\
`GetProcAddress`를 사용하여 DLL에 있는 내보낸 함수의 주소를 얻는 방법에 대해 설명합니다.

[FreeLibrary 및 AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)\
DLL 모듈이 더 이상 필요하지 않을 경우의 `FreeLibrary` 및 `AfxFreeLibrary` 사용에 대해 설명합니다.

[동적 연결 라이브러리 검색 순서](/windows/win32/Dlls/dynamic-link-library-search-order)\
시스템에서 DLL을 찾기 위해 Windows 운영 체제가 사용하는 검색 경로에 대해 설명합니다.

[동적으로 MFC에 연결된 기본 MFC DLL의 모듈 상태](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)\
MFC에 동적으로 연결된 기본 MFC DLL의 모듈 상태에 대해 설명합니다.

[MFC 확장 DLL](extension-dlls-overview.md)\
기존 MFC 클래스에서 파생된 다시 사용할 수 있는 클래스를 일반적으로 구현하는 DLL에 대해 설명합니다.

[리소스 전용 DLL 만들기](creating-a-resource-only-dll.md)\
아이콘, 비트맵, 문자열 및 대화 상자 등의 리소스만 포함된 리소스 전용 DLL에 대해 설명합니다.

[MFC 애플리케이션의 지역화된 리소스: 위성 DLL](localized-resources-in-mfc-applications-satellite-dlls.md)\
여러 언어로 지역화된 애플리케이션을 만드는 데 도움이 되는 위성 DLL에 대한 향상된 지원을 제공합니다.

[가져오기 및 내보내기](importing-and-exporting.md)\
DLL에서 함수를 내보내거나 애플리케이션으로 공용 기호를 가져오는 방법에 대해 설명합니다.

[액티브 기술 및 DLL](active-technology-and-dlls.md)\
DLL 내에서 개체 서버가 구현될 수 있도록 합니다.

[DLL의 자동화](automation-in-a-dll.md)\
MFC DLL 마법사 지원의 자동화 옵션이 무엇인지 설명합니다.

[MFC DLL의 명명 규칙](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)\
MFC에 포함된 DLL 및 라이브러리가 구조적 명명 규칙을 지키는 방법에 대해 설명합니다.

[Visual Basic 애플리케이션에서 DLL 함수 호출](calling-dll-functions-from-visual-basic-applications.md)\
Visual Basic 애플리케이션에서 DLL 함수를 호출하는 방법에 대해 설명합니다.

## <a name="related-sections"></a>관련 단원

[DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)\
Windows 동적 연결 라이브러리의 일부로 MFC 라이브러리를 사용할 수 있게 하는 기본 MFC DLL에 대해 설명합니다.

[MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)\
MFC 애플리케이션 및 MFC 확장 DLL과 함께 MFCxx.dll 및 MFCxxD.dll(여기서 x는 MFC 버전 번호) 공유 동적 연결 라이브러리를 사용하는 방법에 대해 설명합니다.
