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

이 구성은 현재에 대한 포인터와 같은 MFC 글로벌 데이터와 관련 하 여 문제가 발생 `CWinApp` 개체 및 핸들 맵.

MFC 버전 4.0 하기 전에이 전역 데이터 자체는 MFC DLL 내에 상주하고 프로세스의 모든 모듈에 의해 공유 되었습니다. Win32 DLL을 사용 하 여 각 프로세스는 DLL의 데이터의 자체 복사본을 가져옵니다, 때문에이 구성표 프로세스별 데이터를 추적 하는 쉬운 방법을 제공 합니다. 또한 AFXDLL 모델 것으로 가정 하 있습니다 하나만 `CWinApp` 개체 및 하나의 처리 프로세스의 맵, MFC DLL에서 이러한 항목을 추적할 수 있습니다.

그러나 MFC DLL에 대한 기본 MFC DLL을 동적으로 연결 하는 기능을 이제 두 개 이상 가질 수 `CWinApp` 프로세스에서 개체-및 핸들 맵도 두 개 이상의 집합입니다. 어떻게는 MFC 기록해 사용 해야 하는 시나리오?

솔루션 (응용 프로그램 또는 기본 MFC DLL) 각 모듈 사본이이 전역 상태 정보를 제공 하는 것입니다. 따라서 호출 **AfxGetApp** 일반적인 MFC DLL에 대한 포인터를 반환 합니다.는 `CWinApp` 실행 파일이 있는 DLL의 개체입니다. 이 모듈별 복사 MFC 글로벌 데이터의 모듈 상태 라고 하에 설명 되어 [MFC 기술 참고 58](../mfc/tn058-mfc-module-state-implementation.md)합니다.

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
