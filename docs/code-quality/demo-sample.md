---
title: 코드 분석을 위한 샘플 C++ 프로젝트
description: Visual Studio에서 Microsoft C++에 대한 코드 분석 연습에서 사용할 샘플 솔루션을 만드는 방법
ms.date: 04/14/2020
ms.topic: sample
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
ms.openlocfilehash: c2a1b8c80b7e7aebd1f1530c66ade5859b392028
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372056"
---
# <a name="sample-c-project-for-code-analysis"></a>코드 분석을 위한 샘플 C++ 프로젝트

다음 절차에서는 [연습: 결함에 대한 C/C++ 코드 분석에](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md)대한 샘플을 만드는 방법을 보여 준다. 이 절차에서는 다음을 생성합니다.

- *CppDemo라는*시각적 스튜디오 솔루션 .

- *코드Defects라는*정적 라이브러리 프로젝트 .

- *주석이라는*정적 라이브러리 프로젝트 .

절차에서는 헤더에 대해 코드를 제공하고, 정적 라이브러리에 대해 *.cpp* 파일을 제공합니다.

## <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>CppDemo 솔루션 및 CodeDefects 프로젝트 만들기

::: moniker range=">=vs-2019"

1. 비주얼 스튜디오를 열고 **새 프로젝트 만들기를** 선택합니다.

1. 새 **프로젝트** 만들기 대화 상자에서 언어 필터를 **C++로**변경합니다.

1. **Windows 데스크톱 마법사를** 선택하고 다음 단추를 **선택합니다.**

1. 새 **프로젝트 구성** 페이지에서 프로젝트 **이름** 텍스트 상자에 *CodeDefects를 입력합니다.*

1. 솔루션 **이름** 텍스트 상자에 *CppDemo*를 입력합니다.

1. **만들기**를 선택합니다.

1. Windows **데스크톱 프로젝트** 대화 상자에서 **응용 프로그램 유형을** 정적 **라이브러리(.lib)로**변경합니다.

1. **추가 옵션**에서 **빈 프로젝트**를 선택합니다.

1. **확인을** 선택하여 솔루션 및 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="vs-2017"

1. Visual Studio를 엽니다. 메뉴 모음에서**새** > **프로젝트** **파일** > 을 선택합니다.

1. 새 **프로젝트** 대화 상자에서 **Visual C++** > **Windows 데스크톱을**선택합니다.

1. **윈도우 데스크톱 마법사를**선택합니다.

1. **이름** 텍스트 상자에 *Code결함을 입력합니다.*

1. 솔루션 **이름** 텍스트 상자에 *CppDemo*를 입력합니다.

1. **확인을**선택합니다.

1. Windows **데스크톱 프로젝트** 대화 상자에서 **응용 프로그램 유형을** 정적 **라이브러리(.lib)로**변경합니다.

1. **추가 옵션**에서 **빈 프로젝트**를 선택합니다.

1. **확인을** 선택하여 솔루션 및 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="vs-2015"

1. Visual Studio를 엽니다. 메뉴 모음에서**새** > **프로젝트** **파일** > 을 선택합니다.

1. 새 **프로젝트** 대화 상자에서 템플릿 **시각적 C++** > **Win32를** **선택합니다.** >

1. **Win32 콘솔 응용 프로그램을**선택합니다.

1. **이름** 텍스트 상자에 *Code결함을 입력합니다.*

1. 솔루션 **이름** 텍스트 상자에 *CppDemo*를 입력합니다.

1. **확인을**선택합니다.

1. **Win32 응용 프로그램 마법사** 대화 상자에서 **다음** 단추를 선택합니다.

1. 응용 프로그램 형식을 **정적 라이브러리로** **변경합니다.**

1. **추가 옵션에서** **미리 컴파일된 헤더를 선택 취소합니다.**

1. **완료를** 선택하여 솔루션 및 프로젝트를 작성합니다.

::: moniker-end

## <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>CodeDefects 프로젝트에 헤더 및 원본 파일 추가

1. 솔루션 탐색기에서 **CodeDefect를 확장합니다.**

1. 마우스 오른쪽 단추 를 클릭하여 **헤더 파일에**대한 컨텍스트 메뉴를 엽니다. 새 항목 **추가를** > **선택합니다.**

1. 새 **항목 추가** 대화 상자에서 **Visual C++** > **코드를**선택한 다음 **헤더 파일(.h)을 선택합니다.**

1. **이름** 편집 상자에서 *Bug.h를*입력한 다음 **추가** 단추를 선택합니다.

1. *Bug.h의*편집 창에서 내용을 선택하고 삭제합니다.

1. 다음 코드를 복사하여 편집기에서 *Bug.h* 파일에 붙여넣습니다.

    ```cpp
    #pragma once

    #include <windows.h>

    // Function prototypes
    bool CheckDomain(wchar_t const *);
    HRESULT ReadUserAccount();

    // These constants define the common sizes of the
    // user account information throughout the program
    const int USER_ACCOUNT_LEN = 256;
    const int ACCOUNT_DOMAIN_LEN = 128;
    ```

1. 솔루션 탐색기에서 마우스 오른쪽 단추를 클릭하여 **소스 파일의**컨텍스트 메뉴를 엽니다. 새 항목 **추가를** > **선택합니다.**

1. **새 항목 추가** 대화 상자에서 **C++ 파일(.cpp)** 을 선택합니다.

1. **이름** 편집 상자에서 *Bug.cpp를*입력한 다음 **추가** 단추를 선택합니다.

1. 다음 코드를 복사하여 편집기에서 *Bug.cpp* 파일에 붙여넣습니다.

    ```cpp
    #include "Bug.h"

    // the user account
    wchar_t g_userAccount[USER_ACCOUNT_LEN] = { L"domain\\user" };
    int len = 0;

    bool CheckDomain(wchar_t const* domain)
    {
        return (wcsnlen_s(domain, USER_ACCOUNT_LEN) > 0);
    }

    HRESULT ReadUserAccount()
    {
        return S_OK;
    }

    bool ProcessDomain()
    {
        wchar_t* domain = new wchar_t[ACCOUNT_DOMAIN_LEN];
        // ReadUserAccount gets a 'domain\user' input from
        //the user into the global 'g_userAccount'
        if (ReadUserAccount())
        {
            // Copies part of the string prior to the '\'
            // character onto the 'domain' buffer
            for (len = 0; (len < ACCOUNT_DOMAIN_LEN) && (g_userAccount[len] != L'\0'); len++)
            {
                if (g_userAccount[len] == L'\\')
                {
                    // Stops copying on the domain and user separator ('\')
                    break;
                }
                domain[len] = g_userAccount[len];
            }
            if ((len = ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != L'\\'))
            {
                // '\' was not found. Invalid domain\user string.
                delete[] domain;
                return false;
            }
            else
            {
                domain[len] = L'\0';
            }
            // Process domain string
            bool result = CheckDomain(domain);

            delete[] domain;
            return result;
        }
        return false;
    }

    int path_dependent(int n)
    {
        int i;
        int j;
        if (n == 0)
            i = 1;
        else
            j = 1;
        return i + j;
    }
    ```

1. 메뉴 모음에서 모두 저장 **을** > **선택합니다.**

## <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>주석 프로젝트 추가 및 정적 라이브러리로 구성

::: moniker range=">=vs-2019"

1. 솔루션 탐색기에서 **CppDemo를** 마우스 오른쪽 단추로 클릭하여 컨텍스트 메뉴를 엽니다. 새 프로젝트 **추가를** > **선택합니다.**

1. 새 프로젝트 대화 상자 **추가에서** **Windows 데스크톱 마법사를**선택한 다음 **다음** 단추를 선택합니다.

1. 새 **프로젝트 구성** 페이지에서 프로젝트 **이름** 텍스트 상자에 *주석을*입력한 다음 **을**선택합니다.

1. Windows **데스크톱 프로젝트** 대화 상자에서 **응용 프로그램 유형을** 정적 **라이브러리(.lib)로**변경합니다.

1. **추가 옵션**에서 **빈 프로젝트**를 선택합니다.

1. 프로젝트를 만들려면 **확인을** 선택합니다.

::: moniker-end

::: moniker range="vs-2017"

1. 솔루션 탐색기에서 **CppDemo를** 마우스 오른쪽 단추로 클릭하여 컨텍스트 메뉴를 엽니다. 새 프로젝트 **추가를** > **선택합니다.**

1. 새 **프로젝트 추가** 대화 상자에서 **Visual C++** > **Windows 데스크톱을**선택합니다.

1. **윈도우 데스크톱 마법사를**선택합니다.

1. **이름** 텍스트 상자에 *주석을*입력한 다음 **확인을**선택합니다.

1. Windows **데스크톱 프로젝트** 대화 상자에서 **응용 프로그램 유형을** 정적 **라이브러리(.lib)로**변경합니다.

1. **추가 옵션**에서 **빈 프로젝트**를 선택합니다.

1. 프로젝트를 만들려면 **확인을** 선택합니다.

::: moniker-end

::: moniker range="vs-2015"

1. 솔루션 탐색기에서 **CppDemo를** 마우스 오른쪽 단추로 클릭하여 컨텍스트 메뉴를 엽니다. 새 프로젝트 **추가를** > **선택합니다.**

1. 새 **프로젝트 추가** 대화 상자에서 **시각적 C++** > **Win32를**선택합니다.

1. **Win32 콘솔 응용 프로그램을**선택합니다.

1. **이름** 텍스트 상자에 *주석을 입력합니다.*

1. **확인을**선택합니다.

1. **Win32 응용 프로그램 마법사** 대화 상자에서 **다음** 단추를 선택합니다.

1. 응용 프로그램 형식을 **정적 라이브러리로** **변경합니다.**

1. **추가 옵션에서** **미리 컴파일된 헤더를 선택 취소합니다.**

1. 프로젝트를 작성하려면 **완료를** 선택합니다.

::: moniker-end

## <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>주석 프로젝트에 헤더 파일 및 원본 파일 추가

1. 솔루션 탐색기에서 **주석을 확장합니다.**

1. 오른쪽 단추를 클릭하여 주석 아래에 있는 **헤더 파일의** 컨텍스트 메뉴를 **엽니다.** 새 항목 **추가를** > **선택합니다.**

1. 새 **항목 추가** 대화 상자에서 **Visual C++** > **코드를**선택한 다음 **헤더 파일(.h)을 선택합니다.**

1. **이름** 편집 상자에서 *주석.h를*입력한 다음 **추가** 단추를 선택합니다.

1. *주석에*대한 편집 창에서 내용을 선택하고 삭제합니다.

1. 다음 코드를 복사하여 편집기에서 *annotations.h* 파일에 붙여넣습니다.

    ```cpp
    #pragma once
    #include <sal.h>

    struct LinkedList
    {
        struct LinkedList* next;
        int data;
    };

    typedef struct LinkedList LinkedList;

    _Ret_maybenull_ LinkedList* AllocateNode();
    ```

1. 솔루션 탐색기에서 마우스 오른쪽 단추를 클릭하여 **주석**아래에 **있는 소스 파일에** 대한 컨텍스트 메뉴를 엽니다. 새 항목 **추가를** > **선택합니다.**

1. **새 항목 추가** 대화 상자에서 **C++ 파일(.cpp)** 을 선택합니다.

1. **이름** 편집 상자에 *annotations.cpp를*입력한 다음 **추가** 단추를 선택합니다.

1. 다음 코드를 복사하여 편집기에서 *annotations.cpp* 파일에 붙여넣습니다.

    ```cpp
    #include "annotations.h"
    #include <malloc.h>

    _Ret_maybenull_ LinkedList* AllocateNode()
    {
        LinkedList* result = static_cast<LinkedList*>(malloc(sizeof(LinkedList)));
        return result;
    }

    LinkedList* AddTail(LinkedList* node, int value)
    {
        // finds the last node
        while (node->next != nullptr)
        {
            node = node->next;
        }

        // appends the new node
        LinkedList* newNode = AllocateNode();
        newNode->data = value;
        newNode->next = 0;
        node->next = newNode;

        return newNode;
    }
    ```

1. 메뉴 모음에서 모두 저장 **을** > **선택합니다.**

이제 솔루션이 완성되고 오류 없이 빌드됩니다.

::: moniker range="vs-2017"

> [!NOTE]
> Visual Studio 2017에서는 IntelliSense `E1097 unknown attribute "no_init_all"` 엔진에 가짜 경고가 표시될 수 있습니다. 이 경고는 무시해도 됩니다.

::: moniker-end
