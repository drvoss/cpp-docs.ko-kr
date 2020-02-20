---
title: ARM64 예외 처리
description: ARM64의 windows에서 사용 하는 예외 처리 규칙 및 데이터에 대해 설명 합니다.
ms.date: 11/19/2018
ms.openlocfilehash: 2304c04c5e9be31299e30bb48771f7c9777d1cd5
ms.sourcegitcommit: b9aaaebe6e7dc5a18fe26f73cc7cf5fce09262c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504487"
---
# <a name="arm64-exception-handling"></a>ARM64 예외 처리

Windows의 ARM64는 비동기 하드웨어 생성 예외 및 동기 소프트웨어 생성 예외에 대해 동일한 구조화 된 예외 처리 메커니즘을 사용 합니다. 언어별 예외 처리기가 언어 도우미 함수를 사용하여 Windows의 구조적 예외 처리를 기반으로 작성됩니다. 이 문서에서는 ARM64의 Windows에서 발생 하는 예외 처리 및 Microsoft ARM 어셈블러 및 MSVC 컴파일러에 의해 생성 된 코드에서 사용 되는 언어 도우미에 대해 설명 합니다.

## <a name="goals-and-motivation"></a>목표 및 동기

예외 해제 데이터 규칙 및이 설명은 다음 용도로 사용 됩니다.

1. 모든 경우에 코드를 검색 하지 않고 해제할 수 있는 충분 한 설명을 제공 합니다.

   - 코드를 분석 하려면 코드가에서 코드를 호출 해야 합니다. 이렇게 하면 유용한 경우 (추적, 샘플링, 디버깅) 일부 상황에서 해제 되지 않습니다.

   - 코드를 분석 하는 것은 복잡 합니다. 컴파일러는 해제기에서 디코딩할 수 있는 명령만 생성 하도록 주의 해야 합니다.

   - 해제 코드를 사용 하 여 해제를 완전히 설명할 수 없는 경우, 경우에 따라 명령 디코딩으로 대체 해야 합니다. 이렇게 하면 전반적인 복잡성이 증가 하므로이를 피해 야 합니다.

1. 중간 프롤로그 및 중간 에필로그에서 해제를 지원 합니다.

   - 해제는 Windows에서 예외 처리 보다 더 많이 사용 됩니다. 프롤로그 또는 에필로그 코드 시퀀스의 중간에 있는 경우에도 코드가 정확 하 게 해제 될 수 있습니다.

1. 최소한의 공간을 차지 합니다.

   - 해제 코드는 이진 크기를 크게 늘리는 것을 집계 해서는 안 됩니다.

   - 해제 코드는 메모리에서 잠길 수 있으므로 작은 사용 공간은 로드 된 각 이진에 대해 최소한의 오버 헤드를 보장 합니다.

## <a name="assumptions"></a>가정

예외 처리 설명에 이러한 가정이 적용 됩니다.

1. Prologs 및 에필로그는 서로 미러링 하는 경향이 있습니다. 이러한 일반적인 특성을 활용 하 여 해제를 설명 하는 데 필요한 메타 데이터의 크기를 크게 줄일 수 있습니다. 함수 본문 내에서 프롤로그의 작업이 실행 취소 되는지 또는 에필로그의 작업이 앞으로 수행 되는지는 중요 하지 않습니다. 두 작업에서 모두 같은 결과가 생성됩니다.

1. 함수는 전체적으로 비교적 작은 경향이 있습니다. 공간에 대 한 몇 가지 최적화는이 팩트를 사용 하 여 가장 효율적인 데이터 압축을 구현 합니다.

1. 에필로그에는 조건부 코드가 없습니다.

1. 전용 프레임 포인터 레지스터: sp가 프롤로그의 다른 레지스터 (x29)에 저장 된 경우 해당 레지스터는 함수 전체에 그대로 유지 됩니다. 원래 sp가 언제 든 지 복구 될 수 있음을 의미 합니다.

1. Sp가 다른 레지스터에 저장 되지 않는 한 모든 스택 포인터 조작은 프롤로그 및 에필로그 내에서 엄격 하 게 발생 합니다.

1. 스택 프레임 레이아웃은 다음 섹션에 설명 된 대로 구성 됩니다.

## <a name="arm64-stack-frame-layout"></a>ARM64 stack 프레임 레이아웃

![스택 프레임 레이아웃](media/arm64-exception-handling-stack-frame.png "스택 프레임 레이아웃")

프레임 연결 함수의 경우 최적화 고려 사항에 따라 fp 및 lr 쌍을 로컬 변수 영역의 임의 위치에 저장할 수 있습니다. 목표는 프레임 포인터 (x29) 또는 스택 포인터 (sp)를 기반으로 하는 단일 명령으로 도달할 수 있는 지역 수를 최대화 하는 것입니다. 그러나 `alloca` 함수는 연결 되어야 하 고 x29는 스택의 맨 아래를 가리켜야 합니다. 레지스터 쌍 주소 지정 모드를 향상 시킬 수 있도록 하려면 비휘발성 등록 저장 영역이 로컬 영역 스택의 맨 위에 배치 됩니다. 가장 효율적인 여러 프롤로그 시퀀스를 보여 주는 예제는 다음과 같습니다. 명확 하 고 캐시 집약성을 높이기 위해 모든 정식 프롤로그에 호출 수신자 저장 레지스터를 저장 하는 순서는 "증가" 됩니다. 아래 `#framesz`는 전체 스택의 크기 (alloca 영역 제외)를 나타냅니다. `#localsz` 및 `#outsz`는 로컬 영역 크기 (\<x29, lr > 쌍의 저장 영역 포함)와 나가는 매개 변수 크기를 각각 나타냅니다.

1. 체인, #localsz \<= 512

    ```asm
        stp    x19,x20,[sp,#-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,#16]            // save in FP regs (optional)
        stp    x0,x1,[sp,#32]            // home params (optional)
        stp    x2,x3,[sp,#48]
        stp    x4,x5,[sp,#64]
        stp    x6,x7,[sp,#72]
        stp    x29,lr,[sp,#-localsz]!   // save <x29,lr> at bottom of local area
        mov    x29,sp                   // x29 points to bottom of local
        sub    sp,sp,#outsz             // (optional for #outsz != 0)
    ```

1. 체인, #localsz > 512

    ```asm
        stp    x19,x20,[sp,#-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,#16]            // save in FP regs (optional)
        stp    x0,x1,[sp,#32]            // home params (optional)
        stp    x2,x3,[sp,#48]
        stp    x4,x5,[sp,#64]
        stp    x6,x7,[sp,#72]
        sub    sp,sp,#(localsz+outsz)   // allocate remaining frame
        stp    x29,lr,[sp,#outsz]       // save <x29,lr> at bottom of local area
        add    x29,sp,#outsz            // setup x29 points to bottom of local area
    ```

1. 연결 되지 않은 리프 함수 (lr 저장 되지 않음)

    ```asm
        stp    x19,x20,[sp,#-80]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    x21,x22,[sp,#16]
        str    x23,[sp,#32]
        stp    d8,d9,[sp,#40]           // save FP regs (optional)
        stp    d10,d11,[sp,#56]
        sub    sp,sp,#(framesz-80)      // allocate the remaining local area
    ```

   모든 로컬은 SP를 기준으로 액세스 됩니다. \<x29, lr >는 이전 프레임을 가리킵니다. 프레임 크기 \<= 512, "sub sp, ..." regs 저장 된 영역이 스택의 맨 아래로 이동 하는 경우에는 최적화할 수 있습니다. 단점은 위의 다른 레이아웃과 일치 하지 않는 것이 고, 저장 된 regs는 쌍으로 구분 되는 범위와 사전 및 사후 인덱싱된 오프셋 주소 지정 모드의 일부를 차지 합니다.

1. 연결 되지 않은 리프가 아닌 함수 (lr은 Int로 저장 된 영역에 저장 됨)

    ```asm
        stp    x19,x20,[sp,#-80]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    x21,x22,[sp,#16]         // ...
        stp    x23,lr,[sp,#32]          // save last Int reg and lr
        stp    d8,d9,[sp,#48]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,#64]         // ...
        sub    sp,sp,#(framesz-80)      // allocate the remaining local area
    ```

   또는 짝수 수의 저장 된 Int 레지스터를 사용 하 여

    ```asm
        stp    x19,x20,[sp,#-80]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    x21,x22,[sp,#16]         // ...
        str    lr,[sp,#32]              // save lr
        stp    d8,d9,[sp,#40]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,#56]         // ...
        sub    sp,sp,#(framesz-80)      // allocate the remaining local area
    ```

   X19만 저장 됨:

    ```asm
        sub    sp,sp,#16                // reg save area allocation*
        stp    x19,lr,[sp]              // save x19, lr
        sub    sp,sp,#(framesz-16)      // allocate the remaining local area
    ```

   미리 인덱싱된 reg를 해제 코드로 표현할 수 없기 때문에 reg 저장 영역 할당은 stp로 중첩 되지 않습니다. \*

   모든 로컬은 SP를 기준으로 액세스 됩니다. \<x29 >는 이전 프레임을 가리킵니다.

1. 체인, #framesz \<= 512, #outsz = 0

    ```asm
        stp    x29,lr,[sp,#-framesz]!       // pre-indexed, save <x29,lr>
        mov    x29,sp                       // x29 points to bottom of stack
        stp    x19,x20,[sp,#(framesz-32)]   // save INT pair
        stp    d8,d9,[sp,#(framesz-16)]     // save FP pair
    ```

   위의 첫 번째 프롤로그 예제와 비교할 때, 여기서의 이점은 하나의 스택 할당 명령 후에 모든 레지스터 저장 명령을 실행할 준비가 되었다는 것입니다. 즉, 명령 수준 병렬 처리를 방지 하는 sp에 대 한 종속성이 없습니다.

1. 연결 된, 프레임 크기 > 512 (alloca 없는 함수의 경우 선택 사항)

    ```asm
        stp    x29,lr,[sp,#-80]!            // pre-indexed, save <x29,lr>
        stp    x19,x20,[sp,#16]             // save in INT regs
        stp    x21,x22,[sp,#32]             // ...
        stp    d8,d9,[sp,#48]               // save in FP regs
        stp    d10,d11,[sp,#64]
        mov    x29,sp                       // x29 points to top of local area
        sub    sp,sp,#(framesz-80)          // allocate the remaining local area
    ```

   최적화를 위해 x29는 로컬 영역에서 임의의 위치에 배치 하 여 "reg-pair" 및 사전/사후 인덱스 주소 지정 모드에 대 한 향상 된 범위를 제공할 수 있습니다. 프레임 포인터 아래에 있는 로컬은 SP를 기준으로 액세스할 수 있습니다.

1. Alloca ()를 사용 하거나 사용 하지 않고 체인, 프레임 크기 > 4K

    ```asm
        stp    x29,lr,[sp,#-80]!            // pre-indexed, save <x29,lr>
        stp    x19,x20,[sp,#16]             // save in INT regs
        stp    x21,x22,[sp,#32]             // ...
        stp    d8,d9,[sp,#48]               // save in FP regs
        stp    d10,d11,[sp,#64]
        mov    x29,sp                       // x29 points to top of local area
        mov    x15,#(framesz/16)
        bl     __chkstk
        sub    sp,sp,x15,lsl#4              // allocate remaining frame
                                            // end of prolog
        ...
        sub    sp,sp,#alloca                // more alloca() in body
        ...
                                            // beginning of epilog
        mov    sp,x29                       // sp points to top of local area
        ldp    d10,d11,[sp,#64]
        ...
        ldp    x29,lr,[sp],#80              // post-indexed, reload <x29,lr>
    ```

## <a name="arm64-exception-handling-information"></a>ARM64 예외 처리 정보

### <a name="pdata-records"></a>.pdata 레코드

.Pdata 레코드는 PE 이진의 모든 스택 조작 함수를 설명 하는 고정 길이 항목의 정렬 된 배열입니다. "스택 조작" 이란 중요 합니다. 로컬 저장소를 필요로 하지 않는 리프 함수 이며 비휘발성 레지스터를 저장/복원할 필요가 없습니다. .pdata 레코드는 필요 하지 않습니다. 이러한 레코드는 공간을 절약 하기 위해 명시적으로 생략 해야 합니다. 이러한 함수 중 하나에서 해제 하는 경우에는 해당 호출자로 이동 하기 위해 LR에서 직접 반환 주소를 가져올 수 있습니다.

ARM64에 대 한 각 .pdata 레코드의 길이는 8 바이트입니다. 각 레코드의 일반 형식은 함수의 32 비트 RVA를 첫 번째 단어에서 시작 하 고, .xdata 블록에 대 한 포인터 또는 정식 함수 해제 시퀀스를 설명 하는 압축 된 단어를 포함 하는 두 번째 단어를 배치 합니다.

![.pdata 레코드 레이아웃](media/arm64-exception-handling-pdata-record.png ".pdata 레코드 레이아웃")

필드는 다음과 같습니다.

- **함수 시작 rva** 는 함수 시작의 32 비트 rva입니다.

- **플래그** 는 두 번째 .pdata 단어의 나머지 30 비트를 해석 하는 방법을 나타내는 2 비트 필드입니다. **플래그가** 0 이면 나머지 비트는 **예외 정보 RVA** 를 형성 합니다 (두 개의 가장 낮은 비트가 암시적으로 0 인 경우). **플래그가** 0이 아닌 경우 나머지 비트는 **압축 된 해제 데이터** 구조를 형성 합니다.

- **예외 정보 RVA** 는 .xdata 섹션에 저장 된 가변 길이 예외 정보 구조의 주소입니다. 이 데이터는 4비트 단위로 정렬되어야 합니다.

- **압축 된 해제 데이터** 는 정규 형식으로 가정 하 여 함수에서 해제 하는 데 필요한 작업에 대 한 압축 된 설명입니다. 이 경우에는 .xdata 레코드가 필요하지 않습니다.

### <a name="xdata-records"></a>. .xdata 레코드

압축된 해제 형식만으로는 함수 해제를 설명하는 데 부족한 경우에는 가변 길이 .xdata 레코드를 만들어야 합니다. 이 레코드의 주소는 .pdata 레코드의 두 번째 단어에 저장됩니다. .Xdata의 형식은 압축 된 가변 길이 단어 집합입니다.

![. .xdata 레코드 레이아웃](media/arm64-exception-handling-xdata-record.png ". .xdata 레코드 레이아웃")

이 데이터는 네 개의 섹션으로 구분 됩니다.

1. 구조체의 전체 크기를 설명 하 고 키 함수 데이터를 제공 하는 1 또는 2 단어 헤더입니다. 두 번째 단어는 **에필로그 개수** 와 **코드 단어** 필드가 모두 0으로 설정 된 경우에만 존재 합니다. 헤더에는 다음과 같은 비트 필드가 있습니다.

   a. **함수 길이** 는 18 비트 필드입니다. 함수의 전체 길이 (바이트)를 4로 나눈 값을 나타냅니다. 함수가 1M 보다 큰 경우에는 여러 .pdata 및. .xdata 레코드를 사용 하 여 함수를 설명 해야 합니다. 자세한 내용은 [Large 함수](#large-functions) 섹션을 참조 하세요.

   b. **Vers** 는 2 비트 필드입니다. .Xdata의 버전을 설명 합니다. 현재 버전 0만 정의 되었으므로 1-3 값이 허용 되지 않습니다.

   c. **X** 는 1 비트 필드입니다. 예외 데이터의 유무 (1) 또는 부재 (0)를 나타냅니다.

   . **E** 는 1 비트 필드입니다. 이는 단일 에필로그를 설명 하는 정보가 나중에 추가 범위 단어 (0)를 요구 하는 대신 헤더 (1)로 압축 됨을 나타냅니다.

   e. **에필로그 개수** 는 **E** 비트의 상태에 따라 두 가지 의미를 갖는 5 비트 필드입니다.

      1. **E** 가 0 인 경우 섹션 2에 설명 된 총 에필로그 범위의 수를 지정 합니다. 함수에 범위가 31 개 이상 있는 경우 **코드 단어** 필드를 0으로 설정 하 여 확장명 단어가 필요 함을 나타내야 합니다.

      2. **E** 가 1 인 경우이 필드는 하나를 설명 하는 첫 번째 해제 코드의 인덱스를 지정 하 고 에필로그만을 지정 합니다.

   f. **코드 단어** 는 섹션 3의 모든 해제 코드를 포함 하는 데 필요한 32 비트 단어 수를 지정 하는 5 비트 필드입니다. 31 개가 넘는 단어가 필요한 경우 (즉, 해제 코드 바이트 수가 124 개를 초과 하는 경우)이 필드는 확장 단어가 필요 함을 나타내려면 0 이어야 합니다.

   g. **확장 된 에필로그 수** 및 **확장 코드 단어** 는 각각 16 비트 및 8 비트 필드입니다. 비정상적으로 많은 수의 에필로그를 인코딩하는 데 더 많은 공간을 제공 하거나 비정상적으로 많은 수의 해제 코드 단어를 제공 합니다. 이러한 필드를 포함 하는 확장 단어는 첫 번째 헤더 단어의 **에필로그 개수** 와 **코드 단어** 필드가 모두 0 인 경우에만 존재 합니다.

1. **에필로그 수가** 0이 아닌 경우에는 한 단어로 압축 된 에필로그 범위에 대 한 정보 목록이 헤더 및 선택적인 확장 헤더 뒤에 나옵니다. 이는 시작 오프셋이 늘어나는 순서로 저장 됩니다. 각 범위에는 다음 비트가 포함 됩니다.

   a. **에필로그 시작 오프셋** 은 함수의 시작 부분을 기준으로 하 여 4로 나눈 오프셋 (바이트)을 포함 하는 18 비트 필드입니다.

   b. **Res** 는 향후 확장을 위해 예약 된 4 비트 필드입니다. 해당 값은 0이어야 합니다.

   c. **에필로그 시작 인덱스** 는 10 비트 필드입니다 ( **확장 된 코드 단어**보다 2 비트 더 큼). 이는이 에필로그를 설명 하는 첫 번째 해제 코드의 바이트 인덱스를 나타냅니다.

1. 에필로그 범위 목록에는 해제 코드를 포함 하는 바이트 배열이 제공 된 후 이후 단원에서 자세히 설명 합니다. 이 배열은 가장 가까운 전체 단어 경계 끝에 채워집니다. 해제 코드는이 배열에 기록 됩니다. 함수 본문에 가장 가까운 것으로 시작 하 여 함수의 가장자리로 이동 합니다. 각 해제 코드에 대 한 바이트는 빅 endian 순서로 저장 되므로, 작업 및 나머지 코드의 길이를 식별 하는 가장 중요 한 바이트부터 시작 하 여 직접 페치할 수 있습니다.

1. 마지막으로, 해제 코드 바이트 이후에 헤더의 **X** 비트가 1로 설정 된 경우는 예외 처리기 정보를 제공 합니다. 예외 처리기 자체의 주소를 제공 하는 단일 **예외 처리기 RVA** 로 구성 됩니다. 예외 처리기에서 요구 하는 가변 길이 데이터를 즉시 따릅니다.

.Xdata 레코드는 처음 8 바이트를 인출 하 고,이를 사용 하 여 레코드의 전체 크기를 계산 하 고, 다음에 오는 가변 크기 예외 데이터의 길이를 뺀 값을 사용 하도록 설계 되었습니다. 다음 코드 조각에서는 레코드 크기를 계산 합니다.

```cpp
ULONG ComputeXdataSize(PULONG *Xdata)
{
    ULONG EpilogScopes;
    ULONG Size;
    ULONG UnwindWords;

    if ((Xdata[0] >> 27) != 0) {
        Size = 4;
        EpilogScopes = (Xdata[0] >> 22) & 0x1f;
        UnwindWords = (Xdata[0] >> 27) & 0x0f;
    } else {
        Size = 8;
        EpilogScopes = Xdata[1] & 0xffff;
        UnwindWords = (Xdata[1] >> 16) & 0xff;
    }

    Size += 4 * EpilogScopes;
    Size += 4 * UnwindWords;
    if (Xdata[0] & (1 << 20)) {
        Size += 4;        // exception handler RVA
    }
    return Size;
}
```

프롤로그와 각 에필로그에는 해제 코드에 대 한 자체 인덱스가 있지만 테이블 간에 테이블이 공유 됩니다. 모두 동일한 코드를 공유할 수 있는 모든 것이 가능 하 고 전혀 그렇지 않습니다. 예제 [는 예제 섹션의](#examples) 예제 2를 참조 하세요. 특히, 지정할 수 있는 가장 큰 인덱스가 255 이므로 특정 함수에 대 한 해제 코드의 총 수를 제한 하기 때문에 컴파일러 작성자는이 경우를 최적화 해야 합니다.

### <a name="unwind-codes"></a>해제 코드

해제 코드의 배열은 작업을 실행 취소 해야 하는 순서에 따라 프롤로그의 효과를 실행 취소 하는 방법을 정확 하 게 설명 하는 시퀀스의 풀입니다. 해제 코드는 바이트 문자열로 인코드된 작은 명령 집합으로 간주할 수 있습니다. 실행이 완료 되 면 호출 하는 함수에 대 한 반환 주소는 lr 레지스터에 있습니다. 그리고 모든 비휘발성 레지스터는 함수가 호출 될 때 해당 값으로 복원 됩니다.

예외가 함수 본문 내 에서만 발생 하 고 프롤로그 나 에필로그 내에서 발생 하지 않을 것으로 보장 되는 경우에는 하나의 시퀀스만 필요 합니다. 그러나 Windows 해제 모델에서는 코드를 부분적으로 실행 된 프롤로그 나 에필로그 내에서 해제할 수 있어야 합니다. 이러한 요구 사항을 충족 하기 위해 해제 코드는 신중 하 게 설계 되었으므로 프롤로그 및 에필로그의 각 관련 opcode에 1:1을 명확 하 게 매핑할 수 있습니다. 이 디자인에는 다음과 같은 여러 가지 의미가 있습니다.

1. 해제 코드의 수를 계산 하 여 프롤로그 및 에필로그의 길이를 계산할 수 있습니다.

1. 에필로그 범위가 시작 된 후의 명령 수를 계산 하면 해당 해제 코드 수를 건너뛸 수 있습니다. 그런 다음 나머지 시퀀스를 실행 하 여 에필로그에서 수행 하는 부분적으로 실행 된 해제를 완료할 수 있습니다.

1. 프롤로그의 끝 이전에 명령 수를 계산 하면 해당 해제 코드 수를 건너뛸 수 있습니다. 그런 다음 나머지 시퀀스를 실행 하 여 실행이 완료 된 프롤로그 부분만 실행 취소할 수 있습니다.

해제 코드는 아래 표에 따라 인코딩됩니다. 모든 해제 코드는 큰 스택을 할당 하는 것을 제외 하 고 단일/더블 바이트입니다. 완전히 21 개의 해제 코드가 있습니다. 각 해제 코드는 프롤로그/에필로그에서 정확히 하나의 명령만 매핑하여 부분적으로 실행 된 프롤로그 및 에필로그를 해제할 수 있습니다.

|해제 코드|비트 and 해석|
|-|-|
|`alloc_s`|000xxxxx: 크기 \< 512 (2 ^ 5 * 16)의 작은 스택을 할당 합니다.|
|`save_r19r20_x`|    001zzzzz: \<x19, x20 > 쌍 `[sp-#Z*8]!`, 미리 인덱싱된 오프셋 > =-248 |
|`save_fplr`|        01zzzzzz: \<x29, lr > 쌍을 `[sp+#Z*8]`, 오프셋 \<= 504에 저장 합니다. |
|`save_fplr_x`|        10zzzzzz: `[sp-(#Z+1)*8]!`에 \<x29, lr > 쌍을 저장 하 고, 미리 인덱싱된 오프셋 > =-512 |
|`alloc_m`|        11000xxx'xxxxxxxx: 크기가 16k (2 ^ 11 * 16) \< 큰 스택을 할당 합니다. |
|`save_regp`|        110010xx'xxzzzzzz: `[sp+#Z*8]`에 x (19 + #X) 쌍을 저장 합니다. 오프셋 \<= 504 |
|`save_regp_x`|        110011xx'xxzzzzzz: `[sp-(#Z+1)*8]!`, 인덱싱된 오프셋 > =-512에 쌍 x (19 + #X)를 저장 합니다. |
|`save_reg`|        110100xx'xxzzzzzz: `[sp+#Z*8]`에서 reg x (19 + #X)를 저장 합니다. 오프셋 \<= 504 |
|`save_reg_x`|        1101010x'xxxzzzzz: `[sp-(#Z+1)*8]!`, 미리 인덱싱된 오프셋 > =-256에 reg x (19 + #X)를 저장 합니다. |
|`save_lrpair`|         1101011x'xxzzzzzz: \<x (19 + 2 * #X), lr > at `[sp+#Z*8]`, 오프셋 \<= 504을 저장 합니다. |
|`save_fregp`|        1101100x'xxzzzzzz: `[sp+#Z*8]`, offset \<= 504에 쌍 d (8 + #X)를 저장 합니다. |
|`save_fregp_x`|        1101101x'xxzzzzzz: d (8 + #X) 쌍을 저장 `[sp-(#Z+1)*8]!`, 미리 인덱싱된 오프셋 > =-512 |
|`save_freg`|        1101110x'xxzzzzzz: `[sp+#Z*8]`, offset \<= 504에 reg d (8 + #X)를 저장 합니다. |
|`save_freg_x`|        11011110 ' xxxzzzzz: `[sp-(#Z+1)*8]!`, 미리 인덱싱된 오프셋 > =-256에 reg d (8 + #X)를 저장 합니다. |
|`alloc_l`|         11100000 ' xxxxxxxx'xxxxxxxx'xxxxxxxx: \< 크기가 256M 인 큰 스택을 할당 합니다 (2 ^ 24 * 16). |
|`set_fp`|        11100001: x29: `mov x29,sp` 설정: |
|`add_fp`|        11100010 ' xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx: set up x29 with: `add x29,sp,#x*8` |
|`nop`|            11100011: 해제 작업은 필요 하지 않습니다. |
|`end`|            11100100: 해제 코드의 끝입니다. 에필로그에서 ret를 의미 합니다. |
|`end_c`|        11100101: 현재 연결 된 범위에서 해제 코드의 끝입니다. |
|`save_next`|        11100110: 다음 비휘발성 Int 또는 FP 레지스터 쌍을 저장 합니다. |
|`arithmetic(add)`|    11100111 ' 000zxxxx: 추가 쿠키 reg (z)를 lr에 추가 (0 = x28, 1 = sp); `add lr, lr, reg(z)` |
|`arithmetic(sub)`|    11100111의 ' 001zxxxx: 하위 쿠키 reg (z) from lr (0 = x28, 1 = sp); `sub lr, lr, reg(z)` |
|`arithmetic(eor)`|    11100111 ' 010zxxxx: extended-originator-record lr with cookie reg (z) (0 = x28, 1 = sp); `eor lr, lr, reg(z)` |
|`arithmetic(rol)`|    11100111 ' 0110xxxx: x28 (쿠키 .reg)를 사용 하 여 lr의 시뮬레이션 된 역할 (); xip0 = neg x28; `ror lr, xip0` |
|`arithmetic(ror)`|    11100111 ' 100zxxxx: ror lr과 쿠키 reg (z) (0 = x28, 1 = sp); `ror lr, lr, reg(z)` |
| |            11100111: xxxz----: ---- reserved |
| |              11101xxx: 아래에서 asm 루틴에 대해서만 생성 된 사용자 지정 스택 사례에 대해 예약 됨 |
| |              11101000: MSFT_OP_TRAP_FRAME에 대 한 사용자 지정 스택 |
| |              11101001: MSFT_OP_MACHINE_FRAME에 대 한 사용자 지정 스택 |
| |              11101010: MSFT_OP_CONTEXT에 대 한 사용자 지정 스택 |
| |              11101100: MSFT_OP_CLEAR_UNWOUND_TO_CALL에 대 한 사용자 지정 스택 |
| |              1111xxxx: reserved |

여러 바이트를 포함 하는 큰 값에 대 한 지침에서는 가장 중요 한 비트가 먼저 저장 됩니다. 이 디자인을 사용 하면 코드의 첫 번째 바이트만 조회 하 여 해제 코드의 총 크기 (바이트)를 찾을 수 있습니다. 각 해제 코드는 프롤로그 또는 에필로그의 명령에 정확히 매핑되므로 프롤로그 또는 에필로그의 크기를 계산할 수 있습니다. 시퀀스의 시작 부분부터 끝까지 탐색 하 고 조회 테이블 또는 유사한 장치를 사용 하 여 해당 opcode의 길이를 확인할 수 있습니다.

사후 인덱싱된 오프셋 주소 지정은 프롤로그에서 허용 되지 않습니다. 모든 오프셋 범위 (#Z)는 `save_r19r20_x`를 제외 하 고 모든 저장 영역 (10 개 Int 레지스터 + 8 FP 레지스터 + 8 입력 레지스터)에 대해 248이 충분 한 .STP/STR 주소 지정 인코딩과 일치 합니다.

`save_next`은 `save_regp`, `save_regp_x`, `save_fregp`, `save_fregp_x`, `save_r19r20_x`또는 다른 `save_next`에 대 한 저장 Int 또는 FP 휘발성 레지스터 쌍을 따라야 합니다. 다음 레지스터 쌍을 "증가" 순서 대로 다음 16 바이트 슬롯에 저장 합니다. `save_next`는 마지막 Int 레지스터 쌍을 나타내는 `save-next` 뒤에 오는 첫 번째 FP 레지스터 쌍을 참조 합니다.

일반 반환 및 점프 명령의 크기는 동일 하기 때문에 마무리 호출 시나리오에는 분리 된 `end` 해제 코드를 사용할 필요가 없습니다.

`end_c`는 최적화를 위해 인접 하지 않은 함수 조각을 처리 하도록 설계 되었습니다. 현재 범위에 있는 해제 코드의 끝을 표시 하는 `end_c` 다음에 실제 `end`으로 종료 된 해제 코드의 다른 시리즈를 사용 해야 합니다. `end_c`와 `end` 사이의 해제 코드는 부모 지역 ("가상" 프롤로그)의 프롤로그 작업을 나타냅니다.  자세한 내용과 예제는 아래 섹션에 설명 되어 있습니다.

### <a name="packed-unwind-data"></a>압축 된 해제 데이터

프롤로그 및 에필로그가 아래에 설명 된 정규 형식을 따르는 함수의 경우 압축 된 해제 데이터를 사용할 수 있습니다. .Xdata 레코드를 완전히 필요로 하지 않으며 해제 데이터를 제공 하는 비용을 크게 줄일 수 있습니다. 정식 프롤로그 및 에필로그는 간단한 함수의 일반적인 요구 사항을 충족 하도록 설계 되었습니다. 하나는 예외 처리기가 필요 하지 않으며,이는 설정 및 해체 작업을 표준 순서로 수행 합니다.

압축 해제 데이터가 포함 된 .pdata 레코드의 형식은 다음과 같습니다.

![압축 된 해제 데이터가 있는 .pdata 레코드](media/arm64-exception-handling-packed-unwind-data.png "압축 된 해제 데이터가 있는 .pdata 레코드")

필드는 다음과 같습니다.

- **함수 시작 rva** 는 함수 시작의 32 비트 rva입니다.
- **플래그** 는 위에서 설명한 대로 2 비트 필드 이며 다음과 같은 의미를 갖습니다.
  - 00 = 압축 된 해제 데이터를 사용 하지 않습니다. 나머지 비트가 .xdata 레코드를 가리킵니다.
  - 01 = 범위 시작과 끝에서 단일 프롤로그 및 에필로그에 사용 되는 압축 해제 데이터
  - 10 = 프롤로그 및 에필로그 없이 코드에 사용 되는 압축 된 해제 데이터입니다. 구분 된 함수 세그먼트를 설명 하는 데 유용 합니다.
  - 11 = 예약된 비트입니다.
- **함수 길이** 는 전체 함수의 길이 (바이트)를 4로 나눈 값을 제공 하는 11 비트 필드입니다. 함수가 8k 보다 큰 경우 .xdata 레코드를 대신 사용 해야 합니다.
- **프레임 크기** 는이 함수에 할당 된 스택의 바이트 수를 16으로 나눈 값을 나타내는 9 비트 필드입니다. (8k-16) 바이트 보다 큰 값을 할당 하는 함수는 .xdata 레코드를 사용 해야 합니다. 여기에는 지역 변수 영역, 나가는 매개 변수 영역, 호출 수신자 저장 된 Int 및 FP 영역 및 홈 매개 변수 영역이 포함 되지만 동적 할당 영역은 제외 됩니다.
- **CR** 은 함수에 프레임 체인과 반환 링크를 설정 하기 위한 추가 지침이 포함 되어 있는지 여부를 나타내는 2 비트 플래그입니다.
  - 00 = 체인에 연결 되지 않은 함수, \<x29, lr > 쌍이 스택에 저장 되지 않습니다.
  - 01 = 체인에 연결 되지 않은 함수, \<lr > 스택에 저장 됩니다.
  - 10 = 예약 됨;
  - 11 = 연결 된 함수, 저장/로드 쌍 명령은 프롤로그/에필로그 \<x29, lr에 사용 됩니다 >
- **H** 는 함수 시작 부분에 저장 하 여 함수에서 정수 매개 변수를 등록할지 (120) 여부를 나타내는 1 비트 플래그입니다. (0 = 홈 레지스터가 아닙니다. 1 = 홈 레지스터).
- **Regi** 는 정식 스택 위치에 저장 된 비휘발성 INT 레지스터 (x19-x28)의 수를 나타내는 4 비트 필드입니다.
- **Regf** 는 정식 스택 위치에 저장 된 비휘발성 FP 레지스터 (d8-d15)의 수를 나타내는 3 비트 필드입니다. (RegF = 0: FP 레지스터가 저장 되지 않습니다. RegF > 0: RegF + 1 FP 레지스터가 저장 됨). 하나의 FP 레지스터가 저장 되는 함수에는 압축 해제 데이터를 사용할 수 없습니다.

위의 섹션에서 범주 1, 2 (나가는 매개 변수 영역 없음), 3 및 4에 속하는 정식 프롤로그는 압축 해제 형식으로 나타낼 수 있습니다.  정식 함수에 대 한 에필로그는 **H** 가 아무런 영향을 주지 않고, `set_fp` 명령이 생략 되 고, 단계 순서와 각 단계의 지침이 에필로그에서 반전 됨을 제외 하 고 비슷한 형태를 따릅니다. .Xdata에 대 한 알고리즘은 다음 표에 자세히 설명 된 단계를 따릅니다.

0 단계: 각 영역의 크기를 미리 계산 합니다.

1 단계: Int 호출 수신자 저장 레지스터를 저장 합니다.

2 단계:이 단계는 초기 섹션의 형식 4에만 적용 됩니다. lr은 Int 영역 끝에 저장 됩니다.

3 단계: FP 호출 수신자 저장 레지스터를 저장 합니다.

4 단계: 홈 매개 변수 영역에 입력 인수를 저장 합니다.

5 단계: 로컬 영역, \<x29, lr > 쌍 및 나가는 매개 변수 영역을 포함 하 여 남은 스택을 할당 합니다. 5a는 정식 형식 1에 해당 합니다. 5b 및 5c는 정식 형식 2에 대 한 것입니다. 5d와 5e는 형식 3과 형식 4 모두에 대해입니다.

이동 #|플래그 값|명령 #|Opcode|해제 코드
-|-|-|-|-
0|||`#intsz = RegI * 8;`<br/>`if (CR==01) #intsz += 8; // lr`<br/>`#fpsz = RegF * 8;`<br/>`if(RegF) #fpsz += 8;`<br/>`#savsz=((#intsz+#fpsz+8*8*H)+0xf)&~0xf)`<br/>`#locsz = #famsz - #savsz`|
1|0 < **Regi** < = 10|RegI/2 + **regi** %2|`stp x19,x20,[sp,#savsz]!`<br/>`stp x21,x22,[sp,#16]`<br/>`...`|`save_regp_x`<br/>`save_regp`<br/>`...`
2|**CR**= = 01 *|1|`str lr,[sp,#(intsz-8)]`\*|`save_reg`
3|0 < **Regf** < = 7|(RegF + 1)/2 +<br/>(RegF + 1) %2)|`stp d8,d9,[sp,#intsz]`\*\*<br/>`stp d10,d11,[sp,#(intsz+16)]`<br/>`...`<br/>`str d(8+RegF),[sp,#(intsz+fpsz-8)]`|`save_fregp`<br/>`...`<br/>`save_freg`
4|**H** = = 1|4|`stp x0,x1,[sp,#(intsz+fpsz)]`<br/>`stp x2,x3,[sp,#(intsz+fpsz+16)]`<br/>`stp x4,x5,[sp,#(intsz+fpsz+32)]`<br/>`stp x6,x7,[sp,#(intsz+fpsz+48)]`|`nop`<br/>`nop`<br/>`nop`<br/>`nop`
5a|**CR** = = 11 & & #locsz<br/> <= 512|2|`stp x29,lr,[sp,#-locsz]!`<br/>`mov x29,sp`\*\*\*|`save_fplr_x`<br/>`set_fp`
5b|**CR** = = 11 & &<br/>512 < #locsz <= 4080|3|`sub sp,sp,#locsz`<br/>`stp x29,lr,[sp,0]`<br/>`add x29,sp,0`|`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5c|**CR** = = 11 & & #locsz > 4080|4|`sub sp,sp,4080`<br/>`sub sp,sp,#(locsz-4080)`<br/>`stp x29,lr,[sp,0]`<br/>`add x29,sp,0`|`alloc_m`<br/>`alloc_s`/`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5d|(**Cr** = = 00 \|\| **cr**= = 01) & &<br/>#locsz <= 4080|1|`sub sp,sp,#locsz`|`alloc_s`/`alloc_m`
5e|(**Cr** = = 00 \|\| **cr**= = 01) & &<br/>#locsz > 4080|2|`sub sp,sp,4080`<br/>`sub sp,sp,#(locsz-4080)`|`alloc_m`<br/>`alloc_s`/`alloc_m`

\* **CR** = = 01이 고 **regi** 가 홀수인 경우 1 단계에서 2 단계와 마지막 save_rep를 하나의 save_regp 병합 합니다.

\*\* **CR** = = 0, **regi** ! = **0 인 == 경우 부동** 소수점의 첫 번째 .stp는 predecrement를 수행 합니다.

\*\*\* `mov x29,sp`에 해당 하는 지침이 에필로그에 없습니다. 함수에서 x29의 sp를 복원 해야 하는 경우에는 압축 된 해제 데이터를 사용할 수 없습니다.

### <a name="unwinding-partial-prologs-and-epilogs"></a>부분 프롤로그 및 에필로그 해제

가장 일반적인 해제 상황은 프롤로그와 모든 에필로그의 함수 본문에서 예외 또는 호출이 발생 한 경우입니다. 이 경우 해제는 간단 합니다. 해제기는 단순히 인덱스 0부터 시작 하는 해제 배열의 코드 실행을 시작 하 고 종료 opcode가 검색 될 때까지 계속 합니다.

프롤로그 나 에필로그를 실행 하는 동안 예외 또는 인터럽트가 발생 하는 경우에는 올바르게 해제 하기가 더 어렵습니다. 이러한 경우 스택 프레임은 일부만 생성 됩니다. 문제는 올바르게 실행을 취소 하기 위해 수행 된 작업을 정확 하 게 확인 하는 것입니다.

예를 들어 다음 프롤로그 및 에필로그 시퀀스를 사용 합니다.

```asm
0000:    stp    x29,lr,[sp,#-256]!          // save_fplr_x  256 (pre-indexed store)
0004:    stp    d8,d9,[sp,#224]             // save_fregp 0, 224
0008:    stp    x19,x20,[sp,#240]           // save_regp 0, 240
000c:    mov    x29,sp                      // set_fp
         ...
0100:    mov    sp,x29                      // set_fp
0104:    ldp    x19,x20,[sp,#240]           // save_regp 0, 240
0108:    ldp    d8,d9,[sp,224]              // save_fregp 0, 224
010c:    ldp    x29,lr,[sp],#256            // save_fplr_x  256 (post-indexed load)
0110:    ret    lr                          // end
```

각 opcode 옆에는이 작업을 설명 하는 적절 한 해제 코드가 있습니다. 프롤로그에 대 한 해제 코드의 일련 번호가 에필로그의 해제 코드에 대 한 정확한 미러 이미지 인지 확인할 수 있습니다. 에필로그의 최종 명령은 제외 됩니다. 일반적인 상황에서 프롤로그에 대 한 해제 코드는 항상 프롤로그의 실행 순서에서 역순으로 저장 된다고 가정 합니다.

따라서 프롤로그 및 에필로그 모두에 대해 일반 해제 코드 집합을 사용 하 게 됩니다.

`set_fp`, `save_regp 0,240`, `save_fregp,0,224`, `save_fplr_x_256`, `end`

에필로그의 경우는 일반적인 순서로 되어 있기 때문에 간단 합니다. 에필로그 내의 오프셋 0에서 시작 하 여 (함수의 offset 0x100에서 시작) 정리가 아직 수행 되지 않았기 때문에 전체 해제 시퀀스를 실행 하 게 될 것입니다. 에서 한 명령이 있는 경우 (에필로그의 오프셋 2에서) 첫 번째 해제 코드를 건너뛰고 성공적으로 해제할 수 있습니다. 이러한 상황을 일반화 하 고 opcode와 해제 코드 간의 1:1 매핑을 가정할 수 있습니다. 그런 다음 에필로그의 명령 *n* 에서 해제를 시작 하려면 첫 번째 *n* 해제 코드를 건너뛰고 여기서 실행을 시작 해야 합니다.

역방향을 제외 하 고 프롤로그에 대해 유사한 논리가 작동 한다는 것을 확인 합니다. 프롤로그에서 오프셋 0에서 해제를 시작 하는 경우 아무 것도 실행 하지 않으려고 합니다. 의 한 명령인 오프셋 2에서 해제 하는 경우 해제 시퀀스의 실행을 시작 하 고 끝부터 해제 코드를 실행 하려고 합니다. 코드는 반대 순서로 저장 됩니다. 또한 일반화 할 수 있습니다. 프롤로그의 명령 n에서 해제를 시작 하는 경우 코드 목록의 끝에서 n 해제 코드 실행을 시작 해야 합니다.

프롤로그 및 에필로그 코드가 정확 하 게 일치 하는 경우도 있습니다. 이 때문에 해제 배열에 여러 코드 시퀀스가 포함 되어야 할 수 있습니다. 코드 처리를 시작할 위치의 오프셋을 확인 하려면 다음 논리를 사용 합니다.

1. 함수 본문 내에서 해제 하는 경우 인덱스 0에서 해제 코드 실행을 시작 하 고 "end" opcode에 도달할 때까지 계속 합니다.

1. 에필로그 내에서 해제 하는 경우 에필로그 범위와 함께 제공 되는 에필로그 별 시작 인덱스를 시작 지점으로 사용 합니다. 해당 PC가 에필로그의 시작 부분에서 얼마나 많은 바이트를 계산 합니다. 그런 다음 해제 코드를 앞으로 이동 하 여 이미 실행 된 모든 명령이 고려 될 때까지 해제 코드를 건너뜁니다. 그런 다음 해당 지점부터를 실행 합니다.

1. 프롤로그 내에서 해제 하는 경우 인덱스 0을 시작 지점으로 사용 합니다. 시퀀스에서 프롤로그 코드의 길이를 계산한 다음 해당 PC가 프롤로그의 끝에서 얼마나 많은 바이트를 계산 합니다. 그런 다음 해제 코드를 앞으로 이동 하 여, 아직 실행 되지 않은 모든 명령이 고려 될 때까지 해제 코드를 건너뜁니다. 그런 다음 해당 지점부터를 실행 합니다.

이러한 규칙은 프롤로그에 대 한 해제 코드가 항상 배열의 첫 번째가 되어야 함을 의미 합니다. 또한 본문 내에서 해제 하는 일반적인 경우를 해제 하는 데 사용 되는 코드도 있습니다. 모든 에필로그 별 코드 시퀀스는 바로 뒤에와 야 합니다.

### <a name="function-fragments"></a>함수 조각

코드 최적화의 목적 및 기타 이유로 함수를 분리 된 조각 (영역이 라고도 함)으로 분할 하는 것이 더 적합할 수 있습니다. 분할 시 각 결과 함수 조각에는 별도의 .pdata (및 .xdata) 레코드가 필요 합니다.

자체 프롤로그를 포함 하는 분리 된 각 보조 조각에 대해 해당 프롤로그에서 스택 조정이 수행 되지 않아야 합니다. 보조 지역에 필요한 모든 스택 공간은 부모 지역 (또는 호스트 영역)에 의해 미리 할당 되어야 합니다. 이렇게 하면 스택 포인터 조작이 함수의 원래 프롤로그에 엄격 하 게 유지 됩니다.

함수 조각의 일반적인 경우는 컴파일러가 해당 호스트 함수 밖으로 코드 영역을 이동할 수 있는 "코드 분리"입니다. 코드 분리로 인해 발생 하는 세 가지 비정상적인 사례가 있습니다.

#### <a name="example"></a>예제

- (지역 1: 시작)

    ```asm
        stp     x29,lr,[sp,#-256]!      // save_fplr_x  256 (pre-indexed store)
        stp     x19,x20,[sp,#240]       // save_regp 0, 240
        mov     x29,sp                  // set_fp
        ...
    ```

- (지역 1: 끝)

- (지역 3: 시작)

    ```asm
        ...
    ```

- (지역 3: 끝)

- (지역 2: 시작)

    ```asm
        ...
        mov     sp,x29                  // set_fp
        ldp     x19,x20,[sp,#240]       // save_regp 0, 240
        ldp     x29,lr,[sp],#256        // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (지역 2: 끝)

1. 프롤로그만 (지역 1: 모든 에필로그는 분리 된 지역에 있습니다.):

   프롤로그만 설명 해야 합니다. 이는 압축이 .pdata 형식으로 표현 될 수 없습니다. .Xdata의 경우 에필로그 Count = 0을 설정 하 여 나타낼 수 있습니다. 위의 예제에서 지역 1을 참조 하세요.

   해제 코드: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

1. 에필로그 only (지역 2: 프롤로그는 호스트 영역에 있습니다.)

   이 지역으로 이동 하는 시간 제어가 모든 프롤로그 코드를 실행 한 것으로 가정 합니다. 부분 해제는 일반 함수와 동일한 방식으로 에필로그에서 발생할 수 있습니다. 이러한 유형의 지역은 압축이 .pdata로 나타낼 수 없습니다. .Xdata 레코드에서 "가상" 프롤로그를 사용 하 여 `end_c` 하 고 `end` 해제 코드 쌍으로 인코딩할 수 있습니다.  선행 `end_c`는 프롤로그의 크기가 0 임을 나타냅니다. `set_fp`단일 에필로그 지점의 에필로그 시작 인덱스입니다.

   영역 2: `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`에 대 한 해제 코드입니다.

1. 프롤로그 또는 에필로그 없음 (지역 3: 프롤로그 및 모든 에필로그는 다른 조각에 있습니다.):

   압축 .pdata 형식은 플래그를 설정 하는 10을 통해 적용할 수 있습니다. .Xdata 레코드를 사용 하 여 에필로그 수 = 1입니다. 해제 코드는 위의 영역 2에 대 한 코드와 동일 하지만 에필로그 시작 인덱스는 `end_c`도 가리킵니다. 부분 해제는이 코드 영역에서 발생 하지 않습니다.

함수 조각의 또 다른 복잡 한 경우는 "축소 래핑"입니다. 컴파일러는 함수 엔트리 프롤로그 외부에 있을 때까지 일부 호출 수신자 저장 레지스터의 저장을 지연 하도록 선택할 수 있습니다.

- (지역 1: 시작)

    ```asm
        stp     x29,lr,[sp,#-256]!      // save_fplr_x  256 (pre-indexed store)
        stp     x19,x20,[sp,#240]       // save_regp 0, 240
        mov     x29,sp                  // set_fp
        ...
    ```

- (지역 2: 시작)

    ```asm
        stp     x21,x22,[sp,#224]       // save_regp 2, 224
        ...
        ldp     x21,x22,[sp,#224]       // save_regp 2, 224
    ```

- (지역 2: 끝)

    ```asm
        ...
        mov     sp,x29                  // set_fp
        ldp     x19,x20,[sp,#240]       // save_regp 0, 240
        ldp     x29,lr,[sp],#256        // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (지역 1: 끝)

지역 1의 프롤로그에서 스택 공간은 미리 할당 됩니다. 해당 호스트 함수 밖으로 이동 하더라도 지역 2는 동일한 해제 코드를 사용할 수 있습니다.

지역 1: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end` 에필로그 시작 인덱스를 사용 하 여 평소와 같이 `set_fp` 합니다.

영역 2: `save_regp 2, 224`, `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`. 에필로그 시작 인덱스는 첫 번째 해제 코드 `save_regp 2, 224`를 가리킵니다.

### <a name="large-functions"></a>Large 함수

조각은 .xdata 헤더의 비트 필드에 의해 적용 되는 1M 한도 보다 큰 함수를 설명 하는 데 사용할 수 있습니다. 이와 같이 매우 큰 기능을 설명 하려면 1M 보다 작은 조각으로 분할 해야 합니다. 각 조각은 에필로그를 여러 부분으로 분할 하지 않도록 조정 해야 합니다.

함수의 첫 번째 조각에만 프롤로그가 포함 됩니다. 다른 모든 조각은 프롤로그가 없는 것으로 표시 됩니다. 에필로그의 수에 따라 각 조각은 에필로그을 0 개 이상 포함할 수 있습니다. 조각의 각 에필로그 범위는 함수의 시작이 아니라 조각의 시작 부분을 기준으로 시작 오프셋을 지정 합니다.

조각에 프롤로그가 없고 에필로그가 없는 경우에도 함수 본문 내에서 해제 하는 방법을 설명 하는 고유한 .pdata (및 .xdata) 레코드가 필요 합니다.

## <a name="examples"></a>예

### <a name="example-1-frame-chained-compact-form"></a>예제 1: 프레임 연결, 압축 형식

```asm
|Foo|     PROC
|$LN19|
    str     x19,[sp,#-0x10]!        // save_reg_x
    sub     sp,sp,#0x810            // alloc_m
    stp     fp,lr,[sp]              // save_fplr
    mov     fp,sp                   // set_fp
                                    //  end of prolog
    ...

|$pdata$Foo|
    DCD     imagerel     |$LN19|
    DCD     0x416101ed
    ;Flags[SingleProEpi] functionLength[492] RegF[0] RegI[1] H[0] frameChainReturn[Chained] frameSize[2080]
```

### <a name="example-2-frame-chained-full-form-with-mirror-prolog--epilog"></a>예 2: 프레임 연결, 미러 프롤로그를 사용 하는 전체 형식 & 에필로그

```asm
|Bar|     PROC
|$LN19|
    stp     x19,x20,[sp,#-0x10]!    // save_regp_x
    stp     fp,lr,[sp,#-0x90]!      // save_fplr_x
    mov     fp,sp                   // set_fp
                                    // end of prolog
    ...
                                    // begin of epilog, a mirror sequence of Prolog
    mov     sp,fp
    ldp     fp,lr,[sp],#0x90
    ldp     x19,x20,[sp],#0x10
    ret     lr

|$pdata$Bar|
    DCD     imagerel     |$LN19|
    DCD     imagerel     |$unwind$cse2|
|$unwind$Bar|
    DCD     0x1040003d
    DCD     0x1000038
    DCD     0xe42291e1
    DCD     0xe42291e1
    ;Code Words[2], Epilog Count[1], E[0], X[0], Function Length[6660]
    ;Epilog Start Index[0], Epilog Start Offset[56]
    ;set_fp
    ;save_fplr_x
    ;save_r19r20_x
    ;end
```

에필로그 시작 인덱스 [0]은 (는) 프롤로그 해제 코드의 동일한 시퀀스를 가리킵니다.

### <a name="example-3-variadic-unchained-function"></a>예제 3: Variadic unchained 함수

```asm
|Delegate| PROC
|$LN4|
    sub     sp,sp,#0x50
    stp     x19,lr,[sp]
    stp     x0,x1,[sp,#0x10]        // save incoming register to home area
    stp     x2,x3,[sp,#0x20]        // ...
    stp     x4,x5,[sp,#0x30]
    stp     x6,x7,[sp,#0x40]        // end of prolog
    ...
    ldp     x19,lr,[sp]             // beginning of epilog
    add     sp,sp,#0x50
    ret     lr

    AREA    |.pdata|, PDATA
|$pdata$Delegate|
    DCD     imagerel |$LN4|
    DCD     imagerel |$unwind$Delegate|

    AREA    |.xdata|, DATA
|$unwind$Delegate|
    DCD     0x18400012
    DCD     0x200000f
    DCD     0xe3e3e3e3
    DCD     0xe40500d6
    DCD     0xe40500d6
    ;Code Words[3], Epilog Count[1], E[0], X[0], Function Length[18]
    ;Epilog Start Index[4], Epilog Start Offset[15]
    ;nop        // nop for saving in home area
    ;nop        // ditto
    ;nop        // ditto
    ;nop        // ditto
    ;save_lrpair
    ;alloc_s
    ;end
```

에필로그 시작 인덱스 [4]은 (는) 프롤로그 해제 코드의 중간 (해제 배열을 부분적으로 재사용)을 가리킵니다.

## <a name="see-also"></a>참고 항목

[ARM64 ABI 규칙 개요](arm64-windows-abi-conventions.md)<br/>
[ARM 예외 처리](arm-exception-handling.md)
