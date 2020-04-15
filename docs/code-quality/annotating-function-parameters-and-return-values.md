---
title: 함수 매개 변수 에 추가 및 반환 값
description: 함수 매개 변수및 반환 값 주석에 대한 참조 가이드입니다.
ms.date: 10/15/2019
ms.topic: conceptual
f1_keywords:
- _Outptr_opt_result_bytebuffer_to_
- _Inout_updates_all_opt_
- _Post_equal_to_
- _Outptr_opt_result_maybenull_
- _Out_writes_bytes_all_
- _Out_writes_all_opt_
- _In_opt_
- _Outptr_
- _Outptr_result_maybenull_
- _Outref_result_bytebuffer_all_maybenull_
- _Inout_updates_opt_z_
- _Inout_updates_z_
- _Out_writes_
- _Out_writes_to_ptr_opt_z_
- _In_reads_to_ptr_opt_
- _Ret_writes_to_maybenull_
- _Outref_result_maybenull_
- _Ret_writes_bytes_
- _Outptr_result_bytebuffer_
- _Out_writes_opt_
- _Inout_updates_bytes_opt_
- _In_z_
- _Inout_updates_to_
- _Ret_maybenull_
- _Ret_writes_bytes_to_
- _Ret_z_
- _COM_Outptr_
- _Ret_maybenull_z_
- _Out_opt_
- _In_reads_opt_z_
- _Outptr_result_bytebuffer_to_
- _Ret_notnull_
- _COM_Outptr_opt_result_maybenull_
- _Inout_updates_to_opt_
- _Inout_updates_
- _Outptr_opt_result_buffer_
- _Outptr_result_buffer_to_
- _Out_writes_to_ptr_opt_
- _Out_writes_bytes_all_opt_
- _Inout_updates_all_
- _Deref_inout_range_
- _Ret_writes_
- _Out_writes_z_
- _Ret_writes_to_
- _Out_writes_to_ptr_z_
- _Out_writes_bytes_to_opt_
- _In_reads_or_z_
- _Inout_updates_bytes_to_
- _In_reads_z_
- _In_opt_z_
- _Outref_result_buffer_maybenull_
- _Ret_range_
- _COM_Outptr_opt_
- _Outptr_opt_result_maybenull_z_
- _In_reads_opt_
- _Inout_
- _Field_range_
- _Ret_writes_z_
- _Out_writes_to_
- _Out_writes_to_ptr_
- _Inout_opt_z_
- _Outref_
- _Deref_out_range_
- _Outref_result_buffer_
- _Outref_result_buffer_to_
- _Outref_result_bytebuffer_to_maybenull_
- _In_reads_bytes_
- _Outptr_opt_result_buffer_to_
- _Outref_result_buffer_all_
- _Out_writes_bytes_to_
- _Result_zeroonfailure_
- _In_reads_bytes_opt_
- _Outref_result_buffer_to_maybenull_
- _Outref_result_bytebuffer_all_
- _Outref_result_buffer_all_maybenull_
- _Ret_writes_maybenull_z_
- _In_range_
- _Inout_updates_bytes_all_opt_
- _Outref_result_bytebuffer_to_
- _Inout_updates_bytes_to_opt_
- _Pre_equal_to_
- _Ret_writes_bytes_maybenull_
- _COM_Outptr_result_maybenull_
- _Ret_writes_maybenull_
- _Out_writes_bytes_
- _Outptr_opt_
- _Out_writes_opt_z_
- _Outref_result_nullonfailure_
- _Outptr_opt_result_z_
- _Inout_opt_
- _Deref_in_range_
- _Outptr_result_z_
- _In_reads_to_ptr_opt_z_
- _Struct_size_bytes_
- _Outptr_result_nullonfailure_
- _In_
- _Inout_updates_bytes_
- _In_reads_to_ptr_z_
- _Ret_writes_bytes_to_maybenull
- _Outptr_opt_result_nullonfailure_
- _In_reads_to_ptr_
- _Outptr_result_buffer_
- _Out_
- _Outref_result_bytebuffer_maybenull_
- _Outptr_result_maybenull_z_
- _In_reads_
- _Inout_updates_opt_
- _Out_writes_to_opt_
- _Outptr_opt_result_bytebuffer_
- _Out_writes_all_
- _Out_range_
- _Inout_updates_bytes_all_
- _Inout_z_
- _Outref_result_bytebuffer_
- _Result_nullonfailure_
- _Ret_null_
- _Scanf_format_string_
- _Scanf_s_format_string_
- _Printf_format_string_
ms.assetid: 82826a3d-0c81-421c-8ffe-4072555dca3a
ms.openlocfilehash: c787dcfb252da1abe47251d66c46689db289cf15
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328005"
---
# <a name="annotating-function-parameters-and-return-values"></a>함수 매개 변수 에 추가 및 반환 값

이 문서에서는 간단한 함수 매개 변수(스칼라 및 구조및 클래스에 대한 포인터 및 대부분의 버퍼)에 대한 주석의 일반적인 용도에 대해 설명합니다. 이 문서에서는 주석에 대한 일반적인 사용 패턴도 보여 주며, 이 문서에서는 다음과 같은 작업을 보여 주기도 합니다. 함수와 관련된 추가 주석은 함수 동작 에 [주석 추가](../code-quality/annotating-function-behavior.md)를 참조하십시오.

## <a name="pointer-parameters"></a>포인터 매개 변수

다음 표의 주석에 대해 포인터 매개 변수가 주석이 추가될 때 분석기는 포인터가 null인 경우 오류를 보고합니다. 이 추가는 포인터및 가리키는 모든 데이터 항목에 적용됩니다.

### <a name="annotations-and-descriptions"></a>주석 및 설명

- `_In_`

     스칼라, 구조, 구조에 대한 포인터 등의 입력 매개변수에 추가합니다. 간단한 스칼라에 명시적으로 사용할 수 있습니다. 매개 변수는 사전 상태에서 유효해야 하며 수정되지 않습니다.

- `_Out_`

     스칼라, 구조, 구조포인터 등의 출력 매개변수에 추가합니다. 값을 반환할 수 없는 개체(예: 값으로 전달되는 스칼라)에 이 주석을 적용하지 마십시오. 매개 변수는 사전 상태에서 유효할 필요는 없지만 사후 상태에서 유효해야 합니다.

- `_Inout_`

     함수에 의해 변경되는 매개 변수에 추가합니다. 사전 상태와 사후 상태 모두에서 유효해야 하지만 호출 전후에 서로 다른 값을 가지는 것으로 가정합니다. 수정 가능한 값에 적용해야 합니다.

- `_In_z_`

     입력으로 사용되는 null 종료 문자열에 대한 포인터입니다. 문자열은 사전 상태에서 유효해야 합니다. 이미 올바른 `PSTR`주석이 있는 의 변형이 선호됩니다.

- `_Inout_z_`

     수정될 null-종단 문자 배열에 대한 포인터입니다. 호출 전후에 유효해야 하지만 값이 변경되었다고 가정합니다. null 터미네이터를 이동할 수 있지만 원래 null 종기까지의 요소만 액세스할 수 있습니다.

- `_In_reads_(s)`

     `_In_reads_bytes_(s)`

     함수에서 읽는 배열에 대한 포인터입니다. 배열은 크기 `s` 요소이며 모두 유효해야 합니다.

     변형은 `_bytes_` 요소 대신 바이트로 크기를 제공합니다. 크기를 요소로 표현할 수 없는 경우에만 이 변형을 사용합니다. 예를 들어 `char` 문자열은 사용하는 `_bytes_` `wchar_t` 유사한 함수가 있는 경우에만 변형을 사용합니다.

- `_In_reads_z_(s)`

     null-종료되고 알려진 크기를 가지는 배열에 대한 포인터입니다. null 종말기까지의 요소 또는 `s` null 터미네이터가 없는 경우 사전 상태에서 유효해야 합니다. 크기가 바이트단위로 알려진 경우 `s` 요소 크기에 따라 배율을 조정합니다.

- `_In_reads_or_z_(s)`

     null-종료 또는 알려진 크기 또는 둘 다있는 배열에 대한 포인터입니다. null 종말기까지의 요소 또는 `s` null 터미네이터가 없는 경우 사전 상태에서 유효해야 합니다. 크기가 바이트단위로 알려진 경우 `s` 요소 크기에 따라 배율을 조정합니다. `strn` (가족을 위해 사용됩니다.)

- `_Out_writes_(s)`

     `_Out_writes_bytes_(s)`

     함수에 의해 작성될 요소(resp. 바이트)의 `s` 배열에 대한 포인터입니다. 배열 요소는 사전 상태에서 유효할 필요는 없으며 사후 상태에서 유효한 요소 수는 지정되지 않습니다. 매개 변수 형식에 주석이 있으면 사후 상태로 적용됩니다. 예를 들어, 다음과 같은 코드를 생각해 볼 수 있습니다.

     ```cpp
     typedef _Null_terminated_ wchar_t *PWSTR;
     void MyStringCopy(_Out_writes_(size) PWSTR p1, _In_ size_t size, _In_ PWSTR p2);
     ```

     이 예제에서 호출자는 에 `size` 대한 `p1`요소 버퍼를 제공합니다. `MyStringCopy`이러한 요소 중 일부를 유효하게 만듭니다. 더 중요한 것은, `_Null_terminated_` 에 `PWSTR` 대한 `p1` 추가 는 사후 상태에서 null 종료된다는 것을 의미합니다. 이러한 방식으로 유효한 요소의 수는 여전히 잘 정의되어 있지만 특정 요소 수는 필요하지 않습니다.

     변형은 `_bytes_` 요소 대신 바이트로 크기를 제공합니다. 크기를 요소로 표현할 수 없는 경우에만 이 변형을 사용합니다. 예를 들어 `char` 문자열은 사용하는 `_bytes_` `wchar_t` 유사한 함수가 있는 경우에만 변형을 사용합니다.

- `_Out_writes_z_(s)`

     요소 배열에 대한 `s` 포인터입니다. 요소가 사전 상태에서 유효할 필요는 없습니다. 사후 상태에서는 존재해야 하는 null 터미네이터를 통한 요소가 유효해야 합니다. 크기가 바이트단위로 알려진 경우 `s` 요소 크기에 따라 배율을 조정합니다.

- `_Inout_updates_(s)`

     `_Inout_updates_bytes_(s)`

     함수에서 읽고 쓰는 배열에 대한 포인터입니다. 크기 `s` 요소이며 사전 상태 및 사후 상태에서 유효합니다.

     변형은 `_bytes_` 요소 대신 바이트로 크기를 제공합니다. 크기를 요소로 표현할 수 없는 경우에만 이 변형을 사용합니다. 예를 들어 `char` 문자열은 사용하는 `_bytes_` `wchar_t` 유사한 함수가 있는 경우에만 변형을 사용합니다.

- `_Inout_updates_z_(s)`

     null-종료되고 알려진 크기를 가지는 배열에 대한 포인터입니다. 존재해야 하는 null 터미네이터를 통한 요소는 사전 상태와 사후 상태 모두에서 유효해야 합니다. 사후 상태의 값은 사전 상태의 값과 다른 것으로 추정됩니다. 여기에는 null 터미네이터의 위치가 포함됩니다. 크기가 바이트단위로 알려진 경우 `s` 요소 크기에 따라 배율을 조정합니다.

- `_Out_writes_to_(s,c)`

     `_Out_writes_bytes_to_(s,c)`

     `_Out_writes_all_(s)`

     `_Out_writes_bytes_all_(s)`

     요소 배열에 대한 `s` 포인터입니다. 요소가 사전 상태에서 유효할 필요는 없습니다. 사후 상태에서 -th 요소까지의 `c`요소는 유효해야 합니다. 크기가 `_bytes_` 요소 수가 아닌 바이트로 알려진 경우 변형을 사용할 수 있습니다.

     다음은 그 예입니다.

     ```cpp
     void *memcpy(_Out_writes_bytes_all_(s) char *p1, _In_reads_bytes_(s) char *p2, _In_ int s);
     void *wordcpy(_Out_writes_all_(s) DWORD *p1, _In_reads_(s) DWORD *p2, _In_ int s);
     ```

- `_Inout_updates_to_(s,c)`

     `_Inout_updates_bytes_to_(s,c)`

     함수에서 읽고 쓰는 배열에 대한 포인터입니다. 크기 `s` 요소의 모든 사전 상태에서 유효 해야 하 고 `c` 요소는 사후 상태에서 유효 해야 합니다.

     변형은 `_bytes_` 요소 대신 바이트로 크기를 제공합니다. 크기를 요소로 표현할 수 없는 경우에만 이 변형을 사용합니다. 예를 들어 `char` 문자열은 사용하는 `_bytes_` `wchar_t` 유사한 함수가 있는 경우에만 변형을 사용합니다.

- `_Inout_updates_all_(s)`

     `_Inout_updates_bytes_all_(s)`

     크기 `s` 요소의 함수에 의해 읽혀지고 쓰는 배열에 대한 포인터입니다. 다음과 같이 정의됩니다.

     `_Inout_updates_to_(_Old_(s), _Old_(s))    _Inout_updates_bytes_to_(_Old_(s), _Old_(s))`

     즉, 사전 상태에 버퍼에 `s` 존재하는 모든 요소는 사전 상태 및 사후 상태에서 유효합니다.

     변형은 `_bytes_` 요소 대신 바이트로 크기를 제공합니다. 크기를 요소로 표현할 수 없는 경우에만 이 변형을 사용합니다. 예를 들어 `char` 문자열은 사용하는 `_bytes_` `wchar_t` 유사한 함수가 있는 경우에만 변형을 사용합니다.

- `_In_reads_to_ptr_(p)`

     `p - _Curr_` (즉, `p` 마이너스) `_Curr_`유효한 식인 배열에 대한 포인터입니다. 이전의 `p` 요소는 사전 상태에서 유효해야 합니다.

    다음은 그 예입니다.

    ```cpp
    int ReadAllElements(_In_reads_to_ptr_(EndOfArray) const int *Array, const int *EndOfArray);
    ```

- `_In_reads_to_ptr_z_(p)`

     식(즉, `p - _Curr_` `p` 빼기)이 `_Curr_`유효한 식인 null-terminated 배열에 대한 포인터입니다. 이전의 `p` 요소는 사전 상태에서 유효해야 합니다.

- `_Out_writes_to_ptr_(p)`

     `p - _Curr_` (즉, `p` 마이너스) `_Curr_`유효한 식인 배열에 대한 포인터입니다. 이전의 `p` 요소는 사전 상태에서 유효할 필요가 없으며 사후 상태에서 유효해야 합니다.

- `_Out_writes_to_ptr_z_(p)`

     null-terminated 배열에 대한 포인터(즉, `p - _Curr_` `p` 빼기)는 `_Curr_`유효한 식입니다. 이전의 `p` 요소는 사전 상태에서 유효할 필요가 없으며 사후 상태에서 유효해야 합니다.

## <a name="optional-pointer-parameters"></a>선택적 포인터 매개 변수

포인터 매개 변수 가 `_opt_`포함되면 매개 변수가 null일 수 있음을 나타냅니다. 그렇지 않으면 주석은 을 포함하지 `_opt_`않는 버전과 동일하게 행동합니다. 다음은 포인터 매개 `_opt_` 변수 주석의 변형 목록입니다.

||||
|-|-|-|
|`_In_opt_`<br /><br /> `_Out_opt_`<br /><br /> `_Inout_opt_`<br /><br /> `_In_opt_z_`<br /><br /> `_Inout_opt_z_`<br /><br /> `_In_reads_opt_`<br /><br /> `_In_reads_bytes_opt_`<br /><br /> `_In_reads_opt_z_`|`_Out_writes_opt_`<br /><br /> `_Out_writes_opt_z_`<br /><br /> `_Inout_updates_opt_`<br /><br /> `_Inout_updates_bytes_opt_`<br /><br /> `_Inout_updates_opt_z_`<br /><br /> `_Out_writes_to_opt_`<br /><br /> `_Out_writes_bytes_to_opt_`<br /><br /> `_Out_writes_all_opt_`<br /><br /> `_Out_writes_bytes_all_opt_`|`_Inout_updates_to_opt_`<br /><br /> `_Inout_updates_bytes_to_opt_`<br /><br /> `_Inout_updates_all_opt_`<br /><br /> `_Inout_updates_bytes_all_opt_`<br /><br /> `_In_reads_to_ptr_opt_`<br /><br /> `_In_reads_to_ptr_opt_z_`<br /><br /> `_Out_writes_to_ptr_opt_`<br /><br /> `_Out_writes_to_ptr_opt_z_`|

## <a name="output-pointer-parameters"></a>출력 포인터 매개 변수

출력 포인터 매개 변수는 매개 변수 및 뾰족한 위치에 대한 null을 모호하게 하기 위해 특별한 표기가 필요합니다.

### <a name="annotations-and-descriptions"></a>주석 및 설명

- `_Outptr_`

   매개 변수는 null일 수 없으며 사후 상태에서 가리키는 위치는 null이 될 수 없으며 유효해야 합니다.

- `_Outptr_opt_`

   매개 변수는 null일 수 있지만 사후 상태에서 가리키는 위치는 null이 될 수 없으며 유효해야 합니다.

- `_Outptr_result_maybenull_`

   매개 변수는 null일 수 없으며 사후 상태에서 가리키는 위치는 null일 수 있습니다.

- `_Outptr_opt_result_maybenull_`

   매개 변수는 null일 수 있으며 사후 상태에서 가리키는 위치는 null일 수 있습니다.

  다음 표에서는 추가 하위 문자열이 추가 지정 이름에 삽입되어 추가 지정의 의미를 한정합니다. 다양한 하위 문자열은 `_z` `_COM_`" `_buffer_` `_bytebuffer_`, `_to_`및 .

> [!IMPORTANT]
> 주석을 추가하려는 인터페이스가 COM인 경우 이러한 주석의 COM 형식을 사용합니다. 다른 형식 인터페이스에서 COM 주석을 사용하지 마십시오.

- `_Outptr_result_z_`

   `_Outptr_opt_result_z_`

   `_Outptr_result_maybenull_z_`

   `_Outptr_opt_result_maybenull_z_`

   반환된 포인터에는 `_Null_terminated_` 추가가 있습니다.

- `_COM_Outptr_`

   `_COM_Outptr_opt_`

   `_COM_Outptr_result_maybenull_`

   `_COM_Outptr_opt_result_maybenull_`

   반환된 포인터에는 COM 의미 체계가 있으므로 `_On_failure_` 반환된 포인터가 null이라는 사후 조건이 전달됩니다.

- `_Outptr_result_buffer_(s)`

   `_Outptr_result_bytebuffer_(s)`

   `_Outptr_opt_result_buffer_(s)`

   `_Outptr_opt_result_bytebuffer_(s)`

   반환된 포인터는 크기 `s` 요소 또는 바이트의 유효한 버퍼를 가리킵니다.

- `_Outptr_result_buffer_to_(s, c)`

   `_Outptr_result_bytebuffer_to_(s, c)`

   `_Outptr_opt_result_buffer_to_(s,c)`

   `_Outptr_opt_result_bytebuffer_to_(s,c)`

   반환된 포인터는 크기 `s` 요소 또는 바이트버퍼를 가리키며, 그 중 첫 번째 `c` 포인터는 유효합니다.

특정 인터페이스 규칙은 출력 매개 변수가 실패시 무효화된다고 가정합니다. 명시적으로 COM 코드를 제외하고 다음 표의 양식이 선호됩니다. COM 코드의 경우 이전 섹션에 나열된 해당 COM 양식을 사용합니다.

- `_Result_nullonfailure_`

   다른 주석을 수정합니다. 함수가 실패하면 결과가 null로 설정됩니다.

- `_Result_zeroonfailure_`

   다른 주석을 수정합니다. 함수가 실패하면 결과가 0으로 설정됩니다.

- `_Outptr_result_nullonfailure_`

   반환된 포인터는 함수가 성공하면 유효한 버퍼를 가리키거나 함수가 실패하면 null을 가리킵니다. 이 부호는 선택 사항이 아닌 매개 변수에 대한 것입니다.

- `_Outptr_opt_result_nullonfailure_`

   반환된 포인터는 함수가 성공하면 유효한 버퍼를 가리키거나 함수가 실패하면 null을 가리킵니다. 이 부포는 선택적 매개 변수에 대한 것입니다.

- `_Outref_result_nullonfailure_`

   반환된 포인터는 함수가 성공하면 유효한 버퍼를 가리키거나 함수가 실패하면 null을 가리킵니다. 이 부어는 참조 매개 변수에 대한 것입니다.

## <a name="output-reference-parameters"></a>출력 참조 매개 변수

참조 매개 변수의 일반적인 용도는 출력 매개 변수에 대한 것입니다. 와 `int&` `_Out_` 같은 간단한 출력 참조 매개 변수의 경우 올바른 의미 체계를 제공합니다. 그러나 출력 값이 와 같은 `int *&`포인터인 경우 와 같은 `_Outptr_ int **` 동등한 포인터 주석은 올바른 의미 체계를 제공하지 않습니다. 포인터 형식에 대한 출력 참조 매개 변수의 의미 체계를 간결하게 표현하려면 다음 복합 주석을 사용합니다.

### <a name="annotations-and-descriptions"></a>주석 및 설명

- `_Outref_`

     결과는 사후 상태에서 유효해야 하며 null일 수 없습니다.

- `_Outref_result_maybenull_`

     결과는 사후 상태에서 유효해야 하지만 사후 상태에서는 null일 수 있습니다.

- `_Outref_result_buffer_(s)`

     결과는 사후 상태에서 유효해야 하며 null일 수 없습니다. 크기 `s` 요소의 유효한 버퍼를 가리킵니다.

- `_Outref_result_bytebuffer_(s)`

     결과는 사후 상태에서 유효해야 하며 null일 수 없습니다. 크기 `s` 바이트의 유효한 버퍼를 가리킵니다.

- `_Outref_result_buffer_to_(s, c)`

     결과는 사후 상태에서 유효해야 하며 null일 수 없습니다. 첫 번째 `c` `s` 요소가 유효한 요소의 버퍼를 가리킵니다.

- `_Outref_result_bytebuffer_to_(s, c)`

     결과는 사후 상태에서 유효해야 하며 null일 수 없습니다. 첫 번째 `c` `s` 바이트가 유효한 바이트 버퍼를 가리킵니다.

- `_Outref_result_buffer_all_(s)`

     결과는 사후 상태에서 유효해야 하며 null일 수 없습니다. 크기 `s` 유효한 요소의 유효한 버퍼를 가리킵니다.

- `_Outref_result_bytebuffer_all_(s)`

     결과는 사후 상태에서 유효해야 하며 null일 수 없습니다. 유효한 요소바이트의 `s` 유효한 버퍼를 가리킵니다.

- `_Outref_result_buffer_maybenull_(s)`

     결과는 사후 상태에서 유효해야 하지만 사후 상태에서는 null일 수 있습니다. 크기 `s` 요소의 유효한 버퍼를 가리킵니다.

- `_Outref_result_bytebuffer_maybenull_(s)`

     결과는 사후 상태에서 유효해야 하지만 사후 상태에서는 null일 수 있습니다. 크기 `s` 바이트의 유효한 버퍼를 가리킵니다.

- `_Outref_result_buffer_to_maybenull_(s, c)`

     결과는 사후 상태에서 유효해야 하지만 사후 상태에서는 null일 수 있습니다. 첫 번째 `c` `s` 요소가 유효한 요소의 버퍼를 가리킵니다.

- `_Outref_result_bytebuffer_to_maybenull_(s,c)`

     결과는 사후 상태에서 유효해야 하지만 사후 상태에서는 null일 수 있습니다. 첫 번째 `c` `s` 바이트가 유효한 바이트 버퍼를 가리킵니다.

- `_Outref_result_buffer_all_maybenull_(s)`

     결과는 사후 상태에서 유효해야 하지만 사후 상태에서는 null일 수 있습니다. 크기 `s` 유효한 요소의 유효한 버퍼를 가리킵니다.

- `_Outref_result_bytebuffer_all_maybenull_(s)`

     결과는 사후 상태에서 유효해야 하지만 사후 상태에서는 null일 수 있습니다. 유효한 요소바이트의 `s` 유효한 버퍼를 가리킵니다.

## <a name="return-values"></a>반환 값

함수의 반환 값은 `_Out_` 매개 변수와 유사하지만 다른 참조 수준에 있으므로 결과에 대한 포인터개념을 고려할 필요가 없습니다. 다음 주석의 경우 반환 값은 스칼라, 구조체에 대한 포인터 또는 버퍼에 대한 포인터와 같은 주석이 추가된 개체입니다. 이러한 주석에는 해당 `_Out_` 주석과 동일한 의미 체계가 있습니다.

|||
|-|-|
|`_Ret_z_`<br /><br /> `_Ret_writes_(s)`<br /><br /> `_Ret_writes_bytes_(s)`<br /><br /> `_Ret_writes_z_(s)`<br /><br /> `_Ret_writes_to_(s,c)`<br /><br /> `_Ret_writes_maybenull_(s)`<br /><br /> `_Ret_writes_to_maybenull_(s)`<br /><br /> `_Ret_writes_maybenull_z_(s)`|`_Ret_maybenull_`<br /><br /> `_Ret_maybenull_z_`<br /><br /> `_Ret_null_`<br /><br /> `_Ret_notnull_`<br /><br /> `_Ret_writes_bytes_to_`<br /><br /> `_Ret_writes_bytes_maybenull_`<br /><br /> `_Ret_writes_bytes_to_maybenull_`|

## <a name="format-string-parameters"></a>문자열 매개 변수 서식 지정

- `_Printf_format_string_`매개 변수가 식에서 사용할 형식 `printf` 문자열임을 나타냅니다.

     **예제**

    ```cpp
    int MyPrintF(_Printf_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwprintf(format, args);
           va_end(args);
           return ret;
    }
    ```

- `_Scanf_format_string_`매개 변수가 식에서 사용할 형식 `scanf` 문자열임을 나타냅니다.

     **예제**

    ```cpp
    int MyScanF(_Scanf_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwscanf(format, args);
           va_end(args);
           return ret;
    }
    ```

- `_Scanf_s_format_string_`매개 변수가 식에서 사용할 형식 `scanf_s` 문자열임을 나타냅니다.

     **예제**

    ```cpp
    int MyScanF_s(_Scanf_s_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwscanf_s(format, args);
           va_end(args);
           return ret;
    }
    ```

## <a name="other-common-annotations"></a>기타 일반적인 주석

### <a name="annotations-and-descriptions"></a>주석 및 설명

- `_In_range_(low, hi)`

     `_Out_range_(low, hi)`

     `_Ret_range_(low, hi)`

     `_Deref_in_range_(low, hi)`

     `_Deref_out_range_(low, hi)`

     `_Deref_inout_range_(low, hi)`

     `_Field_range_(low, hi)`

     매개 변수, 필드 또는 결과는 에서 `low` 부터 범위(포함)에 `hi`있습니다. 이와 `_Satisfies_(_Curr_ >= low && _Curr_ <= hi)` 동일하며 적절한 사전 상태 또는 사후 상태 조건과 함께 추가된 객체에 적용됩니다.

    > [!IMPORTANT]
    > 이름에 "in" 및 "out"이 포함되어 있지만 의미 `_In_` 체계는 `_Out_` 이러한 주석에 적용되지 **않습니다.**

- `_Pre_equal_to_(expr)`

     `_Post_equal_to_(expr)`

     추가된 값은 정확히 `expr`. 이와 `_Satisfies_(_Curr_ == expr)` 동일하며 적절한 사전 상태 또는 사후 상태 조건과 함께 추가된 객체에 적용됩니다.

- `_Struct_size_bytes_(size)`

     구조체 또는 클래스 선언에 적용됩니다. 해당 형식의 유효한 개체가 선언된 형식보다 클 수 있으며 에 의해 `size`부여되는 바이트 수가 있음을 나타냅니다. 다음은 그 예입니다.

     `typedef _Struct_size_bytes_(nSize) struct MyStruct {    size_t nSize;    ... };`

     그런 다음 형식 `pM` `MyStruct *` 매개 변수의 바이트내 버퍼 크기를 다음과 같은 것으로 이동합니다.

     `min(pM->nSize, sizeof(MyStruct))`

## <a name="related-resources"></a>관련 참고 자료

[코드 분석 팀 블로그](https://blogs.msdn.microsoft.com/codeanalysis/)

## <a name="see-also"></a>참고 항목

- [SAL 주석을 사용하여 C/C++ 코드 결함 감소](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL 이해](../code-quality/understanding-sal.md)
- [함수 동작에 주석 지정](../code-quality/annotating-function-behavior.md)
- [구조체 및 클래스에 주석 지정](../code-quality/annotating-structs-and-classes.md)
- [잠금 동작에 주석 지정](../code-quality/annotating-locking-behavior.md)
- [주석 적용 시기 및 위치 지정](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [본질적인 기능](../code-quality/intrinsic-functions.md)
- [모범 사례 및 예제](../code-quality/best-practices-and-examples-sal.md)
