---
title: NMAKE 심각한 오류 U1033
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: 4511b15c84479c3531a3bea85964e2768de0181f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173389"
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE 심각한 오류 U1033

구문 오류: 예기치 않은 ' string '입니다.

문자열은 메이크파일의 올바른 구문의 일부가 아닙니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 인라인 파일의 닫는 꺾쇠 괄호 ( **<<** ) 집합이 줄의 시작 부분에 없으면 다음 오류가 발생 합니다.

    ```
    syntax error : 'EOF' unexpected
    ```

1. 메이크파일의 매크로 정의에 앞의 이름 없이 등호 ( **=** )가 포함 되어 있거나 정의 되는 이름이 nothing으로 확장 되는 매크로 인 경우 다음 오류가 발생 합니다.

    ```
    syntax error : '=' unexpected
    ```

1. 도구의 주석 줄에 세미콜론 ( **;** )이 있으면입니다. INI는 줄의 시작 부분에 있지 않으며 다음과 같은 오류가 발생 합니다.

    ```
    syntax error : ';' unexpected
    ```

1. Word 프로세서에서 메이크파일의 형식이 지정 된 경우 다음 오류가 발생할 수 있습니다.

    ```
    syntax error : ':' unexpected
    ```
