---
title: 이벤트 그룹 클래스
description: C++ 빌드 인사이트 SDK 이벤트 그룹 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 596c18ca0e9b4d7b26c4ed5209b16871952c4af2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324995"
---
# <a name="eventgroup-class"></a>이벤트 그룹 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

`EventGroup` 클래스 템플릿은 모든 그룹 캡처 클래스의 기본 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <typename TActivity>
class EventGroup;
{
public:
    size_t Size() const;

    const TActivity& operator[](size_t index) const;
    const TActivity& Front() const;
    const TActivity& Back() const;

    std::deque<TActivity>::const_iterator begin() const;
    std::deque<TActivity>::const_iterator end() const;
};
```

### <a name="parameters"></a>매개 변수

*티액티비티* 그룹에 포함된 활동 유형입니다.

## <a name="members"></a>멤버

### <a name="functions"></a>Functions

[백](#back)
[시작](#begin)
[끝](#end)
[프론트](#front)
[연산자[]](#subscript-operator)
[크기](#size)

## <a name="back"></a><a name="back"></a>뒤로

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>Return Value

그룹의 마지막 활동 이벤트에 대한 참조입니다.

## <a name="begin"></a><a name="begin"></a>시작

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>Return Value

활동 이벤트 그룹의 시작 부분을 가리키는 회기입니다.

## <a name="end"></a><a name="end"></a>끝

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>Return Value

활동 이벤트 그룹의 끝을 지나 한 위치를 가리키는 이터레이터입니다.

## <a name="front"></a><a name="front"></a>앞

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>Return Value

그룹의 첫 번째 활동 이벤트에 대한 참조입니다.

## <a name="operator"></a><a name="subscript-operator"></a>연산자[]

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>매개 변수

*인덱스*\
활동 이벤트 그룹에서 액세스할 요소의 인덱스입니다.

### <a name="return-value"></a>Return Value

*인덱스로*표시된 위치에 저장된 이벤트 스택의 이벤트입니다.

## <a name="size"></a><a name="size"></a> 크기

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Return Value

이벤트 그룹의 크기입니다.

::: moniker-end
