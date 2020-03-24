---
title: Boxing(C++/CLI)
ms.date: 11/04/2016
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
ms.openlocfilehash: df0e220c4f744e78aa5bedce4f956b726f524ff4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208837"
---
# <a name="boxing-ccli"></a>Boxing(C++/CLI)

Boxing은 값 형식을 `object` 형식으로 변환 하거나 값 형식에 의해 구현 되는 임의의 인터페이스 형식으로 변환 하는 프로세스입니다. CLR (공용 언어 런타임)은 값 형식을 boxing 하는 경우 `System.Object` 값을 래핑하고 관리 되는 힙에 저장 합니다. unboxing하면 개체에서 값 형식이 추출됩니다. Boxing은 암시적이며 unboxing은 명시적입니다.

## <a name="related-articles"></a>관련 문서

|제목|설명|
|-----------|-----------------|
|[방법: 명시적으로 boxing 요청](../dotnet/how-to-explicitly-request-boxing.md)|변수에 대해 boxing을 명시적으로 요청 하는 방법을 설명 합니다.|
|[방법: gcnew를 사용하여 값 형식 만들기 및 암시적 boxing 사용](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|`gcnew`를 사용 하 여 관리 되는 가비지 수집 힙에 배치할 수 있는 boxed 값 형식을 만드는 방법을 보여 줍니다.|
|[방법: Unbox](../dotnet/how-to-unbox.md)|값을 unbox 하 고 수정 하는 방법을 보여 줍니다.|
|[표준 변환 및 암시적 boxing](../dotnet/standard-conversions-and-implicit-boxing.md)|Boxing이 필요한 변환에 대해 컴파일러에서 표준 변환을 선택 함을 보여 줍니다.|
|[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Visual C++ 설명서에서 .NET 프로그래밍을 위한 최상위 문서입니다.|
