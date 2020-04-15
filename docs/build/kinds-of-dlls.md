---
title: DLL 종류
ms.date: 05/06/2019
helpviewer_keywords:
- MFC DLLs [C++], types
- DLLs [C++], types
- DLLs [C++], MFC
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
ms.openlocfilehash: dae44d2dd39597420ce2a2c4e1642e8a7f0784e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328497"
---
# <a name="kinds-of-dlls"></a>DLL 종류

이 항목에서는 빌드할 DLL의 종류를 결정하는 데 도움이 되는 정보를 제공합니다.

## <a name="different-kinds-of-dlls-available"></a><a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a>다양한 종류의 DLL 사용 가능

Visual Studio를 사용하여 Microsoft 파운데이션 클래스(MFC) 라이브러리를 사용하지 않는 C 또는 C++에서 Win32 DLL을 빌드할 수 있습니다. Win32 응용 프로그램 마법사를 사용하여 MFC가 아닌 DLL 프로젝트를 만들 수 있습니다.

MFC 라이브러리 자체는 정적 링크 라이브러리 또는 MFC DLL 마법사를 사용 하 고 여러 DLL에서 사용할 수 있습니다. DLL이 MFC를 사용하는 경우 Visual Studio는 세 가지 다른 DLL 개발 시나리오를 지원합니다.

- MFC를 정적으로 연결하는 일반 MFC DLL 구축

- MFC를 동적으로 연결하는 일반 MFC DLL 구축

- 항상 동적으로 MFC를 연결하는 MFC 확장 DLL 구축

### <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [비 MFC DLL: 개요](non-mfc-dlls-overview.md)

- [정적으로 MFC에 링크된 기본 MFC DLL](regular-dlls-statically-linked-to-mfc.md)

- [동적으로 MFC에 링크된 기본 MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 확장명 DLL: 개요](extension-dlls-overview.md)

- [사용할 DLL 종류](#_core_which_kind_of_dll_to_use)

## <a name="deciding-which-kind-of-dll-to-use"></a><a name="_core_which_kind_of_dll_to_use"></a>사용할 DLL 종류 결정

DLL에서 MFC를 사용하지 않는 경우 Visual Studio를 사용하여 MFC가 아닌 Win32 DLL을 빌드합니다. DLL을 MFC에 연결하면 디스크 공간과 메모리가 크게 소요됩니다. DLL이 실제로 MFC를 사용하지 않는 한 MFC에 연결해서는 안 됩니다.

DLL이 MFC를 사용하고 MFC 또는 비 MFC 응용 프로그램에서 사용되는 경우 MFC에 동적으로 연결되는 일반 MFC DLL 또는 MFC에 정적으로 연결되는 일반 MFC DLL을 빌드해야 합니다. 대부분의 경우 DLL의 파일 크기가 훨씬 작아지고 MFC의 공유 버전을 사용하는 메모리의 절감이 중요할 수 있으므로 MFC에 동적으로 연결되는 일반 MFC DLL을 사용하려고 할 수 있습니다. MFC에 정적으로 링크하는 경우 DLL의 파일 크기가 커지며 MFC 라이브러리 코드의 자체 개인 복사본을 로드하기 때문에 추가 메모리가 차지할 수 있습니다.

MFC에 동적으로 연결되는 DLL을 빌드하는 것은 MFC 자체를 연결할 필요가 없기 때문에 MFC에 정적으로 연결되는 DLL을 빌드하는 것보다 빠릅니다. 이는 링커가 디버그 정보를 압축해야 하는 디버그 빌드에서 특히 그렇습니다. 디버그 정보가 이미 포함된 DLL과 연결하면 DLL 내에서 압축할 디버그 정보가 줄어듭니다.

MFC에 동적으로 연결하는 한 가지 단점은 공유 DLL Mfcx0.dll 및 Msvcrxx.dll(또는 유사한 파일)을 DLL에 배포해야 한다는 것입니다. MFC DLL은 자유롭게 재배포할 수 있지만 설치 프로그램에 DLL을 설치해야 합니다. 또한 프로그램과 MFC DLL 자체에서 모두 사용되는 C 런타임 라이브러리가 포함된 Msvcrxx.dll을 제공해야 합니다.

DLL이 MFC 실행 파일을 통해서만 사용되는 경우 일반 MFC DLL 또는 MFC 확장 DLL 을 빌드할지 선택할 수 있습니다. DLL이 기존 MFC 클래스에서 파생된 재사용 가능한 클래스를 구현하거나 응용 프로그램과 DLL 간에 MFC 파생 개체를 전달해야 하는 경우 MFC 확장 DLL을 빌드해야 합니다.

DLL이 MFC에 동적으로 링크되는 경우 MFC DLL이 DLL과 함께 재분배될 수 있습니다. 이 아키텍처는 디스크 공간을 절약하고 메모리 사용량을 최소화하기 위해 여러 실행 파일 간에 클래스 라이브러리를 공유하는 데 특히 유용합니다.

### <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [비 MFC DLL: 개요](non-mfc-dlls-overview.md)

- [정적으로 MFC에 링크된 기본 MFC DLL](regular-dlls-statically-linked-to-mfc.md)

- [동적으로 MFC에 링크된 기본 MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 확장명 DLL: 개요](extension-dlls-overview.md)

## <a name="see-also"></a>참고 항목

[Visual Studio에서 C/C++ DLL 만들기](dlls-in-visual-cpp.md)
