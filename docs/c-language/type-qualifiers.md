---
title: 형식 한정자
ms.date: 11/04/2016
helpviewer_keywords:
- volatile keyword [C], type qualifier
- type qualifiers
- volatile keyword [C]
- qualifiers for types
- const keyword [C]
- memory, access using volatile
- volatile keyword [C], type specifier
ms.assetid: bb4c6744-1dd7-40a8-b4eb-f5585be30908
ms.openlocfilehash: 729e9f65fd1054b8381f45b81e5276846145ebc1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87198725"
---
# <a name="type-qualifiers"></a>형식 한정자

형식 한정자는 두 속성 중 하나를 식별자에 제공합니다. **`const`** 형식 한정자는 개체를 수정할 수 없는 것으로 선언합니다. **`volatile`** 형식 한정자가 선언하는 항목의 값은 해당 항목이 나타나는 프로그램의 제어를 벗어난 요소(예: 동시에 실행되는 스레드)가 올바르게 변경할 수 있습니다.

**`const`** 및 **`volatile`** 이라는 두 형식 한정자는 선언에서 한 번만 나타날 수 있습니다. 형식 한정자는 모든 형식 지정자와 함께 나타날 수 있지만, 여러 항목 선언에서 첫 번째 쉼표 뒤에는 나타날 수 없습니다. 예를 들어 다음 선언은 올바릅니다.

```
typedef volatile int VI;
const int ci;
```

다음 선언은 올바르지 않습니다.

```
typedef int *i, volatile *vi;
float f, const cf;
```

형식 한정자는 식에서 l-value로 식별자에 액세스하는 경우에만 관련이 있습니다. l-value와 식에 대한 자세한 내용은 [L-Value 및 R-Value 식](../c-language/l-value-and-r-value-expressions.md)을 참조하세요.

## <a name="syntax"></a>구문

*type-qualifier*: **constvolatile**

다음은 올바른 **`const`** 및 **`volatile`** 선언입니다.

```
int const *p_ci;       /* Pointer to constant int */
int const (*p_ci);     /* Pointer to constant int */
int *const cp_i;       /* Constant pointer to int */
int (*const cp_i);     /* Constant pointer to int */
int volatile vint;     /* Volatile integer        */
```

배열 형식의 지정에 형식 한정자가 포함된 경우 배열 형식이 아니라 요소가 한정됩니다. 함수 형식의 지정에 한정자가 포함된 경우에는 동작이 정의되어 있지 않습니다. **`volatile`** 또는 **`const`** 는 값의 범위와 개체의 산술 속성에 영향을 미치지 않습니다.

다음 목록에서는 **`const`** 및 **`volatile`** 을 사용하는 방법을 설명합니다.

- **`const`** 키워드를 사용하여 모든 기본 또는 집계 형식을 수정하거나 모든 형식의 개체에 대한 포인터 또는 **`typedef`** 를 수정할 수 있습니다. 항목이 **`const`** 형식 한정자만 사용하여 선언되는 경우 형식은 **const int**로 간주됩니다. **`const`** 변수는 초기화되거나 스토리지의 읽기 전용 영역에 배치될 수 있습니다. **`const`** 키워드를 사용하여 포인터를 **`const`** 로 선언하면 함수가 어떤 식으로든 포인터를 변경하지 못하게 되므로 유용합니다.

- 컴파일러는 프로그램의 어떠한 지점에서도 **`volatile`** 변수의 값을 사용하거나 수정하는 알 수 없는 프로세스에 의해 해당 변수가 액세스될 수 있다고 가정합니다. 따라서 명령줄에 지정된 최적화와 관계없이 각각의 **`volatile`** 변수 할당 또는 참조에 대한 코드가 아무런 영향을 주지 않는 것처럼 보이는 경우에도 생성되어야 합니다.

   **`volatile`** 만 사용되는 경우에는 **`int`** 가 가정됩니다. **`volatile`** 형식 지정자를 사용하여 특별한 메모리 위치에 대한 안정적인 액세스를 제공할 수 있습니다. 신호 처리기, 동시에 실행되는 프로그램 또는 메모리 매핑된 I/O 제어 레지스터와 같은 특수 하드웨어가 액세스하거나 변경할 수 있는 데이터 개체와 함께 **`volatile`** 을 사용합니다. 변수의 수명 동안 변수를 **`volatile`** 로 선언하거나 단일 참조를 **`volatile`** 로 캐스팅할 수 있습니다.

- 항목이 **`const`** 이면서 **`volatile`** 일 수도 있습니다. 이 경우 항목은 자체 프로그램에서 올바르게 수정될 수 없지만 비동기 프로세스에서 수정될 수 있습니다.

## <a name="see-also"></a>참조

[선언 및 형식](../c-language/declarations-and-types.md)
