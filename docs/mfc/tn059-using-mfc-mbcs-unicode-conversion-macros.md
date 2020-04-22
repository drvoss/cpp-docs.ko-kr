---
title: 'TN059: MFC MBCS-유니코드 변환 매크로 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- MFCANS32.DLL
- Unicode [MFC], conversion macros
- Unicode [MFC], OLE interfaces
- conversion macros [MFC]
- converting Unicode
- MBCS [MFC], conversion macros
- macros [MFC], MBCS conversion macros
- TN059
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
ms.openlocfilehash: 657381d8247aef14b2c725996dfeb11d0e0535fe
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749433"
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>TN059: MFC MBCS/유니코드 변환 매크로 사용

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 노트에서는 AFXPRIV에 정의된 MBCS/유니코드 변환에 매크로를 사용하는 방법을 설명합니다. H. 이러한 매크로는 응용 프로그램이 OLE API를 직접 처리하거나 어떤 이유로 유니코드와 MBCS 간에 변환해야 하는 경우에 가장 유용합니다.

## <a name="overview"></a>개요

MFC 3.x에서는 특수 DLL(MFCANS32)이 사용되었습니다. DLL) OLE 인터페이스가 호출될 때 유니코드와 MBCS 간에 자동으로 변환됩니다. 이 DLL은 OLE API와 인터페이스가 항상 유니코드(매킨토시를 제외한)인 것처럼 OLE 응용 프로그램을 작성할 수 있는 거의 투명한 계층이었습니다. 이 계층은 편리하고 응용 프로그램을 Win16에서 Win32로 신속하게 이식할 수 있었지만(MFC, Microsoft Word, Microsoft Excel 및 VBA는 이 기술을 사용한 Microsoft 응용 프로그램 중 일부에 불과함) 때로는 상당한 성능 저하를 겪었습니다. 이러한 이유로 MFC 4.x는 이 DLL을 사용하지 않고 대신 유니코드 OLE 인터페이스와 직접 통신합니다. 이렇게 하려면 MFC는 OLE 인터페이스를 호출할 때 유니코드로 MBCS로 변환해야 하며, OLE 인터페이스를 구현할 때 유니코드에서 MBCS로 변환해야 하는 경우가 많습니다. 이를 효율적이고 쉽게 처리하기 위해 이 변환을 더 쉽게 하기 위해 여러 매크로가 만들어졌습니다.

이러한 매크로 집합을 만드는 가장 큰 장애물 중 하나는 메모리 할당입니다. 문자열을 제자리에서 변환할 수 없으므로 변환된 결과를 보유하는 새 메모리를 할당해야 합니다. 이 작업은 다음과 유사한 코드로 수행할 수 있습니다.

```
// we want to convert an MBCS string in lpszA
int nLen = MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    NULL,
    NULL);

LPWSTR lpszW = new WCHAR[nLen];
MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    lpszW,
    nLen);

// use it to call OLE here
pI->SomeFunctionThatNeedsUnicode(lpszW);

// free the string
delete[] lpszW;
```

이 접근 방식은 여러 가지 문제로 합니다. 가장 큰 문제는 작성, 테스트 및 디버깅이 많은 코드라는 것입니다. 간단한 함수 호출이었던 것이 이제는 훨씬 더 복잡해졌습니다. 또한 이렇게 할 때 상당한 런타임 오버헤드가 있습니다. 메모리는 힙에 할당되어야 하며 변환이 완료될 때마다 해제되어야 합니다. 마지막으로 위의 코드는 유니코드 `#ifdefs` 및 Macintosh 빌드에 대해 적절하게 추가해야 합니다(이 변환이 수행될 필요가 없습니다).

우리가 내놓은 해결책은 1) 다양한 플랫폼 간의 차이를 마스크하고 2) 효율적인 메모리 할당 체계를 사용하고 3) 기존 소스 코드에 쉽게 삽입 할 수있는 매크로를 만드는 것입니다. 다음은 정의 중 하나의 예입니다.

```
#define A2W(lpa) (\
((LPCSTR)lpa == NULL) NULL : (\
    _convert = (strnlen(lpa)+1),\
    AfxA2WHelper((LPWSTR) alloca(_convert*2),
    lpa,
    _convert)\)\)
```

위의 코드 대신이 매크로를 사용하면 상황이 훨씬 간단합니다.

```
// use it to call OLE here
USES_CONVERSION;
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```

변환이 필요한 추가 호출이 있지만 매크로를 사용하는 것은 간단하고 효과적입니다.

각 매크로의 구현은 _alloca() 함수를 사용하여 힙 대신 스택에서 메모리를 할당합니다. 스택에서 메모리를 할당하는 것이 힙에 메모리를 할당하는 것보다 훨씬 빠르며 함수가 종료되면 메모리가 자동으로 해제됩니다. 또한 매크로는 두 번 `MultiByteToWideChar` 이상 `WideCharToMultiByte`호출하지 않습니다. 이 작업은 필요한 것보다 약간 더 많은 메모리를 할당하여 수행됩니다. 우리는 MBC가 최대 하나의 **WCHAR로** 변환되며 각 **WCHAR에** 대해 최대 2개의 MBC 바이트를 갖게 된다는 것을 알고 있습니다. 필요 이상으로 조금 더 할당하되 항상 변환을 처리하기에 충분하여 변환 함수에 대한 두 번째 호출을 피할 수 있습니다. 도우미 함수에 `AfxA2Whelper` 대한 호출은 변환을 수행하기 위해 수행해야 하는 인수 푸시 수를 줄입니다(직접 호출하는 `MultiByteToWideChar` 경우보다 코드가 작아진 경우).

매크로가 임시 길이를 저장할 공간을 갖도록 하려면 변환 매크로를 사용하는 각 함수에서 이 작업을 수행하는 _convert라는 로컬 변수를 선언해야 합니다. 이 작업은 예제에서 위에 나타난 USES_CONVERSION 매크로를 호출하여 수행됩니다.

일반 변환 매크로와 OLE 특정 매크로가 모두 있습니다. 이 두 가지 다른 매크로 집합은 아래에서 설명합니다. 모든 매크로는 AFXPRIV에 있습니다. H.

## <a name="generic-conversion-macros"></a>일반 변환 매크로

일반 변환 매크로는 기본 메커니즘을 형성합니다. 이전 섹션A2W에 표시된 매크로 예제 및 구현은 이러한 "일반" 매크로 중 하나입니다. OLE와 구체적으로 관련이 없습니다. 일반 매크로 집합은 다음과 같습니다.

```
A2CW      (LPCSTR) -> (LPCWSTR)
A2W      (LPCSTR) -> (LPWSTR)
W2CA      (LPCWSTR) -> (LPCSTR)
W2A      (LPCWSTR) -> (LPSTR)
```

텍스트 변환 외에도 매크로 및 도움말 함수를 변환하는 `TEXTMETRIC` `DEVMODE` `BSTR`기능및 및 OLE 할당 된 문자열도 있습니다. 이러한 매크로는 이 토론의 범위를 벗어납니다. 이러한 매크로에 대한 자세한 내용은 H입니다.

## <a name="ole-conversion-macros"></a>OLE 변환 매크로

OLE 변환 매크로는 **OLESTR** 문자를 예상하는 함수를 처리하도록 특별히 설계되었습니다. OLE 헤더를 검사하면 **LPCOLESTR** 및 **OLECHAR에**대한 많은 참조가 표시됩니다. 이러한 형식은 플랫폼에 만국되지 않은 방식으로 OLE 인터페이스에 사용되는 문자 유형을 참조하는 데 사용됩니다. **OLECHAR는** Win16및 매킨토시 플랫폼과 Win32의 **WCHAR에서** **char로** 매핑합니다.

MFC 코드의 **#ifdef** 지시문을 최소한으로 유지하기 위해 OLE 문자열이 관련된 각 변환에 대해 유사한 매크로가 있습니다. 다음 매크로가 가장 일반적으로 사용됩니다.

```
T2COLE   (LPCTSTR) -> (LPCOLESTR)
T2OLE   (LPCTSTR) -> (LPOLESTR)
OLE2CT   (LPCOLESTR) -> (LPCTSTR)
OLE2T   (LPCOLESTR) -> (LPCSTR)
```

다시 말하지만 TEXTMETRIC, DEVMODE, BSTR 및 OLE 할당 문자열을 수행하기위한 유사한 매크로가 있습니다. AFXPRIV를 참조하십시오. 자세한 내용은 H.

## <a name="other-considerations"></a>기타 고려 사항

좁은 루프에서 매크로를 사용하지 마십시오. 예를 들어 다음과 같은 종류의 코드를 작성하지 않으려고 합니다.

```cpp
void BadIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, T2COLE(lpsz));

}
```

위의 코드는 문자열의 `lpsz` 내용에 따라 스택에 메가 바이트의 메모리를 할당 할 수 있습니다! 또한 루프의 각 반복에 대한 문자열을 변환하는 데 시간이 걸립니다. 대신 이러한 상수 변환을 루프 밖으로 이동합니다.

```cpp
void MuchBetterIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, lpszT);

}
```

문자열이 일정하지 않으면 메서드 호출을 함수에 캡슐화합니다. 이렇게 하면 매번 변환 버퍼를 해제할 수 있습니다. 다음은 그 예입니다.

```cpp
void CallSomeMethod(int ii, LPCTSTR lpsz)
{
    USES_CONVERSION;
    pI->SomeMethod(ii, T2COLE(lpsz));

}

void MuchBetterIterateCode2(LPCTSTR* lpszArray)
{
    for (int ii = 0; ii <10000; ii++)
    CallSomeMethod(ii, lpszArray[ii]);

}
```

반환 값이 반환하기 전에 데이터의 복사본을 만드는 것을 의미하지 않는 한 매크로 중 하나의 결과를 반환하지 마십시오. 예를 들어 이 코드는 잘못되었습니다.

```
LPTSTR BadConvert(ISomeInterface* pI)
{
    USES_CONVERSION;
    LPOLESTR lpsz = NULL;
    pI->GetFileName(&lpsz);

LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

return lpszT; // bad! returning alloca memory
}
```

위의 코드는 반환 값을 값을 복사하는 값으로 변경하여 수정할 수 있습니다.

```
CString BetterConvert(ISomeInterface* pI)
{
    USES_CONVERSION;
    LPOLESTR lpsz = NULL;
    pI->GetFileName(&lpsz);

LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

return lpszT; // CString makes copy
}
```

매크로는 사용하기 쉽고 코드에 삽입하기 쉽지만 위의 주의 사항에서 알 수 있듯이 매크로를 사용할 때주의해야합니다.

## <a name="see-also"></a>참조

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
