---
title: Array 및 WriteOnlyArray(C++/CX)
ms.date: 01/22/2017
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
ms.openlocfilehash: e050fad38d4f70c651fc0ebfddb51a33e31da6f3
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032410"
---
# <a name="array-and-writeonlyarray-ccx"></a>Array 및 WriteOnlyArray(C++/CX)

C++/CX 프로그램에서 일반 C 스타일 배열 또는 [std::array를](../standard-library/array-class-stl.md) 자유롭게 사용할 수 [있지만(std::vector는](../standard-library/vector-class.md) 종종 더 나은 선택임에도 불구하고) 메타데이터에 게시된 모든 API에서는 C 스타일 배열 또는 벡터를 [플랫폼::배열](../cppcx/platform-array-class.md) 또는 [플랫폼:WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) 형식으로 변환해야 합니다. [Platform::Array](../cppcx/platform-array-class.md) 형식은 [std::vector](../standard-library/vector-class.md)만큼 효율적이지도 않고 강력하지도 않으므로 배열 요소에 대한 많은 작업을 수행하는 내부 코드에서는 사용하지 않아야 합니다.

다음 배열 형식은 ABI 너머로 전달될 수 있습니다.

1. const Platform::Array^

1. Platform::Array^*

1. Platform::WriteOnlyArray

1. Platform::Array^의 반환 값

이러한 배열 형식을 사용하여 Windows 런타임에 의해 정의된 세 가지 종류의 배열 패턴을 구현합니다.

PassArray 호출이 메서드에 배열을 전달할 때 사용 됩니다. C++ 입력 매개 `const`변수 유형은 [플랫폼::배열](../cppcx/platform-array-class.md)\<T>.

채우기호출이 채울 메서드에 대한 배열을 전달할 때 사용됩니다. C++ 입력 매개 변수 유형은 [플랫폼::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)\<T>.

ReceiveArray 메서드가 할당 하는 배열을 수신 하는 호출자 때 사용 합니다. C++/CX에서는 반환 값에서 배열을 Array^로 반환하거나 Array^* 형식의 out 매개 변수로 반환할 수 있습니다.

## <a name="passarray-pattern"></a>PassArray 패턴

클라이언트 코드에서 C++ 메서드에 배열을 전달하고 이 메서드가 해당 배열을 수정하지 않는 경우 이 메서드는 배열을 const Array^로 받습니다. Windows 런타임 응용 프로그램 바이너리 인터페이스(ABI) 수준에서 이를 PassArray라고 합니다. 다음 예제에서는 JavaScript에서 할당된 배열을 이 배열을 읽는 C++ 함수에 전달하는 방법을 보여 줍니다.

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

다음 코드에서는 C++ 메서드를 보여 줍니다.

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>ReceiveArray 패턴

ReceiveArray 패턴에서 클라이언트 코드는 배열을 선언하며, 배열의 메모리를 할당하고 배열을 초기화하는 메서드에 배열을 전달합니다. C++ 입력 매개 변수 유형은 포인터-모자: `Array<T>^*` 다음 예제에서는 JavaScript에서 배열 개체를 선언한 다음, 메모리를 할당하고 요소를 초기화하여 JavaScript에 반환하는 C++ 함수에 이 개체를 전달하는 방법을 보여 줍니다. JavaScript는 할당된 배열을 반환 값으로 처리하지만 C++ 함수는 이 배열을 출력 매개 변수로 처리합니다.

[!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]

다음 코드에서는 C++ 메서드를 구현하는 두 가지 방법을 보여 줍니다.

[!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]

## <a name="fill-arrays"></a>배열 채우기

호출자에서 배열을 할당하고, 호출을 받는 메서드에서 배열을 초기화하거나 수정하려면 `WriteOnlyArray`를 사용합니다. 다음 예제에서는 `WriteOnlyArray` 를 사용하는 C++ 함수를 구현하고 JavaScript에서 이 함수를 호출하는 방법을 보여 줍니다.

[!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]

다음 코드에서는 C++ 메서드를 구현하는 방법을 보여 줍니다.

[!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]

## <a name="array-conversions"></a>배열 규칙

다음 예제에서는 [Platform::Array](../cppcx/platform-array-class.md) 를 사용하여 다른 종류의 컬렉션을 생성하는 방법을 보여 줍니다.

[!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]

다음 예제에서는 C 스타일 배열에서 [Platform::Array](../cppcx/platform-array-class.md) 를 생성하고 public 메서드에서 반환하는 방법을 보여 줍니다.

[!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]

## <a name="jagged-arrays"></a>가변 배열

Windows 런타임 형식 시스템에서는 가변 배열의 개념이 지원되지 않으므로 public 메서드에서 `IVector<Platform::Array<T>>` 를 반환 값 또는 메서드 매개 변수로 사용할 수 없습니다. ABI 전반에서 가변 배열 또는 시퀀스의 시퀀스를 전달하려면 `IVector<IVector<T>^>`를 사용합니다.

## <a name="use-arrayreference-to-avoid-copying-data"></a>ArrayReference를 사용하여 데이터 복사 방지

데이터가 ABI 전반에서 [Platform::Array](../cppcx/platform-array-class.md)로 전달되고 효율성을 위해 C 스타일 배열에서 해당 데이터를 처리하려는 시나리오에서는 [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) 를 사용하여 추가 복사 작업을 방지할 수 있습니다. [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) 를 `Platform::Array`를 사용하는 매개 변수에 대한 인수로 전달하는 경우 `ArrayReference` 는 지정된 C 스타일 배열에 직접 데이터를 저장합니다. `ArrayReference` 에는 소스 데이터에 대한 잠금이 없으므로 호출이 완료되기 전에 다른 스레드에서 해당 데이터가 수정되거나 삭제되는 경우 결과가 정의되지 않습니다.

다음 코드 조각은 [DataReader](/uwp/api/windows.storage.streams.datareader) 작업의 결과를 `Platform::Array` (일반 패턴)에 복사한 다음 `ArrayReference` 를 대신 사용하여 C 스타일 배열에 직접 데이터를 복사하는 방법을 보여 줍니다.

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>속성으로 배열 노출 방지

일반적으로 ref 클래스에서는 `Platform::Array` 형식을 속성으로 노출하지 않아야 합니다. 클라이언트 코드가 단일 요소에만 액세스하려고 하는 경우에도 전체 배열이 반환되기 때문입니다. public ref 클래스에서 시퀀스 컨테이너를 속성으로 노출해야 하는 경우 [Windows::Foundation::IVector](/uwp/api/windows.foundation.collections.ivector-1) 를 선택하는 것이 더 낫습니다. 메타데이터에 게시되지 않는 전용 또는 내부 API에서는 [std::vector](../standard-library/vector-class.md)와 같은 표준 C++ 컨테이너를 사용하는 것이 좋습니다.

## <a name="see-also"></a>참조

[유형 시스템](../cppcx/type-system-c-cx.md)<br/>
[C++/CX 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
