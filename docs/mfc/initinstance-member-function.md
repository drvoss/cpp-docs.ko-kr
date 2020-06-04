---
title: InitInstance 멤버 함수
ms.date: 11/04/2016
f1_keywords:
- InitInstance
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
ms.openlocfilehash: 2cf5b266348e299fe761ba40bd2cfb849f02b9ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377188"
---
# <a name="initinstance-member-function"></a>InitInstance 멤버 함수

Windows 운영 체제를 사용하면 동일한 응용 프로그램의 복사본 또는 "인스턴스"를 두 개 이상 실행할 수 있습니다. `WinMain`응용 프로그램의 새 인스턴스가 시작될 때마다 [InitInstance를](../mfc/reference/cwinapp-class.md#initinstance) 호출합니다.

MFC `InitInstance` 응용 프로그램 마법사에서 만든 표준 구현은 다음 작업을 수행합니다.

- 중앙 작업으로 문서, 뷰 및 프레임 창을 만드는 문서 템플릿을 만듭니다. 이 프로세스에 대한 설명은 [문서 템플릿 만들기](../mfc/document-template-creation.md)를 참조하십시오.

- .ini 파일 또는 Windows 레지스트리에서 가장 최근에 사용한 파일의 이름을 포함하여 표준 파일 옵션을 로드합니다.

- 하나 이상의 문서 템플릿을 등록합니다.

- MDI 응용 프로그램의 경우 주 프레임 창을 만듭니다.

- 명령줄을 처리하여 명령줄에 지정된 문서를 열거나 빈 새 문서를 엽니다.

사용자 고유의 초기화 코드를 추가하거나 마법사가 작성한 코드를 수정할 수 있습니다.

> [!NOTE]
> MFC 응용 프로그램은 단일 스레드 아파트(STA)로 초기화되어야 합니다. 재정의에서 [CoInitializeEx를](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) 호출하는 경우 COINIT_MULTITHREADED 대신 COINIT_APARTMENTTHREADED 지정합니다. `InitInstance`

## <a name="see-also"></a>참고 항목

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)
