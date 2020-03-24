---
title: 일반 규칙 및 제한 사항
ms.date: 11/04/2016
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
ms.openlocfilehash: 1adbaf9d9be3a0fc0724603e01b81700554839bc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188599"
---
# <a name="general-rules-and-limitations"></a>일반 규칙 및 제한 사항

**Microsoft 전용**

- **Dllimport** 또는 **dllexport** 특성을 사용 하지 않고 함수 또는 개체를 선언 하는 경우 함수 또는 개체는 DLL 인터페이스의 일부분으로 간주 되지 않습니다. 따라서 해당 모듈 또는 같은 프로그램의 다른 모듈에 함수 또는 개체의 정의가 있어야 합니다. DLL 인터페이스의 함수 또는 개체 부분을 만들려면 다른 모듈에서 함수 또는 개체의 정의를 **dllexport**로 선언 해야 합니다. 그렇게 하지 않으면 링커 오류가 생성됩니다.

   **Dllexport** 특성을 사용 하 여 함수 또는 개체를 선언 하는 경우 해당 정의가 같은 프로그램의 일부 모듈에 표시 되어야 합니다. 그렇게 하지 않으면 링커 오류가 생성됩니다.

- 프로그램의 단일 모듈에 동일한 함수 또는 개체에 대 한 **dllimport** 및 **dllexport** 선언이 모두 포함 된 경우 **dllexport** 특성이 **dllimport** 특성 보다 우선적으로 적용 됩니다. 그러나 이 경우 컴파일러 경고가 생성됩니다. 예를 들면 다음과 같습니다.

    ```cpp
    __declspec( dllimport ) int i;
    __declspec( dllexport ) int i;   // Warning; inconsistent;
                                     // dllexport takes precedence.
    ```

- 에서는 C++ **dllimport** 특성을 사용 하 여 선언 된 데이터 개체의 주소를 사용 하 여 전역적으로 선언 되거나 정적 로컬 데이터 포인터를 초기화할 수 있습니다. 그러면 C에서 오류를 생성 합니다. 또한 **dllimport** 특성으로 선언 된 함수의 주소를 사용 하 여 정적 로컬 함수 포인터를 초기화할 수 있습니다. C에서는 이러한 대입으로 인해 포인터가 함수의 주소 대신 DLL 가져오기 썽크(함수로 제어를 전송하는 코드 스텁)의 주소로 설정됩니다. C++에서는 포인터가 함수의 주소로 설정됩니다. 예를 들면 다음과 같습니다.

    ```cpp
    __declspec( dllimport ) void func1( void );
    __declspec( dllimport ) int i;

    int *pi = &i;                             // Error in C
    static void ( *pf )( void ) = &func1;     // Address of thunk in C,
                                              // function in C++

    void func2()
    {
       static int *pi = &i;                  // Error in C
       static void ( *pf )( void ) = &func1; // Address of thunk in C,
                                             // function in C++
    }
    ```

   그러나 개체 선언에 **dllexport** 특성을 포함 하는 프로그램은 프로그램의 어딘가에 해당 개체에 대 한 정의를 제공 해야 하므로 **dllexport** 함수의 주소를 사용 하 여 전역 또는 로컬 정적 함수 포인터를 초기화할 수 있습니다. 마찬가지로, **dllexport** 데이터 개체의 주소로 전역 또는 로컬 정적 데이터 포인터를 초기화할 수 있습니다. 예를 들어, 다음 코드는 C 또는 C++에서 오류를 발생시키지 않습니다.

    ```cpp
    __declspec( dllexport ) void func1( void );
    __declspec( dllexport ) int i;

    int *pi = &i;                              // Okay
    static void ( *pf )( void ) = &func1;      // Okay

    void func2()
    {
        static int *pi = &i;                   // Okay
        static void ( *pf )( void ) = &func1;  // Okay
    }
    ```

- **Dllexport**로 표시 되지 않은 기본 클래스가 있는 일반 클래스에 **dllexport** 를 적용 하는 경우 컴파일러는 C4275를 생성 합니다.

   컴파일러는 기본 클래스가 클래스 템플릿의 특수화인 경우 동일한 경고를 생성합니다. 이 문제를 해결 하려면 기본 클래스를 **dllexport**로 표시 합니다. 클래스 템플릿의 특수화와 관련 된 문제는 **__declspec (dllexport)** 를 저장할 위치입니다. 클래스 템플릿을 표시할 수 없습니다. 대신, 명시적으로 클래스 템플릿을 인스턴스화하고이 명시적 인스턴스화를 **dllexport**로 표시 합니다. 예를 들면 다음과 같습니다.

    ```cpp
    template class __declspec(dllexport) B<int>;
    class __declspec(dllexport) D : public B<int> {
    // ...
    ```

   템플릿 인수가 파생 클래스일 경우 이 해결 방법은 실패합니다. 예를 들면 다음과 같습니다.

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

   이는 템플릿을 사용 하는 일반적인 패턴 이므로 하나 이상의 기본 클래스를 포함 하는 클래스에 적용 되 고 하나 이상의 기본 클래스가 클래스 템플릿의 특수화 인 경우 컴파일러가 **dllexport** 의 의미 체계를 변경 했습니다. 이 경우 컴파일러는 클래스 템플릿의 특수화에 **dllexport** 를 암시적으로 적용 합니다. 다음 작업을 수행 하 고 경고를 받을 수 없습니다.

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[dllexport, dllimport](../cpp/dllexport-dllimport.md)
