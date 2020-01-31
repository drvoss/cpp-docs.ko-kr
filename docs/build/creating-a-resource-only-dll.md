---
title: 리소스 전용 DLL 만들기
description: Visual Studio에서 리소스 전용 DLL을 만드는 방법
ms.date: 01/27/2020
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
no-loc:
- noentry
ms.openlocfilehash: ef79de77e35cbef6acd4af1cec82a4edc1b7d105
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821345"
---
# <a name="creating-a-resource-only-dll"></a>리소스 전용 DLL 만들기

리소스 전용 DLL은 아이콘, 비트맵, 문자열 및 대화 상자와 같은 리소스가 없지만 리소스를 포함 하는 DLL입니다. 리소스 전용 DLL을 사용 하는 것은 여러 프로그램에서 동일한 리소스 집합을 공유 하는 좋은 방법입니다. 여러 언어로 지역화 된 리소스를 응용 프로그램에 제공 하는 것도 좋은 방법입니다. 자세한 내용은 [MFC 응용 프로그램의 지역화 된 리소스: 위성 dll](localized-resources-in-mfc-applications-satellite-dlls.md)을 참조 하세요.

## <a name="create-a-resource-only-dll"></a>리소스 전용 DLL 만들기

리소스 전용 DLL을 만들려면 새 Windows DLL (비 MFC) 프로젝트를 만들고 프로젝트에 리소스를 추가 합니다.

::: moniker range="vs-2015"

1. **새 프로젝트** 대화 상자에서 **Win32 프로젝트** 를 선택 합니다. 프로젝트 및 솔루션 이름을 입력 하 고 **확인**을 선택 합니다.

1. **Win32 응용 프로그램 마법사**에서 **응용 프로그램 설정**을 선택 합니다. **DLL**의 **응용 프로그램 유형을** 선택 합니다. **추가 옵션**에서 **빈 프로젝트**를 선택합니다. **마침** 을 선택 하 여 프로젝트를 만듭니다.

1. DLL에 대 한 리소스 (예: 문자열 또는 메뉴)를 포함 하는 새 리소스 스크립트를 만듭니다. `.rc` 파일을 저장 합니다.

1. **프로젝트** 메뉴에서 **기존 항목 추가**를 선택한 다음 새 `.rc` 파일을 프로젝트에 삽입 합니다.

1. [/NOENTRY](reference/noentry-no-entry-point.md) 링커 옵션을 지정 합니다. `/NOENTRY` 링커에서는 `_main`에 대 한 참조를 DLL에 연결할 수 없습니다. 리소스 전용 DLL을 만들려면이 옵션을 선택 해야 합니다.

1. DLL을 빌드합니다.

::: moniker-end
::: moniker range=">=vs-2017"

1. **새 프로젝트** 대화 상자에서 **Windows 데스크톱 마법사** 를 선택 하 고 **다음**을 선택 합니다. **새 프로젝트 구성** 페이지에서 프로젝트 및 솔루션 이름을 입력 하 고 **만들기**를 선택 합니다.

1. **Windows 데스크톱 프로젝트** 대화 상자에서 **동적 연결 라이브러리**의 **응용 프로그램 유형을** 선택 합니다. **추가 옵션**에서 **빈 프로젝트**를 선택합니다. **확인** 을 선택 하 여 프로젝트를 만듭니다.

1. DLL에 대 한 리소스 (예: 문자열 또는 메뉴)를 포함 하는 새 리소스 스크립트를 만듭니다. `.rc` 파일을 저장 합니다.

1. **프로젝트** 메뉴에서 **기존 항목 추가**를 선택한 다음 새 `.rc` 파일을 프로젝트에 삽입 합니다.

1. [/NOENTRY](reference/noentry-no-entry-point.md) 링커 옵션을 지정 합니다. `/NOENTRY` 링커에서는 `_main`에 대 한 참조를 DLL에 연결할 수 없습니다. 리소스 전용 DLL을 만들려면이 옵션을 선택 해야 합니다.

1. DLL을 빌드합니다.

::: moniker-end

## <a name="use-a-resource-only-dll"></a>리소스 전용 DLL 사용

리소스 전용 DLL을 사용 하는 응용 프로그램은 [LoadLibraryEx](loadlibrary-and-afxloadlibrary.md) 또는 관련 함수를 호출 하 여 dll에 명시적으로 연결 해야 합니다. 리소스에 액세스 하려면 `FindResource` 제네릭 함수를 호출 하 고 모든 종류의 리소스에서 작동 하는 `LoadResource`합니다. 또는 다음과 같은 리소스 특정 함수 중 하나를 호출 합니다.

- `FormatMessage`

- `LoadAccelerators`

- `LoadBitmap`

- `LoadCursor`

- `LoadIcon`

- `LoadMenu`

- `LoadString`

응용 프로그램은 리소스 사용을 마친 후 `FreeLibrary`를 호출 해야 합니다.

## <a name="see-also"></a>참조

[리소스 파일 작업](../windows/working-with-resource-files.md)\
[Visual Studio에서 C/C++ DLL 만들기](dlls-in-visual-cpp.md)
