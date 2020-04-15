---
title: CArchive &lt; &lt; 및 &gt; &gt; 연산자 사용
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 91ea565867cc0cb3b27ad9d5597037b637cb6544
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368969"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive &lt; &lt; 및 &gt; &gt; 연산자 사용

`CArchive`은 \< 파일에서 s뿐만 `CObject`아니라 간단한 데이터 형식을 작성하고 읽기위한 <및 >> 연산자제공.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>아카이브를 통해 파일에 객체를 저장하려면

1. 다음 예제에서는 아카이브를 통해 개체를 파일에 저장하는 방법을 보여 주며 있습니다.

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>이전에 파일에 저장된 값에서 개체를 로드하려면

1. 다음 예제에서는 이전에 파일에 저장된 값에서 개체를 로드하는 방법을 보여 주며 있습니다.

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

일반적으로 DECLARE_SERIALIZE 매크로로 선언해야 하는 -derived 클래스의 `Serialize` `CObject`함수에 있는 아카이브를 통해 파일에서 데이터를 저장하고 로드합니다. `CArchive` 개체에 대한 참조가 `Serialize` 함수에 전달됩니다. 개체의 `IsLoading` 함수를 `CArchive` 호출하여 함수가 `Serialize` 파일에서 데이터를 로드하거나 파일에 데이터를 저장하도록 호출되었는지 확인합니다.

직렬화 할 `Serialize` 수 `CObject`있는 -derived 클래스의 함수는 일반적으로 다음과 같은 형식을 가합니다.

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

위의 코드 템플릿은 AppWizard가 문서의 `Serialize` 함수(파생된 `CDocument`클래스)에 대해 만드는 것과 정확히 동일합니다. 이 코드 템플릿은 다음 예제와 같이 저장 코드와 로드 코드가 항상 병렬이어야 하므로 검토하기 쉬운 코드를 작성하는 데 도움이 됩니다.

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

라이브러리는 첫 ** < ** **>>** 번째 오퍼랜드로 및 연산자와 연산자와 `CArchive` 다음 데이터 형식 및 클래스 유형을 두 번째 카연랜드로 정의합니다.

||||
|-|-|-|
|`CObject*`|**크기** 및`CSize`|**플 로트**|
|**WORD**|`CString`|**포인트** 및`CPoint`|
|`DWORD`|**바이트**|`RECT` 및 `CRect`|
|**double**|**긴**|`CTime` 및 `CTimeSpan`|
|`Int`|**COleCurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
> 아카이브를 `CObject`통해 s를 저장하고 로드하려면 추가적인 고려가 필요합니다. 자세한 내용은 [아카이브를 통해 CObjects 저장 및 로드를](../mfc/storing-and-loading-cobjects-via-an-archive.md)참조하십시오.

**CArchive <\< ** **>>** 연산자는 항상 첫 `CArchive` 번째 피연산자인 개체에 대한 참조를 반환합니다. 이렇게 하면 아래 그림과 같이 연산자 체인을 연결할 수 있습니다.

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>참고 항목

[Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)
