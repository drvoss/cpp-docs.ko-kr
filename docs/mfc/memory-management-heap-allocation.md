---
title: '메모리 관리: 힙 할당'
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
ms.openlocfilehash: 1f0b07a0a3439faba71078af1e2d7d1559a42b41
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626289"
---
# <a name="memory-management-heap-allocation"></a>메모리 관리: 힙 할당

힙은 프로그램의 메모리 할당 요구에 예약 되어 있습니다. 프로그램 코드와 스택에서 분리 된 영역입니다. 일반적인 C 프로그램은 함수 **malloc** 및 **free** 를 사용 하 여 힙 메모리를 할당 및 할당 취소 합니다. MFC의 디버그 버전은 c + + 기본 제공 operator **new** 및 **delete** 의 수정 된 버전을 제공 하 여 힙 메모리에 개체를 할당 및 할당 취소 합니다.

**Malloc** 및 **free**대신 **new** 및 **delete** 를 사용 하면 메모리 누수를 탐지 하는 데 유용할 수 있는 클래스 라이브러리의 메모리 관리 디버깅 기능을 활용할 수 있습니다. 릴리스 버전의 MFC를 사용 하 여 프로그램을 빌드하면 **new** 및 **delete** 연산자의 표준 버전은 메모리를 할당 및 할당 취소 하는 효율적인 방법을 제공 합니다 (MFC의 릴리스 버전은 이러한 연산자의 수정 된 버전을 제공 하지 않음).

힙에 할당 된 개체의 총 크기는 시스템의 사용 가능한 가상 메모리에 의해서만 제한 됩니다.

## <a name="see-also"></a>참고 항목

[메모리 관리](memory-management.md)
