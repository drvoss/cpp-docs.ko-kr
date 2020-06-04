---
title: C. OpenMP C 및 C++ 문법
ms.date: 01/16/2019
ms.assetid: 97a878ce-1533-47f7-a134-66fcbff48524
ms.openlocfilehash: 85e18161079b49e83cc9fedb3184ee220c889e75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362948"
---
# <a name="c-openmp-c-and-c-grammar"></a>C. OpenMP C 및 C++ 문법

[C.1 표기법](#c1-notation)<br/>
[C.2 규칙](#c2-rules)

## <a name="c1-notation"></a>C.1 표기법

문법 규칙은 비 단말 이름, 콜론, 개별 줄의 대체 대안으로 구성됩니다.

term<sub>opt</sub> 구문 표현은 해당 용어가 대체 내의 선택사항임을 나타냅니다.

*term*<sub>optseq</sub> 구문 표현은 다음 추가 규칙이 있는 *term-seq*<sub>opt</sub>와 동일합니다.

*term-seq*:  
&nbsp;&nbsp;&nbsp;&nbsp;*term*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*term-seq* *term*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*term-seq*   `,` *term*

## <a name="c2-rules"></a>C.2 규칙

표기법은 C 표준의 섹션 6.1에 설명되어 있습니다. 이 문법 부록은 OpenMP C 및 C++ 지시문에 대한 기본 언어 분법의 확장을 보여줍니다.

**/\* C++ (ISO/IEC 14882:1998) \*/**

*statement-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp-directive*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement-seq statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement-seq openmp-directive*

**/\* C90에서 (ISO/IEC 9899:1990) \*/**

*statement-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp-directive*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*문 목록 문*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement-list openmp-directive*

**/\* C99에서 (ISO/IEC 9899:1999) \*/**

*block-item*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp-directive*

**/\* 표준 문 \*/**

*statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp-construct*

*openmp-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sections-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*single-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-for-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-sections-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*master-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*critical-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atomic-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ordered-construct*

*openmp-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*barrier-directive*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*flush-directive*

*구조화 된 블록*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*

*parallel-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*병렬 지시문 구조화 된 블록*

*parallel-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel` *parallel-clause*<sub>optseq</sub> *new-line*

*parallel-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-parallel-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*

*unique-parallel-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `if (` *expression*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `num_threads (` *expression*   `)`

*for-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*지시문에 대한 반복문*

*for-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp for` *for-clause*<sub>optseq</sub> *new-line*

*for-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-for-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*unique-for-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `ordered`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (` *schedule-kind*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (` *schedule-kind*   `,` *expression*   `)`

*schedule-kind*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `static`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `dynamic`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `guided`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `runtime`

*sections-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*섹션 지시문 섹션 범위*

*sections-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp sections` *sections-clause*<sub>optseq</sub> *new-line*

*sections-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*section-scope*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{0} 섹션 시퀀스}*

*section-sequence*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*section-directive*<sub>opt</sub> *structured-block*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*섹션 시퀀스 섹션 지시문 구조화 된 블록*

*section-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp section` *new-line*

*single-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*단일 지시문 구조화 된 블록*

*single-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp single` *single-clause*<sub>optseq</sub> *new-line*

*single-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*parallel-for-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*지시문에 대한 병렬 반복문*

*parallel-for-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel for` *parallel-for-clause*<sub>optseq</sub> *new-line*

*parallel-for-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-parallel-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-for-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*

*parallel-sections-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*병렬 섹션 지시문 섹션 범위*

*parallel-sections-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel sections` *parallel-sections-clause*<sub>optseq</sub> *new-line*

*parallel-sections-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-parallel-clause*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data-clause*

*master-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*master 지시문 구조화 된 블록*

*master-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp master` *new-line*

*critical-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*critical 지시문 구조화 된 블록*

*critical-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp critical` *region-phrase*<sub>opt</sub> *new-line*

*region-phrase*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(identifier)*

*barrier-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp barrier` *new-line*

*atomic-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atomic-directive expression-statement*

*atomic-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp atomic` *new-line*

*flush-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp flush` *flush-vars*<sub>opt</sub> *new-line*

*flush-vars*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(variable-list)*

*ordered-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*순서가 지정된 지시문 구조화된 블록*

*ordered-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp ordered` *new-line*

**/\* 표준 선언 \*/**

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*threadprivate-directive*

*threadprivate-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp threadprivate (` *variable-list*    `)` *new-line*

*data-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `private (` *variable-list*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyprivate (`  *variable-list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `firstprivate (`  *variable-list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `lastprivate (` *variable-list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `shared (` *variable-list*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( shared )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( none )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `reduction (`  *reduction-operator*    `:`  *variable-list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyin (`  *variable-list*    `)`

*reduction-operator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;중 하나입니다.   `+ \* - & ^ | && ||`

**/\* C \*/**

*variable-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*variable-list*   `,` *identifier*

**/\* C++의 경우 \*/**

*variable-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*id-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*variable-list*   `,` *id-expression*
