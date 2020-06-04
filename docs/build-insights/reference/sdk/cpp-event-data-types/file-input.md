---
title: 파일 입력 클래스
description: C++ 빌드 인사이트 SDK FileInput 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileInput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 642236d3e67465ed38508cb24c8cd698ae880065
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324791"
---
# <a name="fileinput-class"></a>파일 입력 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `FileInput` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [FILE_INPUT](../event-table.md#file-input) 이벤트를 일치시키기 위해 사용합니다.

## <a name="syntax"></a>구문

```cpp
class FileInput : public SimpleEvent
{
public:
    enum class Type
    {
        OTHER               = FILE_TYPE_CODE_OTHER,
        OBJ                 = FILE_TYPE_CODE_OBJ,
        EXECUTABLE_IMAGE    = FILE_TYPE_CODE_EXECUTABLE_IMAGE,
        LIB                 = FILE_TYPE_CODE_LIB,
        IMP_LIB             = FILE_TYPE_CODE_IMP_LIB,
        EXP                 = FILE_TYPE_CODE_EXP
    };

    FileInput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>멤버

[SimpleEvent](simple-event.md) 기본 클래스에서 상속된 멤버와 `FileInput` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[파일 입력](#file-input)

### <a name="functions"></a>Functions

[경로](#path)
[유형](#type)

## <a name="fileinput"></a><a name="file-input"></a>파일 입력

```cpp
FileInput(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[FILE_INPUT](../event-table.md#file-input) 이벤트.

## <a name="path"></a><a name="path"></a>경로

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Return Value

입력 파일에 대한 절대 경로입니다.

## <a name="type"></a><a name="type"></a> 형식

```cpp
Type Type() const;
```

### <a name="return-value"></a>Return Value

입력 파일의 형식을 설명하는 코드입니다.

::: moniker-end
