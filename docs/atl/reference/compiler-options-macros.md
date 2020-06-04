---
title: 컴파일러 옵션 매크로
ms.date: 08/19/2019
f1_keywords:
- _ATL_ALL_WARNINGS
- _ATL_APARTMENT_THREADED
- '_ATL_CSTRING_EXPLICIT_CONSTRUCTORS '
- _ATL_ENABLE_PTM_WARNING
- _ATL_FREE_THREADED
- _ATL_MULTI_THREADED
- _ATL_NO_AUTOMATIC_NAMESPACE
- _ATL_NO_COM_SUPPORT
- ATL_NO_VTABLE
- ATL_NOINLINE
- _ATL_SINGLE_THREADED
helpviewer_keywords:
- compiler options, macros
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
ms.openlocfilehash: 702324c3300ff23bb60113529a681e3b8fa99354
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331616"
---
# <a name="compiler-options-macros"></a>컴파일러 옵션 매크로

이러한 매크로는 특정 컴파일러 기능을 제어합니다.

|||
|-|-|
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|이전 버전의 ATL에서 변환된 프로젝트의 오류를 가능하게 하는 기호입니다.|
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|하나 이상의 개체가 아파트 스레딩을 사용하는지 정의합니다.|
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|특정 `CString` 생성자가 명시되어 의도하지 않은 변환을 방지합니다.|
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|멤버 함수에 대한 포인터를 초기화하는 데 비표준 구문을 사용할 때 C4867 컴파일러 오류를 생성하는 C++ 표준 호환 구문을 사용하려면 이 매크로를 정의합니다.|
|[_ATL_FREE_THREADED](#_atl_free_threaded)|하나 이상의 개체가 무료 또는 중립 스레딩을 사용하는지 정의합니다.|
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|프로젝트를 나타내는 기호에는 둘 다, 무료 또는 중립으로 표시된 개체가 있습니다. 대신 매크로 [_ATL_FREE_THREADED](#_atl_free_threaded) 사용해야 합니다.|
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|네임스페이스를 ATL로 기본으로 사용하지 못하게 하는 기호입니다.|
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|COM 관련 코드가 프로젝트와 함께 컴파일되지 않도록 하는 기호입니다.|
|[ATL_NO_VTABLE](#atl_no_vtable)|클래스의 생성자 및 소멸자에서 vtable 포인터가 초기화되지 않도록 하는 기호입니다.|
|[ATL_NOINLINE](#atl_noinline)|함수를 나타내는 기호는 인라인되지 않아야 합니다.|
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|모든 개체가 단일 스레딩 모델을 사용하는지 정의합니다.|

## <a name="_atl_all_warnings"></a><a name="_atl_all_warnings"></a>_ATL_ALL_WARNINGS

이전 버전의 ATL에서 변환된 프로젝트의 오류를 가능하게 하는 기호입니다.

```
#define _ATL_ALL_WARNINGS
```

### <a name="remarks"></a>설명

Visual C++ .NET 2002 이전에는 ATL에서 많은 경고를 사용하지 않도록 설정하고 사용자 코드에 나타나지 않도록 설정했습니다. 특히 다음에 대한 내용을 설명합니다.

- C4127 조건부 식이 일정합니다.

- C4786 '식별자' : 디버그 정보의 '번호' 문자로 식별자가 잘렸습니다.

- C4201 비표준 확장 사용 : 이름 없는 구조체/공용 구조체

- C4103 '파일 이름' : #pragma 팩을 사용하여 정렬변경

- C4291 '선언' : 일치하는 연산자 삭제가 없습니다. 초기화가 예외를 throw하면 메모리가 해제되지 않습니다.

- C4268 '식별자' : 컴파일러에서 생성된 기본 생성자로 초기화된 'const' 정적/전역 데이터가 개체를 0으로 채웁니다.

- C4702 연결할 수 없는 코드

이전 버전에서 변환된 프로젝트에서 이러한 경고는 라이브러리 헤더에 의해 여전히 비활성화됩니다.

라이브러리 헤더를 포함하기 전에 *pch.h(Visual* Studio 2017 및 이전) 파일에 다음 줄을 추가하면 이 동작을 변경할 수 있습니다.*stdafx.h*

[!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]

이 `#define` 추가 되는 경우 ATL 헤더는 이러한 경고의 상태를 유지 하 고 전역적으로 사용 하지 않도록 설정 하지 않도록 설정 합니다(또는 사용자가 명시적으로 개별 경고를 사용 하지 않도록 설정 하는 경우).

새 프로젝트는 `#define` 기본적으로 *pch.h* *(visual* Studio 2017 및 이전)에서 이 설정을 설정합니다.

## <a name="_atl_apartment_threaded"></a><a name="_atl_apartment_threaded"></a>_ATL_APARTMENT_THREADED

하나 이상의 개체가 아파트 스레딩을 사용하는지 정의합니다.

```
_ATL_APARTMENT_THREADED
```

### <a name="remarks"></a>설명

아파트 스레딩을 지정합니다. ATL 개체에 사용할 수 있는 스레딩 모델에 [Options, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) 대한 설명은 [프로젝트의 스레딩 모델 지정을](../../atl/specifying-the-threading-model-for-a-project-atl.md) 참조하십시오.

## <a name="_atl_cstring_explicit_constructors"></a><a name="_atl_cstring_explicit_constructors"></a>_ATL_CSTRING_EXPLICIT_CONSTRUCTORS

특정 `CString` 생성자가 명시되어 의도하지 않은 변환을 방지합니다.

```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```

### <a name="remarks"></a>설명

이 생성자가 정의되면 단일 매개 변수를 취하는 모든 CString 생성자는 입력 인수의 암시적 변환을 방지하는 명시적 키워드로 컴파일됩니다. 예를 들어 _UNICODE 정의될 때 char* 문자열을 CString 생성자 인수로 사용하려고 하면 컴파일러 오류가 발생합니다. 좁고 넓은 문자열 형식 간의 암시적 변환을 방지해야 하는 경우에 이 매크로를 사용합니다.

모든 생성자 문자열 인수에서 _T 매크로를 사용하면 _ATL_CSTRING_EXPLICIT_CONSTRUCTORS 정의하고 _UNICODE 정의되었는지 여부에 관계없이 컴파일 오류를 방지할 수 있습니다.

## <a name="_atl_enable_ptm_warning"></a><a name="_atl_enable_ptm_warning"></a>_ATL_ENABLE_PTM_WARNING

멤버 함수에 대한 포인터에 ANSI C++ 표준 준수 구문을 사용하도록 하려면 이 매크로를 정의합니다. 이 매크로를 사용하면 멤버 함수에 대한 포인터를 초기화하는 데 비표준 구문을 사용할 때 C4867 컴파일러 오류가 생성됩니다.

```
#define _ATL_ENABLE_PTM_WARNING
```

### <a name="remarks"></a>설명

ATL 및 MFC 라이브러리가 Microsoft C++ 컴파일러의 향상된 표준 C++ 규정 준수에 맞게 변경되었습니다. ANSI C++ 표준에 따라 클래스 멤버 함수에 대한 포인터 `&CMyClass::MyFunc`구문이 있어야 합니다.

[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) 정의되지 않은 경우(기본 사례) ATL/MFC는 이전 버전에서 생성된 코드가 이전과 같이 계속 빌드될 수 있도록 매크로 맵(특히 메시지 맵)에서 C4867 오류를 사용하지 않도록 설정합니다. **_ATL_ENABLE_PTM_WARNING**정의하는 경우 코드는 C++ 표준을 준수해야 합니다.

그러나 비표준 양식은 더 이상 사용되지 않습니다. 기존 코드를 C++ 표준 호환 구문으로 이동해야 합니다. 예를 들어, 다음 코드는

[!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]

다음으로 변경되어야 합니다.

[!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]

맵 매크로의 경우 앰퍼샌드 '&' 문자를 추가합니다. 코드에 문자를 다시 추가하면 안 됩니다.

## <a name="_atl_free_threaded"></a><a name="_atl_free_threaded"></a>_ATL_FREE_THREADED

하나 이상의 개체가 무료 또는 중립 스레딩을 사용하는지 정의합니다.

```
_ATL_FREE_THREADED
```

### <a name="remarks"></a>설명

무료 스레딩을 지정합니다. 무료 스레딩은 다중 스레드 아파트 모델과 동일합니다. ATL 개체에 사용할 수 있는 스레딩 모델에 [Options, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) 대한 설명은 [프로젝트의 스레딩 모델 지정을](../../atl/specifying-the-threading-model-for-a-project-atl.md) 참조하십시오.

## <a name="_atl_multi_threaded"></a><a name="_atl_multi_threaded"></a>_ATL_MULTI_THREADED

프로젝트를 나타내는 기호에는 둘 다, 무료 또는 중립으로 표시된 개체가 있습니다.

```
_ATL_MULTI_THREADED
```

### <a name="remarks"></a>설명

이 기호가 정의된 경우 ATL은 전역 데이터에 대한 액세스를 올바르게 동기화하는 코드를 가져옵니다. 새 코드는 대신 동등한 매크로 [_ATL_FREE_THREADED](#_atl_free_threaded) 사용해야 합니다.

## <a name="_atl_no_automatic_namespace"></a><a name="_atl_no_automatic_namespace"></a>_ATL_NO_AUTOMATIC_NAMESPACE

네임스페이스를 ATL로 기본으로 사용하지 못하게 하는 기호입니다.

```
_ATL_NO_AUTOMATIC_NAMESPACE
```

### <a name="remarks"></a>설명

이 기호가 정의되지 않은 경우 atlbase.h는 기본적으로 **네임스페이스 ATL을 사용하여** 수행하므로 이름 충돌이 발생할 수 있습니다. 이를 방지하려면 이 기호를 정의합니다.

## <a name="_atl_no_com_support"></a><a name="_atl_no_com_support"></a>_ATL_NO_COM_SUPPORT

COM 관련 코드가 프로젝트와 함께 컴파일되지 않도록 하는 기호입니다.

```
_ATL_NO_COM_SUPPORT
```

## <a name="atl_no_vtable"></a><a name="atl_no_vtable"></a>ATL_NO_VTABLE

클래스의 생성자 및 소멸자에서 vtable 포인터가 초기화되지 않도록 하는 기호입니다.

```
ATL_NO_VTABLE
```

### <a name="remarks"></a>설명

vtable 포인터가 클래스의 생성자 및 소멸자에서 초기화되지 않으면 링커는 vtable과 포인터가 가리키는 모든 함수를 제거할 수 있습니다. **__declspec(노브테이블)로**확장됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]

## <a name="atl_noinline"></a><a name="atl_noinline"></a>ATL_NOINLINE

함수를 나타내는 기호는 인라인되지 않아야 합니다.

```
    ATL_NOINLINE inline
    myfunction()
    {
    ...
    }
```

### <a name="parameters"></a>매개 변수

*마이 기능*<br/>
인라인되지 않아야 하는 함수입니다.

### <a name="remarks"></a>설명

함수가 헤더 파일에 배치될 수 있도록 인라인으로 선언되어야 하는 경우에도 컴파일러에 의해 인라인되지 않도록 하려면 이 기호를 사용합니다. **__declspec(noinline)으로**확장됩니다.

## <a name="_atl_single_threaded"></a><a name="_atl_single_threaded"></a>_ATL_SINGLE_THREADED

모든 개체가 단일 스레딩 모델을 사용하는지 정의합니다.

```
_ATL_SINGLE_THREADED
```

### <a name="remarks"></a>설명

개체가 항상 기본 COM 스레드에서 실행되도록 지정합니다. ATL 개체에 사용할 수 있는 스레딩 모델에 [Options, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) 대한 설명은 [프로젝트의 스레딩 모델 지정을](../../atl/specifying-the-threading-model-for-a-project-atl.md) 참조하십시오.

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
