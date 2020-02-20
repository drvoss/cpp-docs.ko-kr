---
title: DLL 종류
ms.date: 05/06/2019
helpviewer_keywords:
- MFC DLLs [C++], types
- DLLs [C++], types
- DLLs [C++], MFC
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
ms.openlocfilehash: 9e66fa1c24ea00961d99eef02c15526eff4eb533
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221483"
---
# <a name="kinds-of-dlls"></a>DLL 종류

이 항목에서는 빌드할 DLL의 종류를 결정 하는 데 유용한 정보를 제공 합니다.

##  <a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a> 사용 가능한 Dll의 종류

Visual Studio를 사용하면 MFC (Microsoft Foundation Class) 라이브러리를 사용하지 않는 C 또는 C++에서 Win32 DLL을 빌드 할 수 있습니다. Win32 응용 프로그램 마법사를 사용하여 비 MFC DLL 프로젝트를 만들 수 있습니다.

MFC 라이브러리 자체는 정적 링크 라이브러리나 여러 DLL에서 MFC DLL 마법사와 함께 사용할 수 있습니다. DLL이 MFC를 사용하는 경우 Visual Studio는 세 가지 DLL 개발 시나리오를 지원합니다.

- MFC를 정적으로 연결하는 일반 MFC DLL 작성

- MFC를 동적으로 연결하는 일반 MFC DLL 작성

- 항상 동적으로 MFC를 연결하는 MFC 확장 DLL 작성

### <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [비 MFC DLL: 개요](non-mfc-dlls-overview.md)

- [정적으로 MFC에 링크 된 기본 MFC Dll](regular-dlls-statically-linked-to-mfc.md)

- [동적으로 MFC에 링크 된 기본 MFC Dll](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 확장명 DLL: 개요](extension-dlls-overview.md)

- [사용할 DLL 종류 결정](#_core_which_kind_of_dll_to_use)

##  <a name="_core_which_kind_of_dll_to_use"></a> 사용할 DLL 종류 결정

DLL에서 MFC를 사용 하지 않는 경우 비 MFC Win32 DLL을 빌드하려면 Visual Studio를 사용 합니다. 중요 한 디스크 공간 및 메모리를 소모 (정적 또는 동적) DLL을 MFC에 링크 합니다. DLL이 실제로 MFC를 사용 하지 않는 한 MFC에 링크 하지 말아야 합니다.

DLL은 MFC를 사용하고 MFC 또는 비 MFC 응용 프로그램에서 사용할 경우에 동적으로 MFC에 링크 된 기본 MFC DLL 또는 정적으로 MFC에 링크 된 기본 MFC DLL을 빌드해야 합니다. 대부분의 경우에서 아마도 하려는 DLL의 파일 크기가 훨씬 작아집니다 함으로써 공유 버전의 MFC 사용하여 메모리 부담도 상당히 클 수 있으므로 동적으로 MFC에 링크 되는 기본 MFC DLL을 사용 합니다. 정적으로 MFC에 링크 하면 DLL의 파일 크기가 더 큰 되며 MFC 라이브러리 코드의 고유한 개인 복사본이 로드 되므로 잠재적으로 추가 메모리를 차지 합니다.

동적으로 MFC에 링크 한 DLL은 MFC를 직접 링크할 필요가 없기 때문에 정적으로 MFC에 링크 한 DLL 보다 빠르게 빌드할 수 있습니다. 링커가 디버그 정보를 압축 해야 합니다는 디버그 빌드에서 특히 그렇습니다. 디버그 정보가 이미 들어 있는 dll에 링크 하 여 DLL 내에 압축 해야 할 디버그 정보가 줄어듭니다 있습니다.

동적으로 MFC에 링크 한 단점은 공유 Dll Mfcx0.dll 및 Msvcrxx.dll (또는 유사한 파일) DLL과 함께 배포 해야 합니다는 것입니다. MFC Dll은 재배포할 수 있지만 여전히 설치 프로그램에서 Dll를 설치 해야 합니다. 또한 한 Msvcrxx.dll을 둘 다 프로그램과 MFC Dll에서 사용 되는 C 런타임 라이브러리가 포함를 발송 해야 합니다.

DLL을 MFC 실행 파일만 사용 하는 경우 기본 MFC DLL 또는 MFC 확장 DLL 빌드 중에서 선택을 해야 합니다. 기존의 MFC 클래스에서 파생 된 다시 사용할 수 있는 클래스를 구현 하는 DLL 또는 응용 프로그램과 DLL 간에 MFC 파생 개체를 전달 해야 하는 경우에 MFC 확장 DLL을 빌드해야 합니다.

DLL 동적으로 MFC에 링크 하는 경우 DLL을 사용하여 MFC Dll은 재배포할 수 있습니다. 이 아키텍처는 디스크 공간을 절약 하 고 메모리 사용량을 최소화 하는 여러 실행 파일 간에 클래스 라이브러리를 공유 하는 데 특히 유용 합니다.

### <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [비 MFC DLL: 개요](non-mfc-dlls-overview.md)

- [정적으로 MFC에 링크 된 기본 MFC Dll](regular-dlls-statically-linked-to-mfc.md)

- [동적으로 MFC에 링크 된 기본 MFC Dll](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 확장명 DLL: 개요](extension-dlls-overview.md)

## <a name="see-also"></a>참고자료

[C를 만들기 /C++ Visual Studio에서 Dll](dlls-in-visual-cpp.md)
