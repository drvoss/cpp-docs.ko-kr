---
title: 동적으로 MFC에 링크 된 기본 MFC DLL의 모듈 상태
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- module states [C++]
- MFC DLLs [C++], regular MFC DLLs
- module states [C++], regular MFC DLLs dynamically linked to
- DLLs [C++], module states
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
ms.openlocfilehash: cedce676f5586369446c9856fd33e4d16c237b27
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220586"
---
# <a name="module-states-of-a-regular-mfc-dll-dynamically-linked-to-mfc"></a>동적으로 MFC에 링크 된 기본 MFC DLL의 모듈 상태

동적으로 MFC DLL 일반 MFC DLL에 연결 하는 기능을 사용 하면 매우 복잡 한 일부 구성 합니다. 예를 들어, 기본 MFC DLL을 사용 하는 실행 파일 수 모두 동적으로 링크할 MFC DLL을 MFC 확장 Dll.

이 구성은 현재 `CWinApp` 개체에 대한 포인터 및 핸들 맵과 같은 MFC 전역 데이터와 관련하여 문제를 일으킵니다.

MFC 버전 4.0 이전에는 이 전역 데이터가 MFC DLL 자체에 있었고 프로세스의 모든 모듈에서 공유했습니다. Win32 DLL을 사용하는 각 프로세스는 DLL 데이터의 자체 복사본을 가져오므로 이 체계는 프로세스별 데이터를 쉽게 추적할 수 있는 방법을 제공했습니다. 또한 AFXDLL 모델에서는 프로세스에 `CWinApp` 개체가 하나만 있고 핸들 맵 집합이 하나만 있다고 가정했으므로 이러한 항목은 MFC DLL 자체에서 추적할 수 있습니다.

그러나 일반 MFC DLL을 MFC DLL에 동적으로 연결하는 기능을 통해 프로세스에 둘 이상의 `CWinApp` 개체와 둘 이상의 핸들 맵을 가질 수 있습니다. MFC는 어떤 것을 사용해야 하는지 어떻게 추적할 수 있을까요?

해결책은 각 모듈(응용 프로그램 또는 일반 MFC DLL)에 이 전역 상태 정보의 고유한 사본을 제공하는 것입니다. 따라서 일반 MFC DLL에서 **AfxGetApp**을 호출하면 실행 파일이 아닌 DLL의 `CWinApp` 개체에 대한 포인터가 반환됩니다. MFC 전역 데이터의 모듈별 복사본은 모듈 상태라고 하며 [MFC 기술 참고 58](../mfc/tn058-mfc-module-state-implementation.md)에 설명되어 있습니다.

MFC 공용 창 프로시저 기본 MFC DLL에서 구현 된 모든 메시지 처리기에서 걱정할 필요가 올바른 모듈 상태로 자동 전환 됩니다. 하지만를 명시적으로 DLL에 대한에 현재 모듈 상태를 설정 해야 실행 파일의 기본 MFC DLL를 호출 합니다. 이 작업을 수행 하려면 사용 합니다 **AFX_MANAGE_STATE** DLL에서 내보낸 모든 함수에는 매크로입니다. DLL에서 내보낸 함수 시작 부분에 다음 코드 줄을 추가 하면 됩니다.

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [MFC 모듈 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)

- [동적으로 MFC에 링크 된 기본 MFC Dll](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 확장명 DLL](extension-dlls-overview.md)

## <a name="see-also"></a>참고자료

[C를 만들기 /C++ Visual Studio에서 Dll](dlls-in-visual-cpp.md)
