---
title: EventStack 클래스
description: C++ BUILD Insights SDK eventstack 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6da2fd25082399b82d788c5d119a39e2f7388714
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334897"
---
# <a name="eventstack-class"></a>EventStack 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`EventStack` 클래스는 [이벤트](event.md) 개체의 컬렉션입니다. C++ BUILD Insights SDK에서 받은 모든 이벤트는 `EventStack` 개체 형식으로 제공 됩니다. 이 스택의 마지막 항목은 현재 처리 중인 이벤트입니다. 마지막 항목 앞에 오는 항목은 현재 이벤트의 부모 계층입니다. 빌드 정보에 C++ 사용 되는 이벤트 모델에 대 한 자세한 내용은 [이벤트 표](../event-table.md)를 참조 하세요.

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

[EventStack](#event-stack)

### <a name="functions"></a>함수

[Back](#back)
[operator []](#subscript-operator)
[크기](#size)

## <a name="back"></a>뒤로

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>반환 값

스택의 마지막 항목을 나타내는 [Rawevent](raw-event.md) 개체입니다. 이벤트 스택의 마지막 항목은 트리거된 이벤트입니다.

## <a name="event-stack"></a>EventStack

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>매개 변수

*데이터*\
`EventStack` 빌드되는 원시 데이터입니다.

### <a name="remarks"></a>주의

일반적으로 `EventStack` 개체를 직접 생성할 필요는 없습니다. 분석 또는 다시 로깅 세션 중에 C++ 이벤트가 처리 될 때 BUILD Insights SDK에서 사용자에 게 제공 됩니다.

## <a name="subscript-operator"></a> operator[]

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>매개 변수

*인덱스*\
이벤트 스택에서 액세스할 요소의 인덱스입니다.

### <a name="return-value"></a>반환 값

이벤트 스택의 *인덱스가* 나타내는 위치에 저장 된 이벤트를 나타내는 [rawevent](raw-event.md) 개체입니다.

## <a name="size"></a>크기가

```cpp
size_t Size() const;
```

### <a name="return-value"></a>반환 값

이벤트 스택의 크기입니다.

::: moniker-end
