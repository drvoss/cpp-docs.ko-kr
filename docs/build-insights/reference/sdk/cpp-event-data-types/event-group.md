---
title: EventGroup 클래스
description: C++ BUILD Insights SDK eventgroup 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ac8ac70f3fc160714b86dd0c483808a4d06e7699
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334921"
---
# <a name="eventgroup-class"></a>EventGroup 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

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

*Tactivity* 그룹에 포함 된 작업 유형입니다.

## <a name="members"></a>멤버

### <a name="functions"></a>함수

[Back](#back)
[begin](#begin)
[end](#end)
[Front](#front)
[operator []](#subscript-operator)
[크기](#size)

## <a name="back"></a>뒤로

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>반환 값

그룹의 마지막 작업 이벤트에 대 한 참조입니다.

## <a name="begin"></a>시작

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>반환 값

작업 이벤트 그룹의 시작 부분을 가리키는 반복기입니다.

## <a name="end"></a>종단

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>반환 값

작업 이벤트 그룹의 끝을 지난 한 위치를 가리키는 반복기입니다.

## <a name="front"></a>앞뒤

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>반환 값

그룹의 첫 번째 작업 이벤트에 대 한 참조입니다.

## <a name="subscript-operator"></a> operator[]

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>매개 변수

*인덱스*\
작업 이벤트 그룹에서 액세스할 요소의 인덱스입니다.

### <a name="return-value"></a>반환 값

*인덱스*에서 표시 된 위치에 저장 된 이벤트 스택의 이벤트입니다.

## <a name="size"></a>크기가

```cpp
size_t Size() const;
```

### <a name="return-value"></a>반환 값

이벤트 그룹의 크기입니다.

::: moniker-end
