---
title: 용도별 특성
ms.custom: index-page
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: 8be2de10-b1ff-4ca4-a114-75318408593c
ms.openlocfilehash: dcbed019f8cd08ddbf4ab6b4756a59f7fcbabc4b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361333"
---
# <a name="attributes-by-usage"></a>용도별 특성

이 항목에서는 적용되는 C++ 언어 요소에 따른 특성을 나열합니다.

특성이 특성의 범위에 없는 요소 앞에 있으면 특성 블록은 주석으로 처리됩니다.

|attribute|Description|
|---------------|-----------------|
|[모듈 특성](module-attributes.md)|[모듈](module-cpp.md) 특성에 적용됩니다.|
|[인터페이스 특성](interface-attributes.md)|[__interface](../../cpp/interface.md) C++ 키워드에 적용됩니다.|
|[클래스 속성](class-attributes.md)|C++ 키워드에 적용됩니다.|
|[메서드 특성](method-attributes.md)|클래스, 공동 클래스 또는 인터페이스의 메서드에 적용됩니다.|
|[매개 변수 특성](parameter-attributes.md)|클래스 또는 인터페이스에서 메서드의 매개 변수에 적용 됩니다.|
|[데이터 멤버 특성](data-member-attributes.md)|클래스, 공동 클래스 또는 인터페이스의 데이터 멤버에 적용됩니다.|
|[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)|C++ 키워드에 적용됩니다.|
|[배열 특성](array-attributes.md)|배열 또는 `SAFEARRAY`s에 적용됩니다.|
|[독립 실행형 특성](stand-alone-attributes.md)|코드 줄처럼 작동하지만 C++ 키워드에서 작동하지 않습니다. 독립 실행형 특성 문은 줄 끝에 세미콜론이 필요합니다.|
|[사용자 지정 속성](custom-attributes-cpp.md)|사용자가 메타데이터를 확장할 수 있습니다.|

## <a name="module-attributes"></a>모듈 특성

다음 특성은 [모듈](module-cpp.md) 특성에만 적용할 수 있습니다.

|attribute|Description|
|---------------|-----------------|
|[helpstringdll](helpstringdll.md)|문서 문자열 조회(지역화)를 수행하는 데 사용할 DLL 의 이름을 지정합니다.|

## <a name="interface-attributes"></a>인터페이스 특성

다음 특성은 [인터페이스(또는 __interface)](../../cpp/interface.md) C++ 키워드에 적용됩니다.

|attribute|Description|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|COM 인터페이스의 동기 및 비동기 버전을 모두 정의하도록 MIDL 컴파일러를 지시하는 UUID를 지정합니다.|
|[주문](custom-cpp.md)|사용자 고유의 특성을 정의할 수 있습니다.|
|[Dispinterface](dispinterface.md)|.Idl 파일의 인터페이스를 디스패치 인터페이스로 배치합니다.|
|[dual](dual.md)|.idl 파일에 인터페이스를 이중 인터페이스로 배치합니다.|
|[내보내기](export.md)|데이터 구조를 .idl 파일에 배치합니다.|
|[helpcontext](helpcontext.md)|사용자가 도움말 파일에서 이 요소에 대한 정보를 볼 수 있는 컨텍스트 ID를 지정합니다.|
|[Helpfile](helpfile.md)|형식 라이브러리에 대한 도움말 파일의 이름을 설정합니다.|
|[helpstring](helpstring.md)|적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.|
|[helpstringcontext](helpstringcontext.md)|.hlp 또는 .chm 파일에서 도움말 항목의 ID를 지정합니다.|
|[helpstringdll](helpstringdll.md)|문서 문자열 조회(지역화)를 수행하는 데 사용할 DLL 의 이름을 지정합니다.|
|[숨겨진](hidden.md)|항목이 존재하지만 사용자 지향 브라우저에 표시되지 않아야 음을 나타냅니다.|
|[library_block](library-block.md)|.idl 파일의 라이브러리 블록 내에 구문구조를 배치합니다.|
|[로컬](local-cpp.md)|인터페이스 헤더에서 사용할 때 MIDL 컴파일러를 헤더 생성기로 사용할 수 있습니다. 개별 함수에서 사용할 경우 스텁이 생성되지 않는 로컬 프로시저를 지정합니다.|
|[nonextensible](nonextensible.md)|구현에는 `IDispatch` 인터페이스 설명에 나열된 속성 및 메서드만 포함되며 런타임에 추가 멤버로 확장할 수 없음을 지정합니다. 이 특성은 [이중](dual.md) 인터페이스에서만 유효합니다.|
|[Odl](odl.md)|인터페이스를 ODL(개체 설명 언어) 인터페이스로 식별합니다.|
|[개체](object-cpp.md)|사용자 지정 인터페이스를 식별합니다.|
|[oleautomation](oleautomation.md)|인터페이스가 자동화와 호환된다는 것을 나타냅니다.|
|[pointer_default](pointer-default.md)|매개 변수 목록에 나타나는 최상위 포인터를 제외한 모든 포인터에 대한 기본 포인터 특성을 지정합니다.|
|[Ptr](ptr.md)|포인터를 전체 포인터로 지정합니다.|
|[제한](restricted.md)|라이브러리의 구성원을 임의로 호출할 수 없도록 지정합니다.|
|[uuid](uuid-cpp-attributes.md)|라이브러리에 대한 고유 ID를 제공합니다.|

인터페이스를 정의하려면 다음 규칙을 준수해야 합니다.

- 기본 호출 규칙은 [__stdcall.](../../cpp/stdcall.md)

- GUID를 공급하지 않으면 GUID가 제공됩니다.

- 오버로드된 메서드는 허용되지 않습니다.

[uuid](uuid-cpp-attributes.md) 특성을 지정하지 않고 다른 특성 프로젝트에서 동일한 인터페이스 이름을 사용하지 않을 경우 동일한 GUID가 생성됩니다.

## <a name="see-also"></a>참고 항목

[COM 및 .NET의 C++ 특성](cpp-attributes-com-net.md)<br/>
[그룹별 특성](attributes-by-group.md)<br/>
[특성 사전순 참조](attributes-alphabetical-reference.md)
