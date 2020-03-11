---
title: Visual Studio에서 C/C++ DLL 빌드
description: Visual Studio에서를 사용 하 여 C++ dll을 만들고 사용 하는 방법에 대 한 개요입니다.
ms.date: 01/27/2020
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
ms.openlocfilehash: 7083924f137fa9283da40404c7d15183e59c0b1c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78872531"
---
# <a name="create-cc-dlls-in-visual-studio"></a>Visual Studio에서 C/C++ DLL 빌드

Windows에서 DLL (동적 연결 라이브러리)은 함수 및 리소스의 공유 라이브러리 역할을 하는 실행 파일의 일종입니다. 동적 링크는 운영 체제 기능입니다. 이를 통해 실행 파일이 함수를 호출 하거나 별도 파일에 저장 된 리소스를 사용할 수 있습니다. 이러한 함수 및 리소스는 사용하는 실행 파일과 별도로 컴파일 및 배포할 수 있습니다.

DLL은 독립 실행형 실행 파일이 아닙니다. Dll은 호출 하는 응용 프로그램의 컨텍스트에서 실행 됩니다. 운영 체제에서 DLL을 응용 프로그램의 메모리 공간에 로드 합니다. 응용 프로그램이 로드 될 때 (*암시적 링크*) 또는 런타임에 요청 시 (*명시적 링크*) 수행 됩니다. DLL을 통해 실행 파일 간에 함수 및 리소스를 쉽게 공유할 수 있습니다. 즉, 여러 개의 애플리케이션이 메모리에 있는 하나의 DLL 복사본 내용을 동시에 액세스할 수 있습니다.

## <a name="differences-between-dynamic-linking-and-static-linking"></a>동적 링크와 정적 링크의 차이점

정적 링크는 정적 라이브러리의 모든 개체 코드를 빌드할 때이를 사용 하는 실행 파일에 복사 합니다. 동적 링크에는 런타임에 데이터 항목이 나 함수를 포함 하는 DLL을 찾아서 로드 하는 데 필요한 정보만 포함 됩니다. DLL을 만들 때이 정보를 포함 하는 가져오기 라이브러리도 만듭니다. DLL을 호출 하는 실행 파일을 빌드하면 링커에서 가져오기 라이브러리의 내보낸 기호를 사용 하 여 Windows 로더에 대 한 정보를 저장 합니다. 로더가 DLL을 로드 하면 DLL이 응용 프로그램의 메모리 공간에 매핑됩니다. Dll의 특수 `DllMain`함수 (있는 경우)를 호출 하 여 DLL에 필요한 초기화를 수행 합니다.

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>응용 프로그램과 Dll의 차이점

Dll과 응용 프로그램은 모두 실행 가능한 모듈 이지만 여러 가지 면에서 차이가 있습니다. 가장 확실 한 차이점은 DLL을 실행할 수 없다는 것입니다. 시스템의 관점에서 볼 때 응용 프로그램과 Dll 간에는 다음과 같은 두 가지 기본적인 차이점이 있습니다.

- 응용 프로그램은 시스템에서 동시에 여러 인스턴스를 실행할 수 있습니다. DLL에는 하나의 인스턴스만 있을 수 있습니다.

- 응용 프로그램을 프로세스로 로드할 수 있습니다. 스택, 실행 스레드, 전역 메모리, 파일 핸들 및 메시지 큐와 같은 작업을 소유할 수 있습니다. DLL은 이러한 사항을 소유할 수 없습니다.

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>Dll 사용의 이점

코드 및 리소스에 대 한 동적 링크는 정적 링크에 비해 여러 가지 이점을 제공 합니다.

- 동적 링크는 메모리를 절약 하 고 스와핑을 감소 시킵니다. 많은 프로세스에서 DLL을 동시에 사용 하 여 메모리에서 DLL의 읽기 전용 부분에 대 한 단일 복사본을 공유할 수 있습니다. 반면 정적으로 연결 된 라이브러리를 사용 하 여 빌드된 모든 응용 프로그램에는 Windows에서 메모리로 로드 해야 하는 라이브러리 코드의 전체 복사본이 있습니다.

- 동적 링크는 디스크 공간 및 대역폭을 절약 합니다. 많은 응용 프로그램은 디스크에서 DLL의 단일 복사본을 공유할 수 있습니다. 반면 정적 링크 라이브러리를 사용 하 여 빌드한 각 응용 프로그램은 해당 실행 가능 이미지에 연결 된 라이브러리 코드를 포함 합니다. 더 많은 디스크 공간을 사용 하 고 전송 하는 데 더 많은 대역폭을 사용 합니다.

- 유지 관리, 보안 픽스 및 업그레이드를 더 쉽게 수행할 수 있습니다. 응용 프로그램에서 DLL의 일반적인 함수를 사용 하는 경우 버그 수정을 구현 하 고 DLL에 업데이트를 배포할 수 있습니다. Dll이 업데이트 되 면이를 사용 하는 응용 프로그램을 다시 컴파일하거나 다시 연결할 필요가 없습니다. 배포 되는 즉시 새 DLL을 사용할 수 있습니다. 이와 대조적으로 정적으로 연결 된 개체 코드에서 수정 작업을 수행 하는 경우이를 사용 하는 모든 응용 프로그램을 다시 연결 하 고 다시 배포 해야 합니다.

- Ddl을 사용 하 여 출시 후 지원을 제공할 수 있습니다. 예를 들어, 응용 프로그램을 배송할 때 사용할 수 없는 디스플레이를 지원 하도록 디스플레이 드라이버 DLL을 수정할 수 있습니다.

- 명시적 링크를 사용 하 여 런타임에 Dll을 검색 하 고 로드할 수 있습니다. 예를 들어 응용 프로그램 확장은 응용 프로그램을 다시 빌드하거나 다시 배포 하지 않고 새 기능을 앱에 추가 합니다.

- 동적 링크를 사용 하면 다양 한 프로그래밍 언어로 작성 된 응용 프로그램을 쉽게 지원할 수 있습니다. 다른 프로그래밍 언어로 작성 된 프로그램은 프로그램이 함수의 호출 규칙을 따르는 동안 동일한 DLL 함수를 호출할 수 있습니다. 프로그램 및 DLL 함수는 함수에서 인수가 스택에 푸시되는 순서와 같은 방식으로 호환 되어야 합니다. 함수 또는 응용 프로그램이 스택 정리를 담당 하는지 여부입니다. 모든 인수가 레지스터에 전달 되었는지 여부를 나타냅니다.

- 동적 링크는 MFC (Microsoft Foundation Class library) 클래스를 확장 하는 메커니즘을 제공 합니다. 기존 MFC 클래스에서 클래스를 파생 시키고 MFC 응용 프로그램에서 사용할 수 있도록 MFC 확장명 DLL에 배치할 수 있습니다.

- 동적 링크를 사용 하면 응용 프로그램의 국가별 버전을 보다 쉽게 만들 수 있습니다. Dll은 로캘별 리소스를 제공 하는 편리한 방법으로,이를 통해 응용 프로그램의 국가별 버전을 훨씬 쉽게 만들 수 있습니다. 지역화 된 여러 버전의 응용 프로그램을 제공 하는 대신 각 언어의 문자열과 이미지를 별도의 리소스 DLL에 저장할 수 있습니다. 그러면 응용 프로그램에서 런타임에 해당 로캘에 대 한 적절 한 리소스를 로드할 수 있습니다.

Dll을 사용 하면 응용 프로그램이 자체 포함 되지 않기 때문에 잠재적인 단점이 있습니다. 이는 별도의 DLL 모듈이 있는지 여부에 따라 달라 집니다. 하나는 설치의 일부로 배포 하거나 직접 확인 해야 합니다.

## <a name="more-information-on-how-to-create-and-use-dlls"></a>Dll을 만들고 사용 하는 방법에 대 한 자세한 정보

다음 문서는 Visual Studio에서 C/C++ dll을 만드는 방법에 대 한 자세한 정보를 제공 합니다.

[연습: 동적 연결 라이브러리 만들기 및 사용 (C++)](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)\
Visual Studio를 사용하여 DLL을 만들고 사용하는 방법에 대해 설명합니다.

[Dll 종류](kinds-of-dlls.md)\
빌드할 수 있는 다양한 종류의 DLL에 대한 정보를 제공합니다.

[DLL](dll-frequently-asked-questions.md) 에 대 한 질문과 대답\
DLL 관련 질문과 대답을 제공합니다.

[DLL에 실행 파일을 연결](linking-an-executable-to-a-dll.md)\
DLL에 대한 명시적 및 암시적 링크에 대해 설명합니다.

[DLL\ 초기화](run-time-library-behavior.md#initializing-a-dll)
DLL이 로드 될 때 실행 되어야 하는 DLL 초기화 코드에 대해 설명 합니다.

[Dll 및 Visual C++ 런타임 라이브러리 동작](run-time-library-behavior.md)\
런타임 라이브러리 DLL 시작 시퀀스에 대해 설명 합니다.

[LoadLibrary 및 AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)\
`LoadLibrary` 및 `AfxLoadLibrary`를 사용 하 여 런타임에 DLL에 명시적으로 연결 하는 방법을 설명 합니다.

[GetProcAddress](getprocaddress.md)\
`GetProcAddress`를 사용 하 여 DLL의 내보낸 함수 주소를 가져오는 방법을 설명 합니다.

[Freelibrary 및 AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)\
DLL 모듈이 더 이상 필요 하지 않을 때 `FreeLibrary` 및 `AfxFreeLibrary`를 사용 하는 방법을 설명 합니다.

[동적 연결 라이브러리 검색 순서](/windows/win32/Dlls/dynamic-link-library-search-order)\
시스템에서 DLL을 찾기 위해 Windows 운영 체제가 사용하는 검색 경로에 대해 설명합니다.

[Mfc에 동적으로 연결 된 일반 MFC DLL의 모듈 상태](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)\
MFC에 동적으로 연결 되는 기본 MFC DLL의 모듈 상태에 대해 설명 합니다.

[MFC 확장 dll](extension-dlls-overview.md)\
일반적으로 기존 MFC 클래스에서 파생 된 다시 사용할 수 있는 클래스를 구현 하는 Dll에 대해 설명 합니다.

[리소스 전용 DLL을 만드는](creating-a-resource-only-dll.md)\
아이콘, 비트맵, 문자열 및 대화 상자 등의 리소스만 포함된 리소스 전용 DLL에 대해 설명합니다.

[MFC 응용 프로그램의 지역화 된 리소스: 위성 dll](localized-resources-in-mfc-applications-satellite-dlls.md)\
여러 언어로 지역화된 애플리케이션을 만드는 데 도움이 되는 위성 DLL에 대한 향상된 지원을 제공합니다.

\ [가져오기 및 내보내기](importing-and-exporting.md)
DLL에서 함수를 내보내거나 애플리케이션으로 공용 기호를 가져오는 방법에 대해 설명합니다.

[액티브 기술 및 dll](active-technology-and-dlls.md)\
DLL 내에서 개체 서버가 구현될 수 있도록 합니다.

[DLL의 자동화](automation-in-a-dll.md)\
MFC DLL 마법사 지원의 자동화 옵션이 무엇인지 설명합니다.

[MFC dll의 명명 규칙](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)\
MFC에 포함된 DLL 및 라이브러리가 구조적 명명 규칙을 지키는 방법에 대해 설명합니다.

[Visual Basic 응용 프로그램에서 DLL 함수 호출](calling-dll-functions-from-visual-basic-applications.md)\
Visual Basic 애플리케이션에서 DLL 함수를 호출하는 방법에 대해 설명합니다.

## <a name="related-sections"></a>관련 단원

[DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)\
Windows 동적 연결 라이브러리의 일부로 MFC 라이브러리를 사용할 수 있도록 하는 일반적인 MFC Dll에 대해 설명 합니다.

[MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)\
MFC 응용 프로그램 및 MFC 확장명 Dll을 사용 하 여 Mfcxx.dll 및 Mfcxxd.dll (여기서 x는 MFC 버전 번호) 공유 동적 연결 라이브러리를 사용 하는 방법을 설명 합니다.
