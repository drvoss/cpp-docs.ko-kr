---
title: 이벤트 스택 클래스
description: C++ 빌드 인사이트 SDK EventStack 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: eaaaedcbf57fdaf8e437a80a7823488febac3e1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324976"
---
# <a name="eventstack-class"></a>이벤트 스택 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `EventStack` [이벤트](event.md) 개체의 컬렉션입니다. C++ 빌드 인사이트 SDK에서 받은 모든 이벤트는 `EventStack` 개체 의 형태로 제공됩니다. 이 스택의 마지막 항목은 현재 처리 중인 이벤트입니다. 마지막 항목 앞에 오는 항목은 현재 이벤트의 상위 계층 구조입니다. C++ 빌드 인사이트에서 사용되는 이벤트 모델에 대한 자세한 내용은 [이벤트 테이블을](../event-table.md)참조하십시오.

## <a name="syntax"></a>구문

```cpp
class EventStack
{
public:
    EventStack(const EVENT_COLLECTION_DATA& data);

    size_t      Size() const;
    RawEvent    Back() const;
    RawEvent    operator[] (size_t index) const;
};
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

[이벤트 스택](#event-stack)

### <a name="functions"></a>Functions

[백](#back)
[연산자[]](#subscript-operator)
[크기](#size)

## <a name="back"></a><a name="back"></a>뒤로

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>Return Value

스택의 마지막 항목을 나타내는 [RawEvent](raw-event.md) 개체입니다. 이벤트 스택의 마지막 항목은 트리거된 이벤트입니다.

## <a name="eventstack"></a><a name="event-stack"></a>이벤트 스택

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>매개 변수

*데이터*\
`EventStack` 빌드되는 원시 데이터입니다.

### <a name="remarks"></a>설명

일반적으로 개체를 직접 생성할 `EventStack` 필요는 없습니다. 분석 또는 리로깅 세션 중에 이벤트가 처리될 때 C++ 빌드 인사이트 SDK에서 제공됩니다.

## <a name="operator"></a><a name="subscript-operator"></a>연산자[]

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>매개 변수

*인덱스*\
이벤트 스택에서 액세스할 요소의 인덱스입니다.

### <a name="return-value"></a>Return Value

이벤트 스택의 *인덱스로* 표시된 위치에 저장된 이벤트를 나타내는 [RawEvent](raw-event.md) 개체입니다.

## <a name="size"></a><a name="size"></a> 크기

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Return Value

이벤트 스택의 크기입니다.

::: moniker-end
