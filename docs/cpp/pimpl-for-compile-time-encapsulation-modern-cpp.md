---
title: 컴파일 타임 캡슐화에 대한 Pimpl(최신 C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: f1eb06ad3a52be486f085babf699677951b1ee71
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245185"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>컴파일 타임 캡슐화에 대한 Pimpl(최신 C++)

*Pimpl* 는 구현을 최소화 하 고 C++ 인터페이스를 분리 하기 위한 최신 기술입니다. 캡슐화 Pimpl는 짧은 "포인터"를 구현합니다. 개념에 익숙할 수 있지만 명칭 또는 컴파일러 방화벽 관용구와 같은 다른 이름으로 이미 알려져 있습니다.

## <a name="why-use-pimpl"></a>Pimpl 사용 되는 이유

다음은 pimpl 방법으로 소프트웨어 개발 수명 주기를 개선할 수 있는 방법입니다.

- 컴파일 종속성의 최소화입니다.

- 인터페이스 및 구현의 분리.

- 식을.

## <a name="pimpl-header"></a>Pimpl 헤더

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

Pimpl를 통해 계단식 및 불안정 개체 레이아웃을 다시 작성할 필요가 없습니다. (전이적) 인기 있는 형식에 적합 합니다.

## <a name="pimpl-implementation"></a>Pimpl 구현

.Cpp 파일에 `impl` 클래스를 정의 합니다.

```cpp
// my_class.cpp
class my_class::impl {  // defined privately here
  // ... all private data and functions: all of these
  //     can now change without recompiling callers ...
};
my_class::my_class(): pimpl( new impl )
{
  // ... set impl values ...
}
```

## <a name="best-practices"></a>모범 사례

비 throw 교환 특수화에 대 한 지원을 추가할지 여부를 고려 합니다.

## <a name="see-also"></a>참고 항목

[다시 시작C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
