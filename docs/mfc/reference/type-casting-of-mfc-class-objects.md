---
title: MFC 클래스 개체의 형식 캐스팅
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
ms.openlocfilehash: 953acc32c3510b31c265f2d64d0a013f6dee06cc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372887"
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC 클래스 개체의 형식 캐스팅

형식 캐스팅 매크로는 캐스트가 합법적인지 여부와 함께 또는 확인하지 않고 특정 클래스의 개체를 가리키는 포인터에 지정된 포인터를 캐스팅하는 방법을 제공합니다.

다음 표에는 매크로를 캐스팅하는 MFC 형식이 나열되어 있습니다.

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>MFC 클래스 개체에 포인터를 캐스팅하는 매크로

|||
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|캐스트가 합법적인지 확인하는 동안 클래스 개체에 대한 포인터를 캐스팅합니다.|
|[STATIC_DOWNCAST](#static_downcast)|한 클래스에서 관련 형식의 포인터로 개체에 대한 포인터를 캐스팅합니다. 디버그 빌드에서 개체가 대상 형식의 "일종"이 아닌 경우 ASSERT를 발생시킵니다.|

## <a name="dynamic_downcast"></a><a name="dynamic_downcast"></a>DYNAMIC_DOWNCAST

캐스트가 합법적인지 확인하는 동안 클래스 개체에 대한 포인터를 캐스팅하는 편리한 방법을 제공합니다.

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>매개 변수

*class*<br/>
클래스의 이름입니다.

*포인터(pointer)*<br/>
형식 *클래스의*개체에 대한 포인터에 캐스팅할 포인터입니다.

### <a name="remarks"></a>설명

매크로는 *포인터* 매개 변수를 *클래스* 매개 변수 형식의 개체에 대한 포인터로 캐스팅합니다.

포인터에서 참조하는 개체가 식별된 클래스의 "종류"인 경우 매크로는 적절한 포인터를 반환합니다. 법적 캐스트가 아닌 경우 매크로는 NULL을 반환합니다.

## <a name="static_downcast"></a><a name="static_downcast"></a>STATIC_DOWNCAST

*pobject를* *class_name* 개체에 대한 포인터로 캐스팅합니다.

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
캐스팅중인 클래스의 이름입니다.

*대상 (것)과 같은*<br/>
*class_name* 개체에 대한 포인터에 캐스팅할 포인터입니다.

### <a name="remarks"></a>설명

*pobject는* null이거나 *class_name*에서 직접 또는 간접적으로 파생되는 클래스의 개체를 가리킬 수 있어야 합니다. _DEBUG 전처리 기호가 정의된 응용 프로그램 빌드에서 *매크로는 pobject가* NULL이 아니거나 *class_name* 매개 변수에 지정된 클래스의 "종류"가 아닌 개체를 가리키는 경우 [assert합니다(CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)참조). _DEBUG **빌드가** 아닌 빌드에서 매크로는 형식 검사 없이 캐스트를 수행합니다.

*class_name* 매개 변수에 지정된 클래스는 `CObject` DECLARE_DYNAMIC 및 IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE 및 IMPLEMENT_DYNCREATE 또는 [cObject 클래스: CObject에서 클래스 파생이라는](../../mfc/deriving-a-class-from-cobject.md)문서에 설명된 대로 DECLARE_SERIAL 및 IMPLEMENT_SERIAL 매크로에서 파생되어야 합니다.

예를 들어 이 식을 `CMyDoc`사용하는 `pMyDoc`포인터에 대해 `CDocument` "라고 하는"에 대한 포인터를 캐스팅할 수 있습니다.

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

직접 `pMyDoc` 또는 간접적으로 `CDocument`파생된 개체를 가리키지 않으면 매크로가 ASSERT됩니다.

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
