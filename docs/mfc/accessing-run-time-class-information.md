---
title: 런타임 클래스 정보 액세스
ms.date: 11/04/2016
helpviewer_keywords:
- CObject class [MFC], and RTTI
- CObject class [MFC], using IsKindOf method [MFC]
- run time [MFC], class information
- RUNTIME_CLASS macro [MFC]
- CObject class [MFC], using RUNTIME_CLASS macro [MFC]
- RTTI compiler option [MFC]
- CObject class [MFC], accessing run-time class information
- run time [MFC]
- IsKindOf method method [MFC]
- run-time class [MFC], accessing information
- classes [MFC], run-time class information
- run-time class [MFC]
- RUNTIME_CLASS macro, using
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
ms.openlocfilehash: 4a836bb7bd03bd6654e5c940442fecf541042fd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354221"
---
# <a name="accessing-run-time-class-information"></a>런타임 클래스 정보 액세스

이 문서에서는 런타임에 개체의 클래스에 대한 정보에 액세스하는 방법을 설명합니다.

> [!NOTE]
> MFC는 Visual C++ 4.0에 도입된 [RTTI(런타임 형식 정보)](../cpp/run-time-type-information.md) 지원을 사용하지 않습니다.

[CObject에서](../mfc/reference/cobject-class.md) 클래스를 파생하고 **DECLARE**_**DYNAMIC** 및 `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` `IMPLEMENT_DYNCREATE`및 , `DECLARE_SERIAL` `IMPLEMENT_SERIAL` 또는 [CObject에서 클래스를 파생하는](../mfc/deriving-a-class-from-cobject.md)문서에서 설명하는 `CObject` 매크로를 사용한 경우 클래스는 런타임에 개체의 정확한 클래스를 결정할 수 있습니다.

이 기능은 함수 인수의 추가 형식 검사가 필요하고 개체의 클래스에 따라 특수 목적 코드를 작성해야 하는 경우에 가장 유용합니다. 그러나 이 방법은 일반적으로 가상 함수의 기능을 복제하기 때문에 권장되지 않습니다.

멤버 `CObject` 함수를 `IsKindOf` 사용하여 특정 개체가 지정된 클래스에 속하는지 또는 특정 클래스에서 파생되는지 확인할 수 있습니다. `IsKindOf` 인수는 클래스의 `CRuntimeClass` 이름으로 매크로를 `RUNTIME_CLASS` 사용할 수 있는 개체입니다.

### <a name="to-use-the-runtime_class-macro"></a>RUNTIME_CLASS 매크로를 사용하려면

1. 클래스의 이름과 함께 다음과 같이 클래스의 `RUNTIME_CLASS` `CObject`이름을 사용합니다.

   [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

런타임 클래스 개체에 직접 액세스할 필요는 거의 없습니다. 더 일반적인 용도는 다음 프로시저에 표시된 `IsKindOf` 대로 런타임 클래스 개체를 함수에 전달하는 것입니다. 함수는 `IsKindOf` 개체가 특정 클래스에 속하는지 확인하기 위해 개체를 테스트합니다.

#### <a name="to-use-the-iskindof-function"></a>IsKindOf 기능을 사용하려면

1. 클래스에 런타임 클래스 지원이 있는지 확인합니다. 즉, 클래스는 `CObject` 직접 또는 간접적으로 파생되어 **선언**_**DYNAMIC** `IMPLEMENT_DYNAMIC`및, `DECLARE_DYNCREATE` `IMPLEMENT_DYNCREATE`및 및 `DECLARE_SERIAL` `IMPLEMENT_SERIAL` [매크로를 CObject에서 클래스 파생](../mfc/deriving-a-class-from-cobject.md)문서에서 설명한 것으로 사용해야 합니다.

1. 매크로를 `IsKindOf` 사용하여 `RUNTIME_CLASS` 다음과 같이 인수를 생성하는 해당 클래스의 개체에 대한 멤버 함수를 `CRuntimeClass` 호출합니다.

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  개체가 지정된 클래스의 멤버이거나 지정된 클래스에서 파생된 클래스의 멤버인 경우 IsKindOf는 **TRUE를** 반환합니다. `IsKindOf`필요한 경우 파생 된 Microsoft Foundation 클래스에 여러 상속을 사용할 수 있지만 여러 상속 또는 가상 기본 클래스를 지원 하지 않습니다.

런타임 클래스 정보의 한 가지 사용은 개체의 동적 생성에 있습니다. 이 프로세스는 [동적 개체 만들기](../mfc/dynamic-object-creation.md)문서에서 설명합니다.

직렬화 및 런타임 클래스 정보에 대한 자세한 내용은 [MFC](../mfc/files-in-mfc.md) 및 [직렬화의](../mfc/serialization-in-mfc.md)문서 파일을 참조하십시오.

## <a name="see-also"></a>참고 항목

[CObject 사용](../mfc/using-cobject.md)
