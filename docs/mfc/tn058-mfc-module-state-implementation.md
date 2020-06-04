---
title: 'TN058: MFC 모듈 상태 구현'
ms.date: 06/28/2018
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
ms.openlocfilehash: b64fb6b97474007c44a2124315e83e1ac119f9ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366617"
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058: MFC 모듈 상태 구현

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 기술 노트는 MFC "모듈 상태" 구문의 구현에 대해 설명합니다. 모듈 상태 구현에 대한 이해는 DLL(또는 OLE 내 프로세스 서버)에서 MFC 공유 DLL을 사용하는 데 중요합니다.

이 메모를 읽기 전에 [새 문서, Windows 및 보기 만들기에서](../mfc/creating-new-documents-windows-and-views.md)"MFC 모듈의 상태 데이터 관리"를 참조하십시오. 이 문서에는 이 주제에 대한 중요한 사용 정보 및 개요 정보가 포함되어 있습니다.

## <a name="overview"></a>개요

MFC 상태 정보에는 모듈 상태, 프로세스 상태 및 스레드 상태의 세 가지 종류가 있습니다. 경우에 따라 이러한 상태 형식을 결합할 수 있습니다. 예를 들어 MFC의 핸들 맵은 모듈 로컬 및 스레드 로컬입니다. 이렇게 하면 두 개의 서로 다른 모듈이 각 스레드에 서로 다른 맵을 가질 수 있습니다.

프로세스 상태와 스레드 상태는 비슷합니다. 이러한 데이터 항목은 일반적으로 전역 변수였지만 적절한 Win32s 지원 또는 적절한 다중 스레딩 지원을 위해 지정된 프로세스 또는 스레드에 특정해야 하는 항목입니다. 지정된 데이터 항목이 맞는 범주는 해당 항목과 프로세스 및 스레드 경계와 관련하여 원하는 의미 체계에 따라 다릅니다.

모듈 상태는 로컬 또는 스레드 로컬프로세스인 진정한 글로벌 상태 또는 상태를 포함할 수 있다는 점에서 고유합니다. 또한 신속하게 전환 할 수 있습니다.

## <a name="module-state-switching"></a>모듈 상태 전환

각 스레드에는 "현재" 또는 "활성" 모듈 상태에 대한 포인터가 포함되어 있습니다(당연히 포인터는 MFC의 스레드 로컬 상태의 일부임). 이 포인터는 실행 스레드가 OLE 컨트롤 또는 DLL로 호출하는 응용 프로그램 또는 응용 프로그램으로 다시 호출하는 OLE 컨트롤과 같은 모듈 경계를 통과할 때 변경됩니다.

현재 모듈 상태가 호출하여 `AfxSetModuleState`전환됩니다. 대부분의 경우 API를 직접 처리하지 않습니다. MFC는 대부분의 경우 WinMain, OLE 엔트리 포인트 `AfxWndProc`등에서 당신을 위해 호출합니다. 이 작업은 특수 및 현재 `WndProc`모듈 상태를 알고 있는 특수(또는)에 `WinMain` `DllMain`정적으로 연결하여 작성하는 모든 구성 요소에서 수행됩니다. DLLMODUL을 보면 이 코드를 볼 수 있습니다. CPP 또는 아모둘. MFC\SRC 디렉토리의 CPP입니다.

모듈 상태를 설정한 다음 다시 설정하지 않으려는 경우는 드뭅니다. 대부분의 경우 자신의 모듈 상태를 현재 모듈 상태로 "푸시"한 다음 완료한 후 원래 컨텍스트를 다시 "팝"합니다. 이 작업은 매크로 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) 특수 클래스에 `AFX_MAINTAIN_STATE`의해 수행됩니다.

`CCmdTarget`모듈 상태 전환을 지원하기 위한 특수 기능이 있습니다. 특히, A는 `CCmdTarget` OLE 자동화 및 OLE COM 진입점에 사용되는 루트 클래스입니다. 시스템에 노출된 다른 진입점과 마찬가지로 이러한 진입점은 올바른 모듈 상태를 설정해야 합니다. 주어진 `CCmdTarget` "올바른" 모듈 상태가 무엇인지 어떻게 알 수 있습니까 대답은 "현재" 모듈 상태가 생성될 때 "기억"하여 나중에 호출될 때 현재 모듈 상태를 "기억" 값으로 설정할 수 있다는 것입니다. 따라서 지정된 `CCmdTarget` 개체가 연관된 모듈 상태는 개체가 생성될 때 현재 상태인 모듈 상태입니다. INPROC 서버를 로드하고, 개체를 만들고, 해당 메서드를 호출하는 간단한 예제를 예로 들어 보겠습니다.

1. DLL은 OLE에서 를 `LoadLibrary`사용하여 로드됩니다.

1. `RawDllMain`을 먼저 호출합니다. 모듈 상태를 DLL에 대해 알려진 정적 모듈 상태로 설정합니다. 이러한 이유로 `RawDllMain` DLL에 정적으로 연결됩니다.

1. 개체와 연결된 클래스 팩터리의 생성자가 호출됩니다. `COleObjectFactory`에서 파생 `CCmdTarget` 되고 결과적으로, 그것은 모듈 상태 는 인스턴스화 된 기억. 이것은 중요합니다 - 클래스 팩터리에서 개체를 만들라는 메시지가 표시됩니다.

1. `DllGetClassObject`클래스 팩터리를 얻기 위해 호출됩니다. MFC는 이 모듈과 연결된 클래스 팩터리 목록을 검색하여 반환합니다.

1. `COleObjectFactory::XClassFactory2::CreateInstance`을 호출합니다. 개체를 만들고 반환하기 전에 이 함수는 모듈 상태를 3단계의 현재 상태(인스턴스화시 현재 `COleObjectFactory` 상태)로 설정합니다. 이것은 [METHOD_PROLOGUE](com-interface-entry-points.md)내부에서 수행됩니다.

1. 개체를 만들 때 너무 `CCmdTarget` 파생 이며 동일한 방식으로 `COleObjectFactory` 활성화 된 모듈 상태를 기억, 그래서이 새 개체를 수행 합니다. 이제 개체는 호출될 때마다 전환할 모듈 상태를 알고 있습니다.

1. 클라이언트는 호출에서 받은 OLE COM 개체의 `CoCreateInstance` 함수를 호출합니다. 개체가 호출되면 모듈 `METHOD_PROLOGUE` 상태를 전환하는 데 `COleObjectFactory` 사용됩니다.

보시다시피 모듈 상태는 생성될 때 개체에서 개체로 전파됩니다. 모듈 상태를 적절하게 설정하는 것이 중요합니다. 설정되지 않은 경우 DLL 또는 COM 개체가 호출하는 MFC 응용 프로그램과 제대로 상호 작용하지 않거나 자체 리소스를 찾을 수 없거나 다른 비참한 방법으로 실패할 수 있습니다.

특정 종류의 DLL, 특히 "MFC 확장" DLL은 모듈 상태를 `RawDllMain` 전환하지 않습니다(실제로는 일반적으로 모듈 `RawDllMain`상태가 없습니다). 이는 실제로 응용 프로그램을 사용하는 응용 프로그램에 있는 것처럼 작동하기 위한 것이기 때문입니다. 실행 중인 응용 프로그램의 일부이며 해당 응용 프로그램의 전역 상태를 수정하려는 의도입니다.

OLE 컨트롤 및 기타 DLL은 매우 다릅니다. 호출 응용 프로그램의 상태를 수정하지 않으려고 합니다. 호출하는 응용 프로그램은 MFC 응용 프로그램이 아니므로 수정할 상태가 없을 수 있습니다. 이것이 모듈 상태 전환이 발명된 이유입니다.

DLL에서 대화 상자를 시작하는 함수와 같이 DLL에서 내보낸 함수의 경우 함수의 시작 부분에 다음 코드를 추가해야 합니다.

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

이렇게 하면 현재 모듈 상태가 [AfxGetStaticModuleState에서](reference/extension-dll-macros.md#afxgetstaticmodulestate) 현재 범위가 끝날 때까지 반환된 상태로 바꿉니다.

AFX_MODULE_STATE 매크로를 사용하지 않으면 DLL의 리소스 문제가 발생합니다. 기본적으로 MFC는 주 응용 프로그램의 리소스 핸들을 사용하여 리소스 템플릿을 로드합니다. 이 템플릿은 실제로 DLL에 저장됩니다. 근본 원인은 MFC의 모듈 상태 정보가 AFX_MODULE_STATE 매크로에 의해 전환되지 않았기 때문에 입니다. 리소스 핸들은 MFC의 모듈 상태에서 복구됩니다. 모듈 상태를 전환하지 않아 잘못된 리소스 핸들이 사용됩니다.

AFX_MODULE_STATE DLL의 모든 함수에 넣을 필요는 없습니다. 예를 들어 `InitInstance` MFC가 모듈 상태를 자동으로 `InitInstance` 전환한 다음 반환 후 `InitInstance` 다시 전환하기 때문에 AFX_MODULE_STATE 않고 응용 프로그램의 MFC 코드에서 호출할 수 있습니다. 모든 메시지 맵 처리기에서도 마찬가지입니다. 일반 MFC DLL에는 실제로 메시지를 라우팅하기 전에 모듈 상태를 자동으로 전환하는 특수 마스터 창 프로시저가 있습니다.

## <a name="process-local-data"></a>로컬 데이터 처리

Win32s DLL 모델의 난이도가 아니라면 프로세스 로컬 데이터는 큰 문제가 되지 않을 것입니다. Win32s에서 모든 DLL은 여러 응용 프로그램에서 로드된 경우에도 글로벌 데이터를 공유합니다. 이는 각 DLL이 DLL에 첨부되는 각 프로세스에서 데이터 공간의 별도 복사본을 얻는 "실제" Win32 DLL 데이터 모델과는 매우 다릅니다. 복잡성을 더하기 위해 Win32s DLL의 힙에 할당된 데이터는 실제로 특정 프로세스입니다(적어도 소유권이 가는 한). 다음 데이터 및 코드를 고려하십시오.

```cpp
static CString strGlobal; // at file scope

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, strGlobal);
}
```

위의 코드가 DLL에 있고 DLL이 두 프로세스 A와 B에 의해 로드되는 경우 어떻게 되는지 고려하십시오(실제로 동일한 응용 프로그램의 두 인스턴스일 수 있음). 호출합니다. `SetGlobalString("Hello from A")` 결과적으로 프로세스 `CString` A. `CString` 자체가 전역이며 A와 B 모두에 표시된다는 점을 염두에 두어야 합니다. 이제 B가 호출합니다. `GetGlobalString(sz, sizeof(sz))` B는 A가 설정한 데이터를 볼 수 있습니다. Win32s는 Win32와 같은 프로세스 간에 보호를 제공하지 않기 때문입니다. 이것이 첫 번째 문제입니다. 대부분의 경우 하나의 응용 프로그램이 다른 응용 프로그램에서 소유한 것으로 간주되는 전역 데이터에 영향을 주는 것은 바람직하지 않습니다.

추가 문제도 있습니다. 이제 A가 종료되었다고 가정해 봅시다. A가 종료되면 ' 문자열에서`strGlobal`사용하는 메모리를 시스템에 사용할 수 있게 됩니다. `CString` 소멸자가 호출되기 때문에 해제되지 않습니다. 아직 호출되지 않았습니다. 할당된 응용 프로그램이 장면을 떠났기 때문에 해제됩니다. 이제 B가 `GetGlobalString(sz, sizeof(sz))`호출되면 유효한 데이터가 얻을 수 없습니다. 다른 응용 프로그램에서 는 다른 용도로 해당 메모리를 사용했을 수 있습니다.

분명히 문제가 있습니다. MFC 3.x는 TLS(스레드 로컬 저장소)라는 기술을 사용했습니다. MFC 3.x는 Win32s에서 실제로 프로세스 로컬 저장소 인덱스로 작동하는 TLS 인덱스를 할당합니다. 이는 Win32에 스레드 로컬 데이터를 저장하는 데 사용된 TLS 인덱스와 유사합니다(해당 주제에 대한 자세한 내용은 아래 참조). 이로 인해 모든 MFC DLL은 프로세스당 적어도 두 개의 TLS 인덱스를 활용하게 되었습니다. 많은 OLE 제어 DDL(OCX)을 로드하는 것을 고려할 때 TLS 지수가 빠르게 소진됩니다(사용 가능한 경우 는 64개만 있음). 또한 MFC는 이 모든 데이터를 하나의 구조로 한 곳에 배치해야 했습니다. 그것은 매우 확장되지 않았으며 TLS 지수의 사용과 관련하여 이상적이지 않았습니다.

MFC 4.x는 로컬 프로세스해야 하는 데이터를 "래핑"할 수 있는 클래스 템플릿 집합으로 이 주소를 해결합니다. 예를 들어 위에서 언급한 문제는 다음과 같이 작성하여 해결할 수 있습니다.

```cpp
struct CMyGlobalData : public CNoTrackObject
{
    CString strGlobal;
};
CProcessLocal<CMyGlobalData> globalData;

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    globalData->strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, globalData->strGlobal);
}
```

MFC는 이를 두 단계로 구현합니다. 첫째, Win32 __Tls\* __ API(TlsAlloc,**TlsAlloc** **TlsSetValue,** **TlsGetValue**등)의 상단에 는 프로세스당 두 개의 TLS 인덱스만 사용하는 계층이 있습니다. 둘째, `CProcessLocal` 이 데이터에 액세스하기 위해 템플릿이 제공됩니다. 위에서 볼 수 있는 직관적인 구문을 허용하는 연산자 > 재정의합니다. 래핑된 모든 `CProcessLocal` 개체는 에서 `CNoTrackObject`파생되어야 합니다. `CNoTrackObject`프로세스가 종료될 때 MFC가 프로세스 로컬 개체를 자동으로 파괴할 수 있도록 하위 수준 할당자(LocalAlloc/**LocalFree)와**가상 소멸자(virtual destroyctor)를 제공합니다.**LocalAlloc** 이러한 개체는 추가 정리가 필요한 경우 사용자 지정 소멸자가 있을 수 있습니다. 컴파일러는 포함된 `CString` 개체를 파괴하기 위해 기본 소멸자를 생성하므로 위의 예제에서는 하나를 필요로 하지 않습니다.

이 접근 방식에는 다른 흥미로운 이점이 있습니다. 모든 `CProcessLocal` 개체가 자동으로 소멸될 뿐만 아니라 필요할 때까지 생성되지 않습니다. `CProcessLocal::operator->`을 참조하면 연결된 개체가 호출될 때 인스턴스화되고 더 빨리 인스턴스화되지 않습니다. 위의 예에서 ' 문자열은`strGlobal`처음 호출될 때까지 생성되지 `SetGlobalString` 않거나 `GetGlobalString` 호출되지 않음을 의미합니다. 경우에 따라 DLL 시작 시간을 줄이는 데 도움이 될 수 있습니다.

## <a name="thread-local-data"></a>스레드 로컬 데이터

로컬 데이터를 처리하는 것과 마찬가지로 데이터가 지정된 스레드에 로컬이어야 하는 경우 스레드 로컬 데이터가 사용됩니다. 즉, 해당 데이터에 액세스하는 각 스레드에 대해 별도의 데이터 인스턴스가 필요합니다. 이것은 광범위한 동기화 메커니즘 대신 여러 번 사용할 수 있습니다. 여러 스레드에서 데이터를 공유할 필요가 없는 경우 이러한 메커니즘은 비용이 많이 들고 불필요할 수 있습니다. 위의 샘플과 `CString` 마찬가지로 개체가 있다고 가정합니다. 템플릿으로 래핑하여 스레드를 로컬로 `CThreadLocal` 만들 수 있습니다.

```cpp
struct CMyThreadData : public CNoTrackObject
{
    CString strThread;
};
CThreadLocal<CMyThreadData> threadData;

void MakeRandomString()
{
    // a kind of card shuffle (not a great one)
    CString& str = threadData->strThread;
    str.Empty();
    while (str.GetLength() != 52)
    {
        unsigned int randomNumber;
        errno_t randErr;
        randErr = rand_s(&randomNumber);

        if (randErr == 0)
        {
            TCHAR ch = randomNumber % 52 + 1;
            if (str.Find(ch) <0)
            str += ch; // not found, add it
        }
    }
}
```

서로 `MakeRandomString` 다른 두 스레드에서 호출된 경우 각 스레드는 다른 스레드를 방해하지 않고 서로 다른 방식으로 문자열을 "섞는"것입니다. 이는 실제로 하나의 전역 `strThread` 인스턴스가 아닌 스레드당 인스턴스가 있기 때문입니다.

루프 반복당 한 번이 `CString` 아니라 참조를 사용하여 주소를 한 번 캡처하는 방법을 설명합니다. 루프 코드는 `threadData->strThread` 어디에지에 ''로`str`작성되었을 수 있지만 코드는 실행 속도가 훨씬 느려집니다. 이러한 참조가 루프에서 발생할 때 데이터에 대한 참조를 캐시하는 것이 가장 좋습니다.

클래스 `CThreadLocal` 템플릿은 `CProcessLocal` 수행하는 것과 동일한 구현 기술과 동일한 메커니즘을 사용합니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
