---
title: 'TN023: 표준 MFC 리소스'
ms.date: 11/04/2016
helpviewer_keywords:
- resources [MFC]
- TN023
- standard resources
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
ms.openlocfilehash: 90e7b9b7c354ba919c3dee279725b4498bea57ff
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370377"
---
# <a name="tn023-standard-mfc-resources"></a>TN023: 표준 MFC 리소스

이 참고 는 MFC 라이브러리에서 제공 하 고 필요한 표준 리소스에 대해 설명 합니다.

## <a name="standard-resources"></a>표준 리소스

MFC는 응용 프로그램에서 사용할 수 있는 미리 정의된 리소스의 두 가지 범주인 클립 아트 리소스및 표준 프레임워크 리소스를 제공합니다.

클립 아트 리소스는 프레임워크가 종속되지 않지만 응용 프로그램의 사용자 인터페이스에 추가할 수 있는 추가 리소스입니다. 다음 클립 아트 리소스는 MFC 일반 샘플 [CLIPART에](../overview/visual-cpp-samples.md)포함되어 있습니다.

- Common.rc: 다음을 포함하는 단일 리소스 파일입니다.

  - 다양한 비즈니스 및 데이터 처리 작업을 나타내는 대규모 아이콘 컬렉션입니다.

  - 몇 가지 일반적인 커서(Afxres.rc 참조).

  - 여러 도구 모음 단추를 포함하는 도구 모음 비트맵입니다.

  - Commdlg.dll에서 사용하는 비트맵 및 아이콘 리소스입니다.

- indicate.rc: Caps Lock에 대한 "CAP"와 같은 상태 표시줄 키 상태 표시기의 문자열 리소스를 포함합니다.

- prompts.rc: ID_FILE_NEW 대해 "새 문서 만들기"와 같이 미리 정의된 각 명령에 대한 메뉴 프롬프트 문자열 리소스를 포함합니다.

- Commdlg.rc: 표준 COMMDLG 대화 상자 템플릿을 포함하는 Visual C++ 호환 .rc 파일입니다.

표준 프레임워크 리소스는 프레임워크가 내부 구현에 종속된 AFX 정의 된 ID가 있는 리소스입니다. 이러한 AFX 정의 리소스를 거의 변경할 필요가 없습니다. 이렇게 하면 이 항목의 설명이 있는 절차를 따라야 합니다.

다음 프레임워크 리소스는 MFC\INCLUDE 디렉터리에 포함되어 있습니다.

- Afxres.rc: 프레임워크에서 사용하는 공통 리소스입니다.

- Afxprint.rc: 인쇄에 관련된 리소스입니다.

- Afxolecl.rc: OLE 클라이언트 응용 프로그램에 특정한 리소스입니다.

- Afxolev.rc: 전체 OLE 서버 응용 프로그램에 관련된 리소스입니다.

## <a name="using-clip-art-resources"></a>클립 아트 리소스 사용

#### <a name="to-use-a-clip-art-binary-resource"></a>클립 아트 바이너리 리소스를 사용하려면

1. Visual C++에서 응용 프로그램의 리소스 파일을 엽니다.

1. 커먼.rc를 엽니다. 이 파일에는 모든 이진 클립 아트 리소스가 포함되어 있습니다. Common.rc 파일이 컴파일되므로 시간이 걸릴 수 있습니다.

1. Common.rc에서 응용 프로그램의 리소스 파일로 사용할 리소스를 드래그하는 동안 CTRL을 누를 수 있습니다.

다른 클립 아트 리소스를 사용하려면 동일한 단계를 따르십시오. 유일한 차이점은 Common.rc 대신 적절한 .rc 파일을 여는 것입니다.

> [!NOTE]
> 실수로 Common.rc에서 리소스를 영구적으로 이동하지 않도록 주의하십시오. 리소스를 드래그하는 동안 CTRL 키를 보유하면 복사본을 만듭니다. 드래그하는 동안 CTRL을 누르지 않으면 리소스가 이동됩니다. Common.rc 파일을 실수로 변경했을 수 있는 경우 변경 내용을 Common.rc에 저장할지 여부를 묻는 메시지가 표시됩니다.

> [!NOTE]
> .rc 리소스 파일에는 표준 .rc 파일 위에 실수로 저장하지 못하게하는 특별한 TEXTINCLUDE 리소스가 있습니다.

### <a name="customizing-standard-framework-resources"></a>표준 프레임워크 리소스 사용자 지정

표준 프레임워크 리소스는 일반적으로 응용 프로그램의 리소스 파일에 #include 명령을 사용하여 응용 프로그램에 포함됩니다. AppWizard 리소스 파일을 생성 합니다. 이 파일에는 선택한 AppWizard 옵션에 따라 적절한 표준 프레임워크 리소스가 포함됩니다. 컴파일 타임 지시문을 변경하여 포함된 리소스를 검토, 추가 또는 제거할 수 있습니다. 이렇게 하려면 **리소스** 메뉴를 열고 **포함 설정을**선택합니다. "컴파일 타임 지시문" 편집 항목을 살펴봅니다. 다음은 그 예입니다.

```
#include "afxres.rc"
#include "afxprint.rc"
```

표준 프레임워크 리소스를 사용자 지정하는 가장 일반적인 경우는 인쇄, OLE 클라이언트 및 OLE 서버 지원에 대한 추가 포함을 추가하거나 제거하는 것입니다.

드문 경우지만 전체 파일을 추가하고 제거하는 것이 아니라 특정 응용 프로그램에 대한 표준 프레임워크 리소스의 내용을 사용자 지정할 수 있습니다. 다음 단계는 포함된 리소스를 제한하는 방법을 보여 주며 다음과 같습니다.

##### <a name="to-customize-the-contents-of-a-standard-resource-file"></a>표준 리소스 파일의 내용을 사용자 지정하려면

1. 시각적 C++에서 리소스 파일을 엽니다.

1. 리소스 집합 포함 명령을 사용하여 `#include` 사용자 지정하려는 표준 .rc 파일에 대해 을 제거합니다. 예를 들어 인쇄 미리 보기 도구 모음을 `#include "afxprint.rc"` 사용자 지정하려면 줄을 제거합니다.

1. MFC\INCLUDE에서 적절한 표준 리소스 파일을 엽니다. 이 항목의 이전 예제에 따라 적절한 파일은 MFC\Include\Aafxprint.rc입니다.

1. 표준 .rc 파일의 모든 리소스를 응용 프로그램 리소스 파일로 복사합니다.

1. 응용 프로그램 리소스 파일에서 표준 리소스의 복사본을 수정합니다.

> [!NOTE]
> 표준 .rc 파일에서 리소스를 직접 수정하지 마십시오. 이렇게 하면 현재 작업 중인 응용 프로그램뿐만 아니라 모든 응용 프로그램에서 사용할 수 있는 리소스가 수정됩니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
