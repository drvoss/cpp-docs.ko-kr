---
title: 링커 도구 오류 LNK2004
ms.date: 11/04/2016
f1_keywords:
- LNK2004
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
ms.openlocfilehash: 0d26ab12c5b82d52b7dcbb176d9bfa033d7ddfee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194839"
---
# <a name="linker-tools-error-lnk2004"></a>링커 도구 오류 LNK2004

' 대상 '에 대 한 gp 관련 픽스업 오버플로 약식 섹션 ' section '이 너무 크거나 범위를 벗어났습니다.

섹션이 너무 깁니다.

이 오류를 해결 하려면 #pragma 섹션 ("섹션 이름", 읽기, 쓰기, 긴)을 통해 긴 섹션에 데이터를 명시적으로 배치 하 고 데이터 정의 및 선언에 `__declspec(allocate(".sectionname"))`를 사용 하 여 짧은 섹션의 크기를 줄입니다.  예를 들어 입니다.

```
#pragma section(".data$mylong", read, write, long)
__declspec(allocate(".data$mylong"))
char    rg0[1] = { 1 };
char    rg1[2] = { 1 };
char    rg2[4] = { 1 };
char    rg3[8] = { 1 };
char    rg4[16] = { 1 };
char    rg5[32] = { 1 };
```

또한 논리적으로 그룹화 된 데이터를 8 바이트 보다 큰 데이터 컬렉션으로 이동할 수 있습니다. 그러면 컴파일러가 long 데이터 섹션에서 할당 합니다.  예를 들어 입니다.

```
// from this...
int     w1  = 23;
int     w2 = 46;
int     w3 = 23*3;
int     w4 = 23*4;

// to this...
struct X {
    int     w1;
    int     w2;
    int     w3;
    int     w4;
} x  = { 23, 23*2, 23*3, 23*4 };
```

이 오류 다음에는 심각한 오류 `LNK1165`발생 합니다.
