---
title: 명시적 인스턴스화
ms.date: 11/04/2016
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
ms.openlocfilehash: dbe8bebf91a174e07c7c5cce8e9caf1cf3432edf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180032"
---
# <a name="explicit-instantiation"></a>명시적 인스턴스화

명시적 인스턴스화를 통해 코드에서 실제로 사용하지 않고 템플릿 기반 클래스 또는 함수의 인스턴스를 만들 수 있습니다. 이는 배포를 위해 템플릿을 사용하는 라이브러리(.lib) 파일을 만들 때 유용하기 때문에 인스턴스화되지 않은 템플릿 정의는 개체 파일(.obj)에 저장되지 않습니다.

이 코드는 **int** 변수 및 6 개 항목에 대 한 `MyStack`를 명시적으로 인스턴스화합니다.

```cpp
template class MyStack<int, 6>;
```

이 명령문은 개체에 대한 스토리지 없이 `MyStack`의 인스턴스를 만듭니다. 모든 멤버에 대한 코드가 생성됩니다.

다음 줄은 생성자 멤버 함수만 명시적으로 인스턴스화합니다.

```cpp
template MyStack<int, 6>::MyStack( void );
```

[함수 템플릿 인스턴스화](../cpp/function-template-instantiation.md)의 예제에 표시 된 것 처럼 특정 형식 인수를 사용 하 여 함수 템플릿을 명시적으로 인스턴스화할 수 있습니다.

**Extern** 키워드를 사용 하 여 멤버의 자동 인스턴스화를 방지할 수 있습니다. 다음은 그 예입니다.

```cpp
extern template class MyStack<int, 6>;
```

마찬가지로 특정 멤버를 외부 및 인스턴스화되지 않음으로 표시할 수 있습니다.

```cpp
extern template MyStack<int, 6>::MyStack( void );
```

**Extern** 키워드를 사용 하 여 컴파일러가 둘 이상의 개체 모듈에서 동일한 인스턴스화 코드를 생성 하지 않도록 할 수 있습니다. 함수가 호출되면 하나 이상의 연결된 모듈에서 지정된 명시적 템플릿 매개 변수를 사용하여 템플릿 함수를 인스턴스화해야 합니다. 그렇지 않으면 프로그램을 빌드할 때 링커 오류가 발생합니다.

> [!NOTE]
>  특수화의 **extern** 키워드는 클래스의 본문 외부에 정의 된 멤버 함수에만 적용 됩니다. 클래스 선언 안에 정의된 함수는 인라인 함수로 간주되며 항상 인스턴스화됩니다.

## <a name="see-also"></a>참고 항목

[함수 템플릿](../cpp/function-templates.md)
