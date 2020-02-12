---
title: '방법: call 및 transformer 클래스에 작업 함수 제공'
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: 4d2b7b3c88b51003a96526ef14d9940a8c26c3b3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142483"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>방법: call 및 transformer 클래스에 작업 함수 제공

이 항목에서는 [concurrency:: call](../../parallel/concrt/reference/call-class.md) 및 [concurrency:: 변환기](../../parallel/concrt/reference/transformer-class.md) 클래스에 작업 함수를 제공 하는 여러 가지 방법을 보여 줍니다.

첫 번째 예제에서는 `call` 개체에 람다 식을 전달 하는 방법을 보여 줍니다. 두 번째 예제에서는 함수 개체를 `call` 개체에 전달 하는 방법을 보여 줍니다. 세 번째 예제에서는 클래스 메서드를 `call` 개체에 바인딩하는 방법을 보여 줍니다.

예시를 위해이 항목의 모든 예제에서는 `call` 클래스를 사용 합니다. `transformer` 클래스를 사용 하는 예제는 [방법: 데이터 파이프라인에서 변환기 사용](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는 `call` 클래스를 사용 하는 일반적인 방법을 보여 줍니다. 이 예제에서는 `call` 생성자에 람다 함수를 전달 합니다.

[!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
13 squared is 169.
```

## <a name="example"></a>예제

다음 예제는 함수 개체 (함수)와 함께 `call` 클래스를 사용 한다는 점을 제외 하 고 이전 예제와 유사 합니다.

[!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]

## <a name="example"></a>예제

다음 예제는 [std:: bind1st](../../standard-library/functional-functions.md#bind1st) 및 [std:: mem_fun](../../standard-library/functional-functions.md#mem_fun) 함수를 사용 하 여 `call` 개체를 클래스 메서드에 바인딩하는 점을 제외 하 고는 이전 예제와 유사 합니다.

함수 호출 연산자, `operator()`대신 `call` 또는 `transformer` 개체를 특정 클래스 메서드에 바인딩해야 하는 경우이 방법을 사용 합니다.

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

다음 예제와 같이 `bind1st` 함수의 결과를 [std:: function](../../standard-library/function-class.md) 개체에 할당 하거나 `auto` 키워드를 사용할 수도 있습니다.

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사 하 여 Visual Studio 프로젝트에 붙여넣거나, `call.cpp` 이름이 지정 된 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.

> **cl.exe/EHsc 호출 .cpp**

## <a name="see-also"></a>참고 항목

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[방법: 데이터 파이프라인에서 transformer 사용](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[call 클래스](../../parallel/concrt/reference/call-class.md)<br/>
[transformer 클래스](../../parallel/concrt/reference/transformer-class.md)
