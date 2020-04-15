---
title: 'MFC ActiveX 컨트롤: 고급 항목'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- MFC ActiveX controls [MFC], accessing invisible dialog controls
- MFC ActiveX controls [MFC], advanced topics
- FireError method [MFC]
- MFC ActiveX controls [MFC], database classes
- MFC ActiveX controls [MFC], special keys
- PreTranslateMessage method [MFC]
- MFC ActiveX controls [MFC], parameterized property
- ThrowError method [MFC]
ms.assetid: e9e34abb-8e2d-461e-bb9c-a1aec5dcecbd
ms.openlocfilehash: c5e3be3915a0707f8df17d3c9ebe2eb0e4f623b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364634"
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC ActiveX 컨트롤: 고급 항목

이 문서에서는 ActiveX 컨트롤 개발과 관련된 고급 항목을 다룹니다. 여기에는 다음이 포함됩니다.

- [ActiveX 컨트롤에서 데이터베이스 클래스 사용](#_core_using_database_classes_in_activex_controls)

- [매개 변수화된 속성 구현](#_core_implementing_a_parameterized_property)

- [ActiveX 컨트롤의 오류 처리](#_core_handling_errors_in_your_activex_control)

- [컨트롤의 특수 키 처리](#_core_handling_special_keys_in_your_control)

- [런타임에 표시되지 않는 대화 상자 컨트롤 액세스](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

## <a name="using-database-classes-in-activex-controls"></a><a name="_core_using_database_classes_in_activex_controls"></a>ActiveX 컨트롤에서 데이터베이스 클래스 사용

ActiveX 컨트롤 클래스는 클래스 라이브러리의 일부이므로 표준 MFC 응용 프로그램에서 데이터베이스 클래스를 사용하기 위한 동일한 절차 및 규칙을 MFC 데이터베이스 클래스를 사용하는 ActiveX 컨트롤을 개발할 수 있습니다.

MFC 데이터베이스 클래스에 대한 일반적인 개요는 [MFC 데이터베이스 클래스(DAO 및 ODBC)를](../data/mfc-database-classes-odbc-and-dao.md)참조하십시오. 이 문서에서는 MFC ODBC 클래스와 MFC DAO 클래스를 모두 소개하고 자세한 내용을 안내합니다.

> [!NOTE]
> DAO는 Office 2013을 통해 지원됩니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다. Visual C++ 환경 및 마법사는 DAO를 지원하지 않습니다(DAO 클래스가 포함되어 있지만 여전히 사용할 수 있음). 새 프로젝트에 는 [OLE DB 템플릿](../data/oledb/ole-db-programming.md) 또는 [ODBC 및 MFC를](../data/odbc/odbc-and-mfc.md) 사용하는 것이 좋습니다. 기존 응용 프로그램을 유지 관리하는 데만 DAO를 사용해야 합니다.

## <a name="implementing-a-parameterized-property"></a><a name="_core_implementing_a_parameterized_property"></a>매개 변수화된 속성 구현

매개 변수화된 속성(속성 배열이라고도 함)은 컨트롤의 단일 속성으로 균일한 값 컬렉션을 노출하는 메서드입니다. 예를 들어 매개 변수화된 속성을 사용하여 배열 또는 사전을 속성으로 노출할 수 있습니다. Visual Basic에서 이러한 속성은 배열 표기화를 사용하여 액세스됩니다.

[!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]

속성 추가 마법사를 사용하여 매개 변수화된 속성을 구현합니다. 속성 추가 마법사는 컨트롤 사용자가 위의 표기또는 표준 방식으로 속성에 액세스할 수 있도록 하는 Get/Set 함수 쌍을 추가하여 속성을 구현합니다.

메서드 및 속성과 마찬가지로 매개 변수화된 속성도 허용되는 매개 변수 수에 제한이 있습니다. 매개 변수화된 속성의 경우 제한은 15개의 매개변수입니다(속성 값을 저장하기 위해 예약된 매개 변수 하나).

다음 절차는 정수의 2차원 배열로 액세스할 수 있는 Array라는 매개 변수화된 속성을 추가합니다.

#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용하여 매개 변수화된 속성을 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **속성 추가를** 클릭한 다음 **속성 추가를**클릭합니다.

1. 속성 **이름** 상자에 을 `Array`입력합니다.

1. 속성 **유형** 상자에서 **짧은**을 선택합니다.

1. **구현** 유형의 경우 **메서드 받기/설정**을 클릭합니다.

1. **함수** **받기** 상자에서 함수 받기 및 설정 함수에 대한 고유 이름을 입력하거나 기본 이름을 수락합니다.

1. 매개 변수 이름 및 매개 변수 **유형** 컨트롤을 사용하여 *행(짧은* 형식)이라는 **매개 변수를** 추가합니다. *short*

1. *열이라는* 두 번째 매개 변수를 추가합니다(짧은 형식). *short*

1. **Finish**를 클릭합니다.

### <a name="changes-made-by-the-add-property-wizard"></a>속성 추가 마법사에 의해 변경 된 변경 사항

사용자 지정 속성을 추가하면 속성 추가 마법사에서 컨트롤 클래스 헤더()를 변경합니다. H) 및 구현(. CPP) 파일.

다음 줄이 컨트롤 클래스에 추가됩니다. H 파일:

[!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]

이 코드는 호출된 `GetArray` 두 `SetArray` 함수를 선언하며 사용자가 속성에 액세스할 때 특정 행과 열을 요청할 수 있도록 합니다.

또한 속성 추가 마법사는 컨트롤 클래스 구현에 있는 컨트롤 디스패치 맵에 다음 줄을 추가합니다. CPP) 파일:

[!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]

마지막으로 `GetArray` 및 `SetArray` 함수의 구현이 의 끝에 추가됩니다. CPP 파일. 대부분의 경우 속성 값을 반환하도록 Get 함수를 수정합니다. Set 함수에는 일반적으로 속성이 변경되기 전이나 후에 실행해야 하는 코드가 포함됩니다.

이 속성이 유용하도록 하려면 컨트롤 클래스에서 2차원 배열 멤버 변수를 **short**선언할 수 있습니다. 그런 다음 Get 함수를 수정하여 매개 변수에 표시된 대로 적절한 행 및 열에 저장된 값을 반환하고 Set 함수를 수정하여 행 및 열 매개 변수에서 참조하는 값을 업데이트할 수 있습니다.

## <a name="handling-errors-in-your-activex-control"></a><a name="_core_handling_errors_in_your_activex_control"></a>ActiveX 컨트롤의 오류 처리

컨트롤에서 오류 조건이 발생하는 경우 컨트롤 컨테이너에 오류를 보고해야 할 수 있습니다. 오류가 발생하는 상황에 따라 오류를 보고하는 방법에는 두 가지가 있습니다. 속성의 Get or Set 함수 내에서 또는 OLE 자동화 메서드의 구현 내에서 오류가 발생하는 경우 컨트롤은 [COleControl:ThrowError를](../mfc/reference/colecontrol-class.md#throwerror)호출해야 하며, 이 오류는 컨트롤 사용자에게 오류가 발생했음을 알리는 신호입니다. 다른 시간에 오류가 발생하면 컨트롤은 [COleControl::FireError를](../mfc/reference/colecontrol-class.md#fireerror)호출하여 주식 오류 이벤트를 발생시야 합니다.

발생한 오류의 종류를 나타내려면 컨트롤이 오류 코드를 `ThrowError` 또는 `FireError`에 전달해야 합니다. 오류 코드는 32비트 값을 가지는 OLE 상태 코드입니다. 가능하면 OLECTL에 정의된 표준 코드 집합에서 오류 코드를 선택합니다. H 헤더 파일입니다. 다음 표에는 이러한 코드가 요약되어 있습니다.

### <a name="activex-control-error-codes"></a>ActiveX 제어 오류 코드

|Error|Description|
|-----------|-----------------|
|CTL_E_ILLEGALFUNCTIONCALL|잘못된 함수 호출|
|CTL_E_OVERFLOW|오버플로|
|CTL_E_OUTOFMEMORY|메모리가 부족합니다.|
|CTL_E_DIVISIONBYZERO|0으로 나누기|
|CTL_E_OUTOFSTRINGSPACE|문자열 공간이 부족합니다.|
|CTL_E_OUTOFSTACKSPACE|스택 공간이 부족합니다.|
|CTL_E_BADFILENAMEORNUMBER|파일 이름 또는 번호가 잘못되었습니다.|
|CTL_E_FILENOTFOUND|파일을 찾을 수 없습니다.|
|CTL_E_BADFILEMODE|파일 모드가 잘못되었습니다.|
|CTL_E_FILEALREADYOPEN|파일이 이미 열려 있습니다.|
|CTL_E_DEVICEIOERROR|디바이스 입/출력(I/O) 오류입니다.|
|CTL_E_FILEALREADYEXISTS|파일이 이미 있습니다.|
|CTL_E_BADRECORDLENGTH|레코드 길이가 잘못되었습니다.|
|CTL_E_DISKFULL|디스크 전체|
|CTL_E_BADRECORDNUMBER|레코드 개수가 잘못되었습니다.|
|CTL_E_BADFILENAME|잘못된 파일 이름|
|CTL_E_TOOMANYFILES|파일이 너무 많습니다.|
|CTL_E_DEVICEUNAVAILABLE|디바이스를 사용할 수 없습니다.|
|CTL_E_PERMISSIONDENIED|사용 권한이 거부됨|
|CTL_E_DISKNOTREADY|디스크가 준비되지 않았습니다.|
|CTL_E_PATHFILEACCESSERROR|경로/파일 액세스 오류|
|CTL_E_PATHNOTFOUND|경로를 찾을 수 없습니다.|
|CTL_E_INVALIDPATTERNSTRING|잘못된 패턴 문자열|
|CTL_E_INVALIDUSEOFNULL|NULL의 잘못된 사용|
|CTL_E_INVALIDFILEFORMAT|잘못된 파일 형식|
|CTL_E_INVALIDPROPERTYVALUE|잘못된 속성 값|
|CTL_E_INVALIDPROPERTYARRAYINDEX|잘못된 속성 배열 인덱스|
|CTL_E_SETNOTSUPPORTEDATRUNTIME|Set은 런타임에 지원되지 않습니다.|
|CTL_E_SETNOTSUPPORTED|Set은 지원되지 않습니다(읽기 전용 속성).|
|CTL_E_NEEDPROPERTYARRAYINDEX|속성 배열 인덱스가 필요합니다.|
|CTL_E_SETNOTPERMITTED|Set은 허용되지 않습니다.|
|CTL_E_GETNOTSUPPORTEDATRUNTIME|Get은 런타임에 지원되지 않습니다.|
|CTL_E_GETNOTSUPPORTED|Get은 지원되지 않습니다(쓰기 전용 속성).|
|CTL_E_PROPERTYNOTFOUND|속성을 찾을 수 없습니다.|
|CTL_E_INVALIDCLIPBOARDFORMAT|잘못된 클립보드 형식|
|CTL_E_INVALIDPICTURE|잘못된 그림|
|CTL_E_PRINTERERROR|프린터 오류|
|CTL_E_CANTSAVEFILETOTEMP|파일을 임시로 저장할 수 없습니다.|
|CTL_E_SEARCHTEXTNOTFOUND|검색 텍스트를 찾을 수 없습니다.|
|CTL_E_REPLACEMENTSTOOLONG|대체 텍스트가 너무 깁니다.|

필요한 경우 CUSTOM_CTL_SCODE 매크로를 사용하여 표준 코드 중 하나에서 다루지 않는 조건에 대한 사용자 지정 오류 코드를 정의합니다. 이 매크로의 매개 변수는 1000에서 32767 사이의 정수여야 합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]

기존 VBX 컨트롤을 대체하기 위해 ActiveX 컨트롤을 만드는 경우 ActiveX 컨트롤 오류 코드를 VBX 컨트롤에서 사용하는 것과 동일한 숫자 값으로 정의하여 오류 코드가 호환되도록 합니다.

## <a name="handling-special-keys-in-the-control"></a><a name="_core_handling_special_keys_in_your_control"></a>컨트롤의 특수 키 처리

경우에 따라 특정 키 입력 조합을 특수한 방식으로 처리할 수 있습니다. 예를 들어 ENTER 키가 다중 줄 텍스트 상자 컨트롤에서 누를 때 새 줄을 삽입하거나 방향 키 ID를 누를 때 편집 컨트롤 그룹 간에 이동합니다.

ActiveX 컨트롤의 기본 클래스가 `COleControl`있는 경우 [CWnd::PreTranslateMessage를](../mfc/reference/cwnd-class.md#pretranslatemessage) 재정의하여 컨테이너가 메시지를 처리하기 전에 메시지를 처리할 수 있습니다. 이 기술을 사용하는 경우 재정의에서 `PreTranslateMessage`메시지를 처리하는 경우 TRUE를 항상 반환합니다. **TRUE**

다음 코드 예제에서는 방향 키와 관련된 모든 메시지를 처리하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]

ActiveX 컨트롤의 키보드 인터페이스 처리에 대한 자세한 내용은 ActiveX SDK 설명서를 참조하십시오.

## <a name="accessing-dialog-controls-that-are-invisible-at-run-time"></a><a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a>런타임에 표시되지 않는 대화 상자 컨트롤 에 액세스

사용자 인터페이스가 없고 런타임에 표시되지 않는 대화 상자 컨트롤을 만들 수 있습니다. 런타임에 보이지 않는 ActiveX 컨트롤을 대화 상자에 추가하고 [CWnd::GetDlgItem을](../mfc/reference/cwnd-class.md#getdlgitem) 사용하여 컨트롤에 액세스하면 컨트롤이 제대로 작동하지 않습니다. 대신 다음 기술 중 하나를 사용하여 컨트롤을 나타내는 개체를 가져와야 합니다.

- 멤버 변수 추가 마법사를 사용하여 **컨트롤 변수를** 선택한 다음 컨트롤의 ID를 선택합니다. 멤버 변수 이름을 입력하고 컨트롤의 래퍼 클래스를 **컨트롤 유형으로**선택합니다.

     또는

- 지역 변수와 하위 클래스를 대화 상자 항목으로 선언합니다. 다음과 유사한 코드를 삽입합니다(래퍼`CMyCtrl` 클래스, 컨트롤의 ID IDC_MYCTRL1).

   [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
