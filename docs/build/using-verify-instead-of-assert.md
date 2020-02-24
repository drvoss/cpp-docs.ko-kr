---
title: ASSERT 대신 VERIFY 사용
ms.date: 05/06/2019
f1_keywords:
- assert
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
ms.openlocfilehash: 83ea24904c75d41f7c9c9b383f8b7cf8c39e328f
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65217675"
---
# <a name="using-verify-instead-of-assert"></a>ASSERT 대신 VERIFY 사용

MFC 응용 프로그램의 디버그 버전을 실행하는 경우는 문제가 없다고 생각됩니다. 그러나 동일한 응용 프로그램의 릴리스 버전이 충돌하고 잘못된 결과가 반환되거나 다른 몇 가지 비정상적인 동작을 수행할 수 있습니다.

이 문제는 ASSERT 문에 중요한 코드를 배치하여 올바르게 수행되는지 확인할 때 발생할 수 있습니다. ASSERT 문은 MFC 프로그램의 릴리스 빌드에서 주석 처리되므로 코드는 릴리스 빌드에서 실행되지 않습니다.

ASSERT를 사용하여 함수 호출이 성공했는지 확인하는 경우 대신 [VERIFY](../mfc/reference/diagnostic-services.md#verify) 사용을 고려해 보세요. VERIFY 매크로는 응용 프로그램의 디버그 및 릴리스 빌드에서 자체 인수를 평가합니다.

다른 좋은 방법은 함수의 반환 값을 임시 변수에 할당 한 다음 ASSERT 문에서 변수를 테스트 합니다.

다음 코드 조각을 확인합니다.

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

이 코드는 MFC 응용 프로그램의 디버그 버전에서 완벽하게 실행됩니다. `calloc( )`에 대한 호출에 실패하면 파일 및 줄 번호를 포함하는 진단 메시지가 표시됩니다. 그러나 MFC 응용 프로그램의 정품 빌드에서:

- `calloc( )`에 대한 호출이 발생하지 않으며, `buf`가 초기화되지 않거나

- `calloc()`에 대한 호출이 발생하지 않으므로 `buf`가 초기화되지 않습니다.

- `strcpy_s()`가 "`Hello, World`"를 임의의 메모리 조각에 복사하여 응용 프로그램이 충돌하거나 시스템이 응답하지 않거나

- `free()`는 할당되지 않은 메모리를 확보하려고 시도합니다.

ASSERT를 올바르게 사용하려면 다음과 같이 코드 샘플을 변경해야 합니다.

```
enum {
    sizeOfBuffer = 20
};
char *buf;
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );
ASSERT( buf != NULL );
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

또는 VERIFY를 대신 사용할 수 있습니다.

```
enum {
    sizeOfBuffer = 20
};
char *buf;
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

## <a name="see-also"></a>참고자료

[릴리스 빌드 문제 해결](fixing-release-build-problems.md)
