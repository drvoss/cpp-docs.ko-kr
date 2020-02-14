---
title: 이벤트 추가(ATL 자습서, 5부)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
ms.openlocfilehash: c9a7c6f38a2f47ec808081e440a200737ad1928a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127576"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>이벤트 추가(ATL 자습서, 5부)

이 단계에서는 `ClickIn` 및 `ClickOut` 이벤트를 ATL 컨트롤에 추가 합니다. 사용자가 다각형 내부를 클릭 하 고 사용자가 외부를 클릭 하는 경우 `ClickOut`를 발생 시키는 경우 `ClickIn` 이벤트를 발생 시킵니다. 이벤트를 추가 하는 작업은 다음과 같습니다.

- `ClickIn` 및 `ClickOut` 메서드 추가

- 형식 라이브러리 생성

- 연결 지점 인터페이스 구현

## <a name="adding-the-clickin-and-clickout-methods"></a>ClickIn 및 클릭 메서드 추가

2 단계에서 ATL 컨트롤을 만들 때 **연결점** 확인란을 선택 했습니다. 그러면 Polygon .idl 파일에 `_IPolyCtlEvents` 인터페이스가 생성 됩니다. 인터페이스 이름은 밑줄로 시작 합니다. 인터페이스가 내부 인터페이스 임을 나타내는 규칙입니다. 따라서 COM 개체를 탐색할 수 있는 프로그램은 사용자에 게 인터페이스를 표시 하지 않도록 선택할 수 있습니다. 또한 **연결 지점은** 다각형 .idl 파일에서 다음 줄을 추가 하 여 `_IPolyCtlEvents` 기본 소스 인터페이스 임을 표시 합니다.

`[default, source] dispinterface _IPolyCtlEvents;`

원본 특성은 컨트롤이 알림의 출처 임을 나타내므로 컨테이너에서이 인터페이스를 호출 합니다.

이제 `ClickIn` 및 `ClickOut` 메서드를 `_IPolyCtlEvents` 인터페이스에 추가 합니다.

### <a name="to-add-the-clickin-and-clickout-methods"></a>ClickIn 및 클릭 메서드를 추가 하려면

1. **솔루션 탐색기**에서 Polygon을 열고 PolygonLib 라이브러리의 `dispInterface_IPolyCtlEvents` 선언에 있는 `methods:` 아래에 다음 코드를 추가 합니다.

    ```cpp
   [id(1), helpstring("method ClickIn")] void ClickIn([in] LONG x,[in] LONG y);
   [id(2), helpstring("method ClickOut")] void ClickOut([in] LONG x,[in] LONG y);
    ```

`ClickIn` 및 `ClickOut` 메서드는 클릭 된 지점의 x 및 y 좌표를 매개 변수로 사용 합니다.

## <a name="generating-the-type-library"></a>형식 라이브러리 생성

이 시점에서 형식 라이브러리를 생성 합니다 .이 시점에서 프로젝트는이 라이브러리를 사용 하 여 컨트롤에 대 한 연결 지점 인터페이스와 연결 지점 컨테이너 인터페이스를 생성 하는 데 필요한 정보를 가져옵니다.

### <a name="to-generate-the-type-library"></a>형식 라이브러리를 생성 하려면

1. 프로젝트를 다시 빌드합니다.

     또는

1. **솔루션 탐색기** 에서 Polygon 파일을 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **컴파일** 을 클릭 합니다.

그러면 형식 라이브러리인 Polygon 파일이 생성 됩니다. Polygon 파일은 이진 파일 이므로 직접 보거나 편집할 수 없기 때문에 **솔루션 탐색기**에서 표시 되지 않습니다.

## <a name="implementing-the-connection-point-interfaces"></a>연결 지점 인터페이스 구현

컨트롤에 대 한 연결 지점 인터페이스와 연결 지점 컨테이너 인터페이스를 구현 합니다. COM에서 이벤트는 연결 지점의 메커니즘을 통해 구현 됩니다. COM 개체에서 이벤트를 수신 하기 위해 컨테이너는 COM 개체가 구현 하는 연결 지점에 대 한 advise 연결을 설정 합니다. COM 개체에는 여러 개의 연결 지점이 있을 수 있으므로 COM 개체는 연결 지점 컨테이너 인터페이스도 구현 합니다. 이 인터페이스를 통해 컨테이너는 지원 되는 연결 지점이 무엇 인지 확인할 수 있습니다.

연결 지점을 구현 하는 인터페이스를 `IConnectionPoint`이라고 하며, 연결 지점 컨테이너를 구현 하는 인터페이스를 `IConnectionPointContainer`이라고 합니다.

`IConnectionPoint`구현에 도움이 되도록 연결 지점 구현 마법사를 사용 합니다. 이 마법사는 형식 라이브러리를 읽고 발생 될 수 있는 각 이벤트에 대해 함수를 구현 하 여 `IConnectionPoint` 인터페이스를 생성 합니다.

### <a name="to-implement-the-connection-points"></a>연결 요소를 구현 하려면

1. **솔루션 탐색기**에서 _IPolyCtlEvents_CP를 열고 `CProxy_IPolyCtlEvents` 클래스의 `public:` 문 아래에 다음 코드를 추가 합니다.

    ```cpp
    VOID Fire_ClickIn(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x1, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    VOID Fire_ClickOut(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x2, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    ```

이 파일에는 `IConnectionPointImpl`에서 파생 되는 `CProxy_IPolyCtlEvents` 라는 클래스가 있습니다. 이제 _IPolyCtlEvents_CP는 두 개의 메서드 `Fire_ClickIn` 및 `Fire_ClickOut`를 정의 합니다 .이 두 메서드는 두 개의 좌표 매개 변수를 사용 합니다. 컨트롤에서 이벤트를 발생 시키려는 경우 이러한 메서드를 호출 합니다.

**연결 점으로** 컨트롤 옵션을 선택 하 여 _IPolyCtlEvents_CP 파일을 생성 했습니다. 또한 `CProxy_PolyEvents` 및 `IConnectionPointContainerImpl`를 컨트롤의 여러 상속 목록에 추가 하 고 적절 한 항목을 COM 맵에 추가 하 여 `IConnectionPointContainer` 노출 합니다.

이벤트를 지 원하는 코드를 구현 했습니다. 이제 이벤트를 발생 시키는 코드를 적절 한 순간에 추가 합니다. 사용자가 컨트롤의 왼쪽 마우스 단추를 클릭 하면 `ClickIn` 또는 `ClickOut` 이벤트를 발생 시킬 수 있습니다. 사용자가 단추를 클릭 하는 시기를 확인 하려면 `WM_LBUTTONDOWN` 메시지에 대 한 처리기를 추가 합니다.

### <a name="to-add-a-handler-for-the-wm_lbuttondown-message"></a>WM_LBUTTONDOWN 메시지에 대 한 처리기를 추가 하려면

1. **클래스 뷰**에서 `CPolyCtl` 클래스를 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **속성** 을 클릭 합니다.

1. **속성** 창에서 **메시지** 아이콘을 클릭 한 다음 왼쪽 목록에서 `WM_LBUTTONDOWN`을 클릭 합니다.

1. 표시 되는 드롭다운 목록에서 **\<추가 > OnLButtonDown**을 클릭 합니다. `OnLButtonDown` 처리기 선언이 Polyctl.htm에 추가 되 고 처리기 구현이 Polyctl.htm에 추가 됩니다.

그런 다음 처리기를 수정 합니다.

### <a name="to-modify-the-onlbuttondown-method"></a>OnLButtonDown 메서드를 수정 하려면

1. Polyctl.htm의 `OnLButtonDown` 메서드로 구성 된 코드를 변경 합니다 .이 코드는 마법사에 의해 배치 된 모든 코드를 삭제 하 여 다음과 같이 표시 됩니다.

    [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]

이 코드는 `OnDraw` 함수에서 계산 된 점을 사용 하 여 `PtInRegion`에 대 한 호출로 사용자의 마우스 클릭을 검색 하는 영역을 만듭니다.

*Umsg* 매개 변수는 처리 중인 Windows 메시지의 ID입니다. 이를 통해 메시지 범위를 처리 하는 함수 하나를 사용할 수 있습니다. *WParam* 및 *lParam* 매개 변수는 처리 되는 메시지에 대 한 표준 값입니다. *Bhandled* 매개 변수를 사용 하면 함수에서 메시지를 처리할지 여부를 지정할 수 있습니다. 기본적으로이 값은 값이 TRUE로 설정 되어 함수가 메시지를 처리 했음을 나타내지만 FALSE로 설정할 수 있습니다. 이렇게 하면 ATL이 메시지를 보낼 다른 메시지 처리기 함수를 계속 검색 합니다.

## <a name="building-and-testing-the-control"></a>컨트롤 빌드 및 테스트

이제 이벤트를 사용해 보세요. 컨트롤을 빌드하고 ActiveX 컨트롤 테스트 컨테이너를 다시 시작 합니다. 이번에는 이벤트 로그 창을 확인 합니다. 이벤트를 출력 창으로 라우팅하려면 **옵션** 메뉴에서 **로깅** 을 클릭 하 고 **출력 창에 로그를**선택 합니다. 컨트롤을 삽입 하 고 창에서 클릭 합니다. 채워진 다각형 안쪽을 클릭 하면 `ClickIn` 발생 하며, `ClickOut` 바깥쪽을 클릭 하면 발생 합니다.

다음에는 속성 페이지를 추가 합니다.

&#124; [6 단계에서](../atl/adding-a-property-page-atl-tutorial-part-6.md) [4 단계로](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) 돌아갑니다.

## <a name="see-also"></a>참고 항목

[자습서](../atl/active-template-library-atl-tutorial.md)
