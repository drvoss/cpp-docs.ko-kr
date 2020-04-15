---
title: MFC 모듈의 상태 데이터 관리
ms.date: 11/19/2018
helpviewer_keywords:
- global state [MFC]
- data management [MFC], MFC modules
- window procedure entry points [MFC]
- exported interfaces and global state [MFC]
- module states [MFC], saving and restoring
- data management [MFC]
- MFC, managing state data
- multiple modules [MFC]
- module state restored [MFC]
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
ms.openlocfilehash: c8e79f54ed586201a7d82327662643a9a241b8f4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357274"
---
# <a name="managing-the-state-data-of-mfc-modules"></a>MFC 모듈의 상태 데이터 관리

이 문서에서는 MFC 모듈의 상태 데이터와 실행 흐름(경로 코드가 실행 시 응용 프로그램을 통해 소요됨)이 모듈에 들어오고 나갈 때 이 상태가 업데이트되는 방법에 대해 설명합니다. AFX_MANAGE_STATE 및 METHOD_PROLOGUE 매크로로 모듈 상태를 전환하는 것도 논의됩니다.

> [!NOTE]
> 여기서 "모듈"이라는 용어는 실행 가능한 프로그램 또는 응용 프로그램의 나머지 부분과 독립적으로 작동하지만 MFC DLL의 공유 복사본을 사용하는 DLL(또는 DLL 집합)을 의미합니다. ActiveX 컨트롤은 모듈의 일반적인 예입니다.

다음 그림과 같이 MFC에는 응용 프로그램에 사용되는 각 모듈에 대한 상태 데이터가 있습니다. 이 데이터의 예로는 Windows 인스턴스 핸들(리소스 로드에 사용됨), `CWinApp` `CWinThread` 응용 프로그램의 현재 및 개체에 대한 포인터, OLE 모듈 참조 수, Windows 개체 핸들과 MFC 개체의 해당 인스턴스 간의 연결을 유지하는 다양한 맵이 있습니다. 그러나 응용 프로그램이 여러 모듈을 사용하는 경우 각 모듈의 상태 데이터는 응용 프로그램 전체가 아닙니다. 대신 각 모듈에는 MFC 상태 데이터의 자체 개인 복사본이 있습니다.

![단일 모듈 의 상태 데이터 &#40;응용 프로그램&#41;](../mfc/media/vc387n1.gif "단일 모듈 의 상태 데이터 &#40;응용 프로그램&#41;") <br/>
단일 모듈(애플리케이션)의 상태 데이터

모듈의 상태 데이터는 구조에 포함되며 해당 구조에 대한 포인터를 통해 항상 사용할 수 있습니다. 다음 그림과 같이 실행 흐름이 특정 모듈에 들어가면 해당 모듈의 상태가 "현재" 또는 "유효" 상태여야 합니다. 따라서 각 스레드 개체에는 해당 응용 프로그램의 유효 상태 구조에 대한 포인터가 있습니다. 이 포인터를 항상 업데이트하는 것은 응용 프로그램의 전역 상태를 관리하고 각 모듈의 상태의 무결성을 유지하는 데 중요합니다. 전역 상태를 잘못 관리하면 예기치 않은 응용 프로그램 동작이 발생할 수 있습니다.

![여러 모듈의 상태 데이터](../mfc/media/vc387n2.gif "여러 모듈 상태 데이터") <br/>
여러 모듈의 상태 데이터

즉, 각 모듈은 모든 진입점에서 모듈 상태 간에 올바르게 전환할 책임이 있습니다. "진입점"은 실행 흐름이 모듈의 코드를 입력할 수 있는 모든 위치입니다. 진입점은 다음과 같습니다.

- [DLL에서 내보낸 함수](../mfc/exported-dll-function-entry-points.md)

- [COM 인터페이스의 멤버 기능](../mfc/com-interface-entry-points.md)

- [창 절차](../mfc/window-procedure-entry-points.md)

## <a name="see-also"></a>참고 항목

[일반 MFC 항목](../mfc/general-mfc-topics.md)
