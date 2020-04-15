---
title: 템플릿 기반 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections
- CTypedPtrList class [MFC], template-based classes
- arrays [MFC], classes
- arrays [MFC], pointers
- typed pointers, collections of
- arrays [MFC], template-based
- CArray class [MFC], template-based classes
- simple template-based collections
- simple array collection classes [MFC]
- typed pointers
- collections, typed-pointer
- CList class [MFC], template-based classes
- collection classes [MFC], template-based
- CTypedPtrMap class [MFC], template-based classes
- pointers, collections of typed
- CTypedPtrArray class [MFC], template-based classes
- MFC collection classes [MFC], template-based
- template-based collection classes [MFC]
- simple list collection classes [MFC]
ms.assetid: c69fc95b-c8f6-4a99-abed-517c9898ef0c
ms.openlocfilehash: 29f5f815b62835aedbca1f79b797f826ea53d83b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370464"
---
# <a name="template-based-classes"></a>템플릿 기반 클래스

이 문서에서는 MFC 버전 3.0 이상에서 형식 이 안전한 템플릿 기반 컬렉션 클래스에 대해 설명합니다. 이러한 템플릿을 사용하여 형식 이 안전한 컬렉션을 만드는 것이 더 편리하며 템플릿을 기반으로 하지 않는 컬렉션 클래스를 사용하는 것보다 형식 안전도를 보다 효과적으로 제공하는 데 도움이 됩니다.

MFC는 템플릿 기반 컬렉션의 두 가지 범주를 미리 정의합니다.

- [간단한 배열, 목록 및 맵 클래스](#_core_using_simple_array.2c_.list.2c_.and_map_templates)

   `CArray`, `CList`, `CMap`

- [형식이 있는 포인터의 배열, 목록 및 맵](#_core_using_typed.2d.pointer_collection_templates)

   `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`

단순 컬렉션 클래스는 모두 클래스에서 `CObject`파생되므로 직렬화, 동적 만들기 및 `CObject`의 기타 속성을 상속합니다. 형식이 지정된 포인터 컬렉션 클래스에서는 MFC에서 미리 정의한 템플릿이 아닌 포인터 컬렉션 중 하나여야 `CPtrList` `CPtrArray`하는 파생 클래스를 지정해야 합니다. 새 컬렉션 클래스는 지정된 기본 클래스에서 상속되고 새 클래스의 멤버 함수는 형식 안전을 적용하기 위해 기본 클래스 멤버에 대한 캡슐화된 호출을 사용합니다.

C++ 템플릿에 대한 자세한 내용은 *C++ 언어 참조의* [템플릿을](../cpp/templates-cpp.md) 참조하십시오.

## <a name="using-simple-array-list-and-map-templates"></a><a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a>간단한 배열, 목록 및 맵 템플릿 사용

간단한 컬렉션 템플릿을 사용하려면 이러한 컬렉션에 저장할 수 있는 데이터의 종류와 컬렉션 선언에 사용할 매개 변수를 알아야 합니다.

### <a name="simple-array-and-list-usage"></a><a name="_core_simple_array_and_list_usage"></a>간단한 배열 및 목록 사용

간단한 배열 및 목록 클래스인 [CArray](../mfc/reference/carray-class.md) 및 [CList는](../mfc/reference/clist-class.md) `ARG_TYPE` *TYPE* 및 . 이러한 클래스는 *TYPE* 매개 변수에서 지정한 모든 데이터 형식을 저장할 수 있습니다.

- **int,** **char**및 **float와** 같은 기본 C++ 데이터 형식

- C++ 구조 및 클래스

- 정의하는 다른 형식

편의성과 효율성을 위해 *ARG_TYPE* 매개 변수를 사용하여 함수 인수의 유형을 지정할 수 있습니다. 일반적으로 *ARG_TYPE* *TYPE* 매개 변수에서 지정한 형식에 대한 참조로 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]

첫 번째 예제에서는 `myArray` **int**s를 포함하는 배열 컬렉션 , "를 선언합니다. 두 번째 예제에서는 개체를 `myList`저장하는 `CPerson` 목록 컬렉션( 및 개체)을 선언합니다. 컬렉션 클래스의 특정 멤버 함수는 *ARG_TYPE* 템플릿 매개 변수에 의해 형식이 지정된 인수를 사용합니다. 예를 들어 `Add` 클래스의 `CArray` 멤버 함수는 *ARG_TYPE* 인수를 취합니다.

[!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]

### <a name="simple-map-usage"></a><a name="_core_simple_map_usage"></a>간단한 지도 사용

간단한 맵 클래스인 [CMap은](../mfc/reference/cmap-class.md) *KEY,* *ARG_KEY,* *value*및 *ARG_VALUE*네 가지 매개 변수를 사용합니다. 배열 및 목록 클래스와 마찬가지로 맵 클래스는 모든 데이터 형식을 저장할 수 있습니다. 저장하는 데이터를 인덱싱하고 정렬하는 배열 및 목록과 달리 맵은 키와 값을 연결합니다: 값의 관련 키를 지정하여 맵에 저장된 값에 액세스합니다. *KEY* 매개 변수는 맵에 저장된 데이터에 액세스하는 데 사용되는 키의 데이터 형식을 지정합니다. *KEY* 의 형식이 구조 또는 클래스인 경우 *ARG_KEY* 매개 변수는 일반적으로 *KEY에*지정된 형식에 대한 참조입니다. *VALUE* 매개 변수는 맵에 저장된 항목의 유형을 지정합니다. *ARG_VALUE* 형식이 구조또는 클래스인 경우 *ARG_VALUE* 매개 변수는 일반적으로 *VALUE에*지정된 형식에 대한 참조입니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]

첫 번째 `MY_STRUCT` 예제에서는 값을 저장하고 **int** 키로 `MY_STRUCT` 액세스하며 액세스한 항목을 참조로 반환합니다. 두 번째 `CPerson` 예제에서는 값을 저장하고, 키로 `CString` 액세스하고, 액세스한 항목에 대한 참조를 반환합니다. 이 예제에서는 성으로 사람을 조회하는 간단한 주소록을 나타낼 수 있습니다.

*KEY* 매개 변수는 `CString` 형식이고 *KEY_TYPE* 매개 `LPCSTR`변수는 형식이기 때문에 키는 형식의 `CString` 항목으로 맵에 저장되지만 `SetAt` 형식의 `LPCSTR`포인터를 통해 참조됩니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]

## <a name="using-typed-pointer-collection-templates"></a><a name="_core_using_typed.2d.pointer_collection_templates"></a>입력된 포인터 컬렉션 템플릿 사용

형식화 된 포인터 컬렉션 템플릿을 사용 하려면 이러한 컬렉션에 저장할 수 있는 데이터의 종류와 컬렉션 선언에 사용할 매개 변수를 알아야 합니다.

### <a name="typed-pointer-array-and-list-usage"></a><a name="_core_typed.2d.pointer_array_and_list_usage"></a>입력된 포인터 배열 및 목록 사용

입력된 포인터 배열 및 목록 클래스인 [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) 및 [CTypedPtrList는](../mfc/reference/ctypedptrlist-class.md) *BASE_CLASS* 및 *TYPE*의 두 가지 매개 변수를 사용합니다. 이러한 클래스는 *TYPE* 매개 변수에 지정한 모든 데이터 형식을 저장할 수 있습니다. 포인터를 저장하는 템플릿이 아닌 컬렉션 클래스 중 하나에서 파생됩니다. *BASE_CLASS*이 기본 클래스를 지정합니다. 배열의 경우 `CObArray` 또는 `CPtrArray`를 사용합니다. 목록의 경우 `CObList` 또는 `CPtrList`을 사용하십시오.

실제로 새 클래스를 기반으로 `CObList`컬렉션을 선언할 때 는 기본 클래스의 멤버를 상속할 뿐만 아니라 기본 클래스 멤버에 대한 호출을 캡슐화하여 형식 안전성을 제공하는 데 도움이 되는 여러 가지 추가 형식 안전 멤버 함수 및 연산자도 선언합니다. 이러한 캡슐화는 필요한 모든 형식 변환을 관리합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]

첫 번째 예제에서는 에서 파생된 `myArray`형식된 포인터 `CObArray`배열을 선언합니다. 배열은 포인터를 개체(여기서 `CPerson` `CPerson` `CObject`파생된 클래스)에 저장하고 반환합니다. 모든 `CObArray` 멤버 함수를 호출하거나 새 형식 안전 `GetAt` 함수를 `ElementAt` 호출하거나 형식 안전 **[]** 연산자를 사용할 수 있습니다.

두 번째 예제에서는 에서 `myList` `CPtrList`파생된 형식된 포인터 목록을 선언합니다. 목록에서 개체에 `MY_STRUCT` 포인터를 저장하고 반환합니다. 을 기반으로 `CPtrList` 하는 클래스는 `CObject`에서 파생되지 않은 개체에 대한 포인터를 저장하는 데 사용됩니다. `CTypedPtrList`형식이 `GetHead`안전한 멤버 함수가 `GetTail` `RemoveHead` `RemoveTail` `GetNext` `GetPrev` `GetAt`있습니다.

### <a name="typed-pointer-map-usage"></a><a name="_core_typed.2d.pointer_map_usage"></a>입력된 포인터 맵 사용

입력된 포인터 맵 클래스인 [CTypedPtrMap은](../mfc/reference/ctypedptrmap-class.md) *BASE_CLASS,* *KEY*및 *VALUE의*세 가지 매개 변수를 사용합니다. *BASE_CLASS* 매개 `CMapPtrToWord`변수는 새 클래스를 `CMapPtrToPtr` `CMapStringToPtr` `CMapWordToPtr` `CMapStringToOb`파생할 클래스를 지정합니다. *KEY는* *KEY에서* `CMap`와 유사합니다: 조회에 사용되는 키의 유형을 지정합니다. *VALUE는* *VALUE에서* 와 `CMap`유사합니다: 맵에 저장된 개체의 유형을 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]

첫 번째 예는 에 `CMapPtrToPtr` 대한 `CString` 포인터에 매핑된 키를 사용하는 맵을 기반으로 하는 `MY_STRUCT`맵입니다. 형식 이 안전한 `Lookup` 멤버 함수를 호출하여 저장된 포인터를 조회할 수 있습니다. **[]** 연산자를 사용하여 저장된 포인터를 조회하고 찾을 수 없는 경우 추가할 수 있습니다. 또한 형식 안전 `GetNextAssoc` 함수를 사용하여 맵을 반복할 수 있습니다. 클래스의 `CMapPtrToPtr`다른 멤버 함수를 호출할 수도 있습니다.

두 번째 예는 오브젝트에 저장된 포인터에 매핑된 문자열 키를 사용하는 맵을 기반으로 `CMapStringToOb` 하는 맵입니다. `CMyObject` 이전 단락에서 설명한 것과 동일한 형식 보호 멤버를 사용하거나 `CMapStringToOb`클래스의 멤버를 호출할 수 있습니다.

> [!NOTE]
> *VALUE* 매개 변수에 대 한 **클래스** 또는 **구조체** 형식을 지정 하는 경우 포인터 또는 형식에 대 한 참조 대신, 클래스 또는 구조체는 복사 생성자가 있어야 합니다.

자세한 내용은 [형식 안전 컬렉션을 만드는 방법을](../mfc/how-to-make-a-type-safe-collection.md)참조하세요.

## <a name="see-also"></a>참고 항목

[컬렉션](../mfc/collections.md)
