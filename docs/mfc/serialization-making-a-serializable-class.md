---
title: 'Serialization: Serialize 가능한 클래스 만들기'
ms.date: 11/04/2016
helpviewer_keywords:
- serializable class [MFC]
- DECLARE_SERIAL macro [MFC]
- default constructor [MFC]
- VERSIONABLE_SCHEMA macro [MFC]
- classes [MFC], derived
- IMPLEMENT_SERIAL macro [MFC]
- no-arguments constructor [MFC]
- Serialize method, overriding
- defaults [MFC], constructor
- CObject class [MFC], deriving serializable classes
- constructors [MFC], defining with no arguments
- serialization [MFC], serializable classes
- no default constructor
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
ms.openlocfilehash: 9648bd4f516a5f174534336b1ca3b42bb51ca0c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372713"
---
# <a name="serialization-making-a-serializable-class"></a>Serialization: Serialize 가능한 클래스 만들기

클래스를 직렬화할 수 있도록 하려면 다섯 가지 주요 단계가 필요합니다. 이들은 아래에 나열되어 있으며 다음 섹션에 설명되어 있습니다.

1. [CObject(또는](#_core_deriving_your_class_from_cobject) 일부 클래스에서 파생된 클래스)에서 `CObject`클래스를 파생합니다.

1. [직렬화 멤버 함수 재정의](#_core_overriding_the_serialize_member_function).

1. 클래스 [선언에서 DECLARE_SERIAL 매크로를 사용 합니다.](#_core_using_the_declare_serial_macro)

1. [인수를 하지 않는 생성자 정의](#_core_defining_a_constructor_with_no_arguments).

1. [클래스의 구현 파일에서 IMPLEMENT_SERIAL 매크로를 사용합니다.](#_core_using_the_implement_serial_macro_in_the_implementation_file)

`Serialize` [CArchive의](../mfc/reference/carchive-class.md) >> 및 << 연산자가 아닌 직접 호출하는 경우 직렬화에 마지막 세 단계가 필요하지 않습니다.

## <a name="deriving-your-class-from-cobject"></a><a name="_core_deriving_your_class_from_cobject"></a>CObject에서 클래스 파생

기본 직렬화 프로토콜 및 기능은 `CObject` 클래스에 정의되어 있습니다. 클래스의 다음 선언에 `CObject` `CObject` `CPerson`표시된 대로 클래스에서(또는 파생된 클래스에서) 클래스를 파생하면 `CObject`의 직렬화 프로토콜 및 기능에 액세스할 수 있습니다.

## <a name="overriding-the-serialize-member-function"></a><a name="_core_overriding_the_serialize_member_function"></a>직렬화 멤버 함수 재정의

`CObject` 클래스에 정의된 `Serialize` 멤버 함수는 개체의 현재 상태를 캡처하는 데 필요한 데이터를 실제로 직렬화합니다. 함수에는 `Serialize` 개체 `CArchive` 데이터를 읽고 쓰는 데 사용하는 인수가 있습니다. [CArchive](../mfc/reference/carchive-class.md) 개체에는 데이터 저장(데이터 쓰기) 또는 로드(데이터 읽기)를 `IsStoring` `Serialize` 나타내는 멤버 함수가 있습니다. `IsStoring` 안내선으로 결과를 사용하여 삽입 연산자()를 사용하여 `CArchive` 개체에 개체의 데이터를**<** 삽입하거나 추출 연산자()를**>>** 사용하여 데이터를 추출합니다.

형식 `CString` 및 **WORD의**두 `CObject` 개의 새 멤버 변수에서 파생되고 있는 클래스를 고려합니다. 다음 클래스 선언 조각은 새 멤버 변수와 재정의된 `Serialize` 멤버 함수에 대한 선언을 보여 주십습니다.

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>Serialize 멤버 함수를 재정의하려면

1. 개체의 `Serialize` 상속된 부분이 직렬화되어 있는지 확인하려면 기본 클래스 버전을 호출합니다.

1. 클래스에 특정한 멤버 변수를 삽입하거나 추출합니다.

   삽입 및 추출 연산자는 아카이브 클래스와 상호 작용하여 데이터를 읽고 씁니다. 다음 예제에서는 위에서 `Serialize` 선언된 `CPerson` 클래스에 대해 구현하는 방법을 보여 주며 다음과 같이 보여 주시면 됩니다.

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

[CArchive::Read](../mfc/reference/carchive-class.md#read) 및 [CArchive:Write](../mfc/reference/carchive-class.md#write) 멤버 함수를 사용하여 많은 양의 형식이 사용되지 않은 데이터를 읽고 쓸 수도 있습니다.

## <a name="using-the-declare_serial-macro"></a><a name="_core_using_the_declare_serial_macro"></a>DECLARE_SERIAL 매크로 사용

다음과 같이 직렬화를 지원하는 클래스 선언에 DECLARE_SERIAL 매크로가 필요합니다.

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

## <a name="defining-a-constructor-with-no-arguments"></a><a name="_core_defining_a_constructor_with_no_arguments"></a>인수없이 생성자 정의

MFC는 디serial화(디스크에서 로드됨)로 개체를 다시 만들 때 기본 생성자가 필요합니다. 역직렬화 프로세스는 개체를 다시 만드는 데 필요한 값으로 모든 멤버 변수를 채웁니다.

이 생성자는 공용, 보호 또는 private으로 선언할 수 있습니다. 보호 또는 비공개로 만들면 직렬화 함수에서만 사용되도록 할 수 있습니다. 생성자는 필요한 경우 개체를 삭제할 수 있는 상태에 배치해야 합니다.

> [!NOTE]
> DECLARE_SERIAL 및 IMPLEMENT_SERIAL 매크로를 사용하는 클래스에서 인수가 없는 생성자를 정의하는 것을 잊어버린 경우 IMPLEMENT_SERIAL 매크로가 사용되는 줄에 "기본 생성자를 사용할 수 없음" 컴파일러 경고가 표시됩니다.

## <a name="using-the-implement_serial-macro-in-the-implementation-file"></a><a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a>구현 파일에서 IMPLEMENT_SERIAL 매크로 사용

IMPLEMENT_SERIAL 매크로는 에서 `CObject`직렬화 가능한 클래스를 파생할 때 필요한 다양한 함수를 정의하는 데 사용됩니다. 구현 파일에서 이 매크로를 사용합니다. CPP)를 귀하의 클래스에 사용할 수 있습니다. 매크로에 대한 처음 두 인수는 클래스의 이름과 해당 기본 클래스의 이름입니다.

이 매크로의 세 번째 인수는 스키마 번호입니다. 스키마 번호는 기본적으로 클래스의 개체에 대한 버전 번호입니다. 스키마 번호의 경우 0보다 크거나 같을 정수를 사용합니다. 이 스키마 번호를 데이터베이스 용어와 혼동하지 마십시오.

MFC 직렬화 코드는 메모리로 개체를 읽을 때 스키마 번호를 확인합니다. 디스크에 있는 개체의 스키마 수가 메모리에 있는 클래스의 스키마 번호와 일치하지 않으면 `CArchiveException`라이브러리에서 프로그램이 잘못된 버전의 개체를 읽지 못하도록 합니다.

멤버 함수가 여러 버전(즉, 응용 프로그램의 다른 버전으로 작성된 파일)을 읽을 수 있도록 하려면 VERSIONABLE_SCHEMA 값을 IMPLEMENT_SERIAL 매크로에 대한 인수로 사용할 수 있습니다. *VERSIONABLE_SCHEMA* `Serialize` 사용 정보 및 예제는 `GetObjectSchema` 클래스의 `CArchive`멤버 함수를 참조하십시오.

다음 예제에서는 클래스에 대해 IMPLEMENT_SERIAL `CPerson`사용하는 방법을 보여 `CObject`주며, 이 예제에서는 에서 파생됩니다.

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

직렬화 가능한 클래스가 있으면 [직렬화: 개체 직렬화문서에서](../mfc/serialization-serializing-an-object.md)설명한 대로 클래스의 개체를 직렬화할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Serialization](../mfc/serialization-in-mfc.md)
