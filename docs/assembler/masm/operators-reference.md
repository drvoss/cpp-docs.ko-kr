---
title: MASM 연산자 참조
ms.date: 07/15/2020
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: c29b173a1dcf29c297e41f136044599fbd5218a5
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446465"
---
# <a name="masm-operators-reference"></a>MASM 연산자 참조

## <a name="arithmetic"></a>산술

:::row:::
   :::column span="":::
      [`*`곱하기](operator-multiply.md)<br/>[`+`추가](operator-add.md)<br/>[`-`(빼기 또는 부정)](operator-subtract-2.md)
   :::column-end:::
   :::column span="":::
      [`.`필드가](operator-dot.md)<br/>[`/`나누면](operator-subtract-1.md)
   :::column-end:::
   :::column span="":::
      [`[]`인덱싱할](operator-brackets.md)<br/>[`MOD`남은](operator-mod.md)
   :::column-end:::
:::row-end:::

## <a name="control-flow"></a>제어 흐름

:::row:::
   :::column span="":::
      [`!`(런타임 논리적 not)](operator-logical-not-masm-run-time.md)<br/>[`!=`(런타임이 같지 않음)](operator-not-equal-masm.md)<br/>[`||`(런타임 논리적 or)](operator-logical-or.md)<br/>[`&&`(런타임 논리적 and)](operator-logical-and-masm-run-time.md)<br/>[`<`(런타임 보다 작음)](operator-less-than-masm-run-time.md)
   :::column-end:::
   :::column span="":::
      [`<=`(런타임이 작거나 같음)](operator-less-or-equal-masm-run-time.md)<br/>[`==`(런타임 같음)](operator-equal-masm-run-time.md)<br/>[`>`(런타임 보다 큼)](operator-greater-than-masm-run-time.md)<br/>[`>=`(런타임 보다 크거나 같음)](operator-greater-or-equal-masm-run-time.md)<br/>[`&`(런타임 비트 and)](operator-bitwise-and.md)
   :::column-end:::
   :::column span="":::
      [`CARRY?`(런타임 운반 테스트)](operator-carry-q.md)<br/>[`OVERFLOW?`(런타임 오버플로 테스트)](operator-overflow-q.md)<br/>[`PARITY?`(런타임 패리티 테스트)](operator-parity-q.md)<br/>[`SIGN?`(런타임 서명 테스트)](operator-sign-q.md)<br/>[`ZERO?`(런타임 제로 테스트)](operator-zero-q.md)
   :::column-end:::
:::row-end:::

## <a name="logical-and-shift"></a>논리적 and 시프트

:::row:::
   :::column span="":::
      [`AND`(비트 and)](operator-and.md)<br/>[`NOT`(비트 not)](operator-not.md)
   :::column-end:::
   :::column span="":::
      [`OR`(비트 or)](operator-or.md)<br/>[`SHL`(왼쪽 시프트 비트)](operator-shl.md)
   :::column-end:::
   :::column span="":::
      [`SHR`(오른쪽 시프트 비트)](operator-shr.md)<br/>[`XOR`(배타적 비트 or)](operator-xor.md)
   :::column-end:::
:::row-end:::

## <a name="macro"></a>매크로

:::row:::
   :::column span="":::
      [`!`(문자 리터럴)](operator-logical-not-masm.md)<br/>[`%`(텍스트로 처리)](operator-percent.md)
   :::column-end:::
   :::column span="":::
      [`;;`(주석으로 처리)](operator-semicolons.md)<br/>[`< >`(한 리터럴로 처리)](operator-literal.md)
   :::column-end:::
   :::column span="":::
      [`& &`(대체 매개 변수 값)](operator-logical-and-masm.md)
   :::column-end:::
:::row-end:::

## <a name="miscellaneous"></a>기타

:::row:::
   :::column span="":::
      [`' '`(문자열로 처리)](operator-single-quote.md)<br/>[`" "`(문자열로 처리)](operator-double-quote.md)<br/>`:`(로컬 레이블 정의)
   :::column-end:::
   :::column span="":::
      `::`(세그먼트 및 오프셋 등록)<br/>`::`(전역 레이블 정의)
   :::column-end:::
   :::column span="":::
      [`;`(주석으로 처리)](operator-semicolon.md)<br/>[`DUP`(반복 선언)](operator-dup.md)
   :::column-end:::
:::row-end:::

## <a name="record"></a>레코드

:::row:::
   :::column span="":::
      [`MASK`(레코드 또는 필드 비트 마스크 가져오기)](operator-mask.md)
   :::column-end:::
   :::column span="2":::
      [`WIDTH`(레코드 또는 필드 너비 가져오기)](operator-width.md)
   :::column-end:::
:::row-end:::

## <a name="relational"></a>관계형

:::row:::
   :::column span="":::
      [`EQ`다릅니다](operator-eq.md)<br/>[`GE`(크거나 같음)](operator-ge.md)
   :::column-end:::
   :::column span="":::
      [`GT`(보다 큼)](operator-gt.md)<br/>[`LE`(작거나 같음)](operator-le.md)
   :::column-end:::
   :::column span="":::
      [`LT`(보다 작음)](operator-lt.md)<br/>[`NE`(같지 않음)](operator-ne.md)
   :::column-end:::
:::row-end:::

## <a name="segment"></a>Segment

:::row:::
   :::column span="":::
      [`:`(세그먼트 재정의)](operator-colon.md)<br/>`::`(세그먼트 및 오프셋 등록)<br/>[`IMAGEREL`(이미지 상대 오프셋)](operator-imagerel.md)
   :::column-end:::
   :::column span="":::
      [`LROFFSET`(로더가 확인 된 오프셋)](operator-lroffset.md)<br/>[`OFFSET`(세그먼트 상대 오프셋)](operator-offset.md)
   :::column-end:::
   :::column span="":::
      [`SECTIONREL`(섹션 상대 오프셋)](operator-sectionrel.md)<br/>[`SEG`(세그먼트 가져오기)](operator-seg.md)
   :::column-end:::
:::row-end:::

## <a name="type"></a>Type

:::row:::
   :::column span="":::
      [`HIGH`(가장 낮은 16 비트의 상위 8 비트)](operator-high.md)<br/>[`HIGH32`(64 비트의 상위 32 비트)](operator-high32.md)<br/>[`HIGHWORD`(가장 낮은 32 비트의 상위 16 비트)](operator-highword.md)<br/>[`LENGTH`(배열의 요소 수)](operator-length.md)<br/>[`LENGTHOF`(배열의 요소 수)](operator-lengthof.md)<br/>[`LOW`(하위 8 비트)](operator-low.md)
   :::column-end:::
   :::column span="":::
      [`LOW32`(낮은 32 비트)](operator-low32.md)<br/>[`LOWWORD`(하위 16 비트)](operator-lowword.md)<br/>[`OPATTR`(인수 형식 정보 가져오기)](operator-opattr.md)<br/>[`PTR`(형식에 대 한 포인터)](operator-ptr.md)<br/>[`SHORT`(간단한 레이블 유형 표시)](operator-short.md)
   :::column-end:::
   :::column span="":::
      [`SIZE`(형식 또는 변수 크기)](operator-size.md)<br/>[`SIZEOF`(형식 또는 변수 크기)](operator-sizeof.md)<br/>[`THIS`(현재 위치)](operator-this.md)<br/>[`TYPE`(식 형식 가져오기)](operator-type.md)<br/>[`.TYPE`(인수 형식 정보 가져오기)](operator-dot-type.md)
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>참조

[Microsoft 매크로 어셈블러 참조](microsoft-macro-assembler-reference.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
