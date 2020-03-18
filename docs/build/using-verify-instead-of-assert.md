---
title: ASSERT 대신 VERIFY 사용
ms.date: 05/06/2019
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
ms.openlocfilehash: bfc0847677ae232fef67ab6200c626472f042bdb
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438615"
---
# <a name="using-verify-instead-of-assert"></a>ASSERT 대신 VERIFY 사용

MFC 응용 프로그램의 디버그 버전을 실행하는 경우는 문제가 없다고 생각됩니다. 그러나 동일한 응용 프로그램의 릴리스 버전이 충돌하고 잘못된 결과가 반환되거나 다른 몇 가지 비정상적인 동작을 수행할 수 있습니다.

이 문제는 ASSERT 문에 중요한 코드를 배치하여 올바르게 수행되는지 확인할 때 발생할 수 있습니다. ASSERT 문은 MFC 프로그램의 릴리스 빌드에서 주석 처리되므로 코드는 릴리스 빌드에서 실행되지 않습니다.

ASSERT를 사용 하 여 함수 호출이 성공 했는지 확인 하는 경우 대신 [VERIFY](../mfc/reference/diagnostic-services.md#verify) 를 사용 하는 것이 좋습니다. VERIFY 매크로는 응용 프로그램의 디버그 및 릴리스 빌드에서 자체 인수를 평가합니다.

또 다른 방법은 함수의 반환 값을 임시 변수에 할당 한 다음 ASSERT 문에서 변수를 테스트 하는 것입니다.

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

이 코드는 MFC 응용 프로그램의 디버그 버전에서 완벽하게 실행됩니다. `calloc( )`에 대 한 호출이 실패 하면 파일 및 줄 번호를 포함 하는 진단 메시지가 표시 됩니다. 그러나 MFC 응용 프로그램의 상용 빌드에서는 다음을 수행 합니다.

- `calloc( )`에 대 한 호출이 발생 하지 않으며 `buf` 초기화 되지 않은 상태로 유지 됩니다.

- `strcpy_s( )` "`Hello, World`"을 임의의 메모리 부분으로 복사 하 여 응용 프로그램의 작동이 중단 되거나 시스템이 응답을 중지 하거나

- `free()` 할당 되지 않은 메모리를 해제 하려고 시도 합니다.

ASSERT를 올바르게 사용 하려면 코드 샘플을 다음과 같이 변경 해야 합니다.

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

## <a name="see-also"></a>참고 항목

[릴리스 빌드 문제 해결](fixing-release-build-problems.md)
