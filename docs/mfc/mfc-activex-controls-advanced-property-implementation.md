---
title: 'MFC ActiveX 컨트롤: 고급 속성 구현'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
ms.openlocfilehash: d4f1265e6540e9f84bdb680e7948a4e308d31bb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364644"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX 컨트롤: 고급 속성 구현

이 문서에서는 ActiveX 컨트롤에서 고급 속성을 구현하는 데 관련된 항목에 대해 설명합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

- [읽기 전용 및 쓰기 전용 속성](#_core_read2donly_and_write2donly_properties)

- [속성에서 오류 코드 반환](#_core_returning_error_codes_from_a_property)

## <a name="read-only-and-write-only-properties"></a><a name="_core_read2donly_and_write2donly_properties"></a>읽기 전용 및 쓰기 전용 속성

속성 추가 마법사는 컨트롤에 대한 읽기 전용 또는 쓰기 전용 속성을 구현하는 빠르고 쉬운 방법을 제공합니다.

#### <a name="to-implement-a-read-only-or-write-only-property"></a>읽기 전용 또는 쓰기 전용 속성을 구현하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **속성 추가를** 클릭한 다음 **속성 추가를**클릭합니다.

   그러면 [속성 추가 마법사가](../ide/names-add-property-wizard.md)열립니다.

1. 속성 **이름** 상자에 속성 이름을 입력합니다.

1. **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.

1. 속성 **유형** 상자에서 속성에 대한 적절한 유형을 선택합니다.

1. 읽기 전용 속성을 원하는 경우 Set 함수 이름을 지웁니다. 쓰기 전용 속성을 원하는 경우 Get 함수 이름을 지웁니다.

1. **Finish**를 클릭합니다.

이렇게 하면 속성 추가 마법사가 일반 `SetNotSupported` 설정 `GetNotSupported` 또는 Get 함수 대신 함수 또는 디스패치 맵 항목에 삽입합니다.

기존 속성을 읽기 전용 또는 쓰기 전용으로 변경하려면 디스패치 맵을 수동으로 편집하고 컨트롤 클래스에서 불필요한 설정 또는 Get 함수를 제거할 수 있습니다.

속성이 조건부 읽기 전용 또는 쓰기 전용(예: 컨트롤이 특정 모드에서 작동하는 경우에만)을 원하는 경우 설정 또는 Get 함수를 정상적으로 `SetNotSupported` `GetNotSupported` 제공하고 적절한 경우 또는 함수를 호출할 수 있습니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]

이 코드 `SetNotSupported` 샘플은 `m_bReadOnlyMode` 데이터 멤버가 **TRUE인**경우 를 호출합니다. **FALSE인**경우 속성이 새 값으로 설정됩니다.

## <a name="returning-error-codes-from-a-property"></a><a name="_core_returning_error_codes_from_a_property"></a>속성에서 오류 코드 반환

속성을 얻거나 설정하는 동안 오류가 발생했음을 나타내려면 SCODE(상태 코드)를 매개 변수로 사용하는 `COleControl::ThrowError` 함수를 사용합니다. 미리 정의된 SCODE를 사용하거나 사용자 고유의 SCODE를 정의할 수 있습니다. 미리 정의된 SCOD 및 사용자 지정 SCOD를 정의하기 위한 지침은 ActiveX 컨트롤 문서: 고급 [항목에서 ActiveX 컨트롤의 오류 처리를](../mfc/mfc-activex-controls-advanced-topics.md) 참조하십시오.

도우미 함수는 [COleControl::SetNotSupported,](../mfc/reference/colecontrol-class.md#setnotsupported) [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported)및 [COleControl::SetNot허용](../mfc/reference/colecontrol-class.md#setnotpermitted)된 것과 같은 가장 일반적인 미리 정의된 SCODEs에 대해 존재합니다.

> [!NOTE]
> `ThrowError`속성의 Get 또는 Set 함수 또는 자동화 메서드 내에서 오류를 반환하는 수단으로만 사용됩니다. 스택에 적절한 예외 처리기가 있는 유일한 시간입니다.

코드의 다른 영역에서 예외를 보고하는 방법에 대한 자세한 내용은 ActiveX 컨트롤: 고급 항목문서에서 [ActiveX 컨트롤의](../mfc/mfc-activex-controls-advanced-topics.md) [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) 및 오류 처리 섹션을 참조하십시오.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)<br/>
[콜레컨트롤 클래스](../mfc/reference/colecontrol-class.md)
