---
title: 애플리케이션 컨트롤
ms.date: 11/04/2016
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
ms.openlocfilehash: 7e18b4504ddbfdd9a4399f33c34c6e6e9900233b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752861"
---
# <a name="application-control"></a>애플리케이션 컨트롤

OLE는 응용 프로그램과 해당 개체를 실질적으로 제어해야 합니다. OLE 시스템 DLL은 응용 프로그램을 자동으로 시작하고 릴리스하고 개체의 생산 및 수정을 조정하는 등의 등으로 응용 프로그램을 시작할 수 있어야 합니다. 이 항목의 함수는 이러한 요구 사항을 충족합니다. OLE 시스템 DLL에서 호출되는 것 외에도 이러한 함수는 응용 프로그램에서도 호출해야 합니다.

### <a name="application-control"></a>애플리케이션 컨트롤

|||
|-|-|
|[AfxOleCanExitApp](#afxolecanexitapp)|애플리케이션이 종료될 수 있는지 여부를 나타냅니다.|
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|응용 프로그램의 현재 메시지 필터를 검색합니다.|
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|현재 사용자 제어 플래그를 검색합니다.|
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|사용자 제어 플래그를 설정하거나 지웁습니다.|
|[AfxOleLockApp](#afxolelockapp)|응용 프로그램의 활성 개체 수에 대한 프레임워크의 전역 수를 증가시입니다.|
|[AfxOleLockControl](#afxolelockcontrol)| 지정된 컨트롤의 클래스 팩터리를 잠급전지. |
|[AfxOleUnlockApp](#afxoleunlockapp)|응용 프로그램의 활성 개체 수에 대한 프레임워크의 수를 감소시입니다.|
|[AfxOleUnlockControl](#afxoleunlockcontrol)| 지정된 컨트롤의 클래스 팩터리 잠금을 해제합니다. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|OLE 시스템 레지스트리에 서버를 등록합니다.|
|[AfxOleSetEditMenu](#afxoleseteditmenu)|*개체 형식에* 대 한 사용자 인터페이스를 구현 합니다 개체 입니다.|

## <a name="afxolecanexitapp"></a><a name="afxolecanexitapp"></a>아엑솔레칸엑시트앱

애플리케이션이 종료될 수 있는지 여부를 나타냅니다.

```
BOOL AFXAPI AfxOleCanExitApp();
```

### <a name="return-value"></a>Return Value

애플리케이션이 종료될 수 있으면 0이 아닌 값이고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

개체에 대해 해결되지 않은 참조가 있으면 애플리케이션이 종료될 수 없습니다. 전역 함수 `AfxOleLockApp` 및 `AfxOleUnlockApp`은 각각 애플리케이션의 개체에 대한 참조 수를 늘리거나 줄입니다. 이 카운터가 0이 아니면 애플리케이션이 종료될 수 없습니다. 카운터가 0이 아니면 사용자가 시스템 메뉴에서 닫기를 선택하거나 파일 메뉴에서 종료를 선택할 때 애플리케이션의 기본 창이 숨겨집니다(삭제되지 않음). 프레임워크는 에서 이 `CFrameWnd::OnClose`함수를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

## <a name="afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a>아fxOleGetMessage필터

응용 프로그램의 현재 메시지 필터를 검색합니다.

```
COleMessageFilter* AFXAPI AfxOleGetMessageFilter();
```

### <a name="return-value"></a>Return Value

현재 메시지 필터에 대한 포인터입니다.

### <a name="remarks"></a>설명

현재 응용 프로그램 개체에 액세스하기 위해 호출하는 `COleMessageFilter` `AfxGetApp` 것처럼 이 함수를 호출하여 현재 파생 개체에 액세스합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]

[!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]

### <a name="requirements"></a>요구 사항

**헤더**: afxwin.h

## <a name="afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a>아fxOleGetUserCtrl

현재 사용자 제어 플래그를 검색합니다.

```
BOOL AFXAPI AfxOleGetUserCtrl();
```

### <a name="return-value"></a>Return Value

사용자가 응용 프로그램을 제어하는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

사용자가 새 문서를 명시적으로 열거나 만들 때 응용 프로그램을 제어할 수 있습니다. OLE 시스템 DLL에서 응용 프로그램을 시작하지 않은 경우(즉, 사용자가 시스템 셸을 사용 하 여 응용 프로그램을 시작 하는 경우) 사용자가 제어 할 수 있습니다.

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

## <a name="afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a>아프올레셋유저Ctrl

에 대한 `AfxOleGetUserCtrl`참조에 설명된 사용자 제어 플래그를 설정하거나 지웁니다.

```cpp
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl);
```

### <a name="parameters"></a>매개 변수

*bUserCtrl*<br/>
사용자 제어 플래그를 설정할지 지 여부를 지정합니다.

### <a name="remarks"></a>설명

프레임워크는 사용자가 문서를 만들거나 로드할 때 이 함수를 호출하지만 컨테이너 응용 프로그램에서 포함된 개체를 로드하는 등의 간접 작업을 통해 문서를 로드하거나 만들 때는 그렇지 않습니다.

응용 프로그램의 다른 작업이 사용자를 응용 프로그램을 제어하도록 해야 하는 경우 이 함수를 호출합니다.

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

## <a name="afxolelockapp"></a><a name="afxolelockapp"></a>아프올레록앱

응용 프로그램의 활성 개체 수에 대한 프레임워크의 전역 수를 증가시입니다.

```cpp
void AFXAPI AfxOleLockApp();
```

### <a name="remarks"></a>설명

프레임워크는 응용 프로그램에서 활성 개체 수를 유지합니다. `AfxOleLockApp` 함수와 `AfxOleUnlockApp` 함수는 각각 이 카운트를 증분 및 감소시요.

사용자가 활성 개체수가 0이 아닌 응용 프로그램인 활성 개체가 있는 응용 프로그램을 닫려고 하면 프레임워크는 응용 프로그램을 완전히 종료하는 대신 사용자의 보기에서 숨깁니다. 이 `AfxOleCanExitApp` 함수는 응용 프로그램이 종료될 수 있는지 여부를 나타냅니다.

클라이언트 `AfxOleLockApp` 응용 프로그램에서 계속 사용하는 동안 해당 개체가 소멸되는 것이 바람직하지 않은 경우 OLE 인터페이스를 노출하는 모든 개체에서 호출합니다. 또한 `AfxOleUnlockApp` 생성자에서 호출하는 모든 개체의 `AfxOleLockApp` 소멸자에서 호출합니다. `COleDocument` 기본적으로(및 파생 된 클래스) 자동으로 잠그고 응용 프로그램의 잠금을 해제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

## <a name="afxoleunlockapp"></a><a name="afxoleunlockapp"></a>아fxOle잠금 앱

응용 프로그램에서 활성 개체의 프레임워크 수를 감소시입니다.

```cpp
void AFXAPI AfxOleUnlockApp();
```

### <a name="remarks"></a>설명

자세한 `AfxOleLockApp` 내용은 를 참조하십시오.

활성 개체 수가 0에 `AfxOleOnReleaseAllObjects` 도달하면 호출됩니다.

### <a name="example"></a>예제

[AfxOleLockApp에](#afxolelockapp)대한 예제를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

## <a name="afxolelockcontrol"></a>AfxOleLockControl

컨트롤과 연결된 동적으로 생성된 데이터가 메모리에 유지되도록 지정된 컨트롤의 클래스 팩터리를 잠급니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
컨트롤의 고유 클래스 ID입니다.

*lpszProgID*<br/>
컨트롤의 고유 프로그램 ID입니다.

### <a name="return-value"></a>Return Value

컨트롤의 클래스 팩터리가 성공적으로 잠겼을 경우 0이 아닌 값이고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이렇게 하면 컨트롤 표시 속도가 상당히 빨라질 수 있습니다. 예를 들어 대화 상자에서 컨트롤을 만들고 이 컨트롤을 `AfxOleLockControl`로 잠글 경우에는 대화 상자를 표시 또는 삭제할 때마다 대화 상자를 만들고 종료할 필요가 없습니다. 사용자가 대화 상자를 반복해서 열고 닫는 경우, 컨트롤을 잠그면 성능이 크게 향상될 수 있습니다. 컨트롤을 제거할 준비가 되면 `AfxOleUnlockControl`을 호출합니다.

### <a name="example"></a>예제

```cpp
// Starts and locks control's (Microsoft Calendar) class factory.
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a>아프올레레지스터서버클래스

이 기능을 사용하면 OLE 시스템 레지스트리에 서버를 등록할 수 있습니다.

```
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,
    LPCTSTR lpszClassName,
    LPCTSTR lpszShortTypeName,
    LPCTSTR lpszLongTypeName,
    OLE_APPTYPE nAppType = OAT_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
서버의 OLE 클래스 ID를 참조합니다.

*lpszClassName*<br/>
서버 개체의 클래스 이름을 포함하는 문자열에 대한 포인터입니다.

*lpsz쇼트타입네임*<br/>
"차트"와 같이 서버 개체 유형의 짧은 이름이 포함된 문자열에 대한 포인터입니다.

*lpszLongTypeName*<br/>
"Microsoft Excel 5.0 차트"와 같이 서버 개체 유형의 긴 이름이 포함된 문자열에 대한 포인터입니다.

*nAppType*<br/>
OLE 응용 프로그램의 형식을 지정하는 OLE_APPTYPE 열거형에서 가져온 값입니다. 가능한 값은 다음과 같습니다.

- OAT_INPLACE_SERVER 서버에는 전체 서버 사용자 인터페이스가 있습니다.

- OAT_SERVER 서버는 포함만 지원합니다.

- OAT_CONTAINER 컨테이너는 포함에 대한 링크를 지원합니다.

- OAT_DISPATCH_OBJECT `IDispatch`가능 객체입니다.

*rglpsz레지스터*<br/>
키에 대한 기존 값이 없는 경우 OLE 시스템 레지스트리에 추가할 키와 값을 나타내는 문자열에 대한 포인터 배열입니다.

*rglpsz오버쓰기*<br/>
레지스트리에 지정된 키에 대한 기존 값이 포함된 경우 OLE 시스템 레지스트리에 추가할 키와 값을 나타내는 문자열에 대한 포인터 배열입니다.

### <a name="return-value"></a>Return Value

서버 클래스가 성공적으로 등록된 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

대부분의 응용 프로그램은 `COleTemplateServer::Register` 응용 프로그램의 문서 유형을 등록하는 데 사용할 수 있습니다. 응용 프로그램의 시스템 레지스트리 형식이 일반적인 패턴에 맞지 않으면 `AfxOleRegisterServerClass` 더 많은 제어를 위해 사용할 수 있습니다.

레지스트리는 키와 값 집합으로 구성됩니다. *rglpszRegister* 및 *rglpszOverwrite* 인수는 각각 KEY와 **NULL** 문자()로 `'\0'`구분된 값으로 구성된 문자열에 대한 포인터의 배열입니다. 이러한 각 문자열에는 대체 가능한 매개 변수를 가질 수 있으며 그 자리는 *문자 시퀀스 %1에서* *%5로*표시됩니다.

기호는 다음과 같이 채워져 있습니다.

|기호|값|
|------------|-----------|
|%1|문자열로 서식이 지정된 클래스 ID|
|%2|클래스 이름|
|%3|실행 파일 경로|
|%4|짧은 유형 이름|
|%5|롱 타입 네임|

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

## <a name="afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a>아프올레세트편집메뉴

*개체 형식에* 대 한 사용자 인터페이스를 구현 합니다 개체 입니다.

```cpp
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,
    CMenu* pMenu,
    UINT iMenuItem,
    UINT nIDVerbMin,
    UINT nIDVerbMax = 0,
    UINT nIDConvert = 0);
```

### <a name="parameters"></a>매개 변수

*p 클라이언트*<br/>
클라이언트 OLE 항목에 대한 포인터입니다.

*p메뉴*<br/>
업데이트할 메뉴 개체에 대한 포인터입니다.

*아이 메뉴항목*<br/>
업데이트할 메뉴 항목의 인덱스입니다.

*니드버비민*<br/>
기본 동사에 해당하는 명령 ID입니다.

*니드버브맥스*<br/>
마지막 동사에 해당하는 명령 ID입니다.

*니디변환*<br/>
변환 메뉴 항목의 ID입니다.

### <a name="remarks"></a>설명

서버가 기본 동사만 인식하면 메뉴 항목은 "동사 *형식 이름* 개체"가 되고 사용자가 명령을 선택할 때 *nIDVerbMin* 명령이 전송됩니다. 서버가 여러 동사를 인식하면 메뉴 항목이 *"형식 이름* 개체"가 되고 사용자가 명령을 선택할 때 모든 동사를 나열하는 하위 메뉴가 나타납니다. 사용자가 하위 메뉴에서 동사를 선택하면 첫 번째 동사를 선택하면 *nIDVerbMin이* 전송되고 두 번째 동사가 선택되면 *nIDVerbMin* + 1이 전송됩니다. 기본 `COleDocument` 구현에서는 이 기능을 자동으로 처리합니다.

클라이언트의 응용 프로그램 리소스 스크립트에 다음 문이 있어야 합니다. RC) 파일:

**#include \<afxolecl.rc>**

### <a name="requirements"></a>요구 사항

**헤더**: afxole.h

## <a name="afxoleunlockcontrol"></a><a name="afxoleunlockcontrol"></a>아프올레잠금 해제 제어

지정된 컨트롤의 클래스 팩터리 잠금을 해제합니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
컨트롤의 고유 클래스 ID입니다.

*lpszProgID*<br/>
컨트롤의 고유 프로그램 ID입니다.

### <a name="return-value"></a>Return Value

컨트롤의 클래스 팩터리가 성공적으로 잠금 해제된 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

컨트롤은 `AfxOleLockControl`로 잠겨 있으므로 컨트롤과 연결된 동적으로 생성된 데이터가 메모리에 남아 있습니다. 이렇게 하면 컨트롤이 표시될 때마다 컨트롤을 만들고 소멸할 필요가 없으므로 컨트롤 표시 속도가 크게 빨라질 수 있습니다. 컨트롤을 제거할 준비가 되면 `AfxOleUnlockControl`을 호출합니다.

### <a name="example"></a>예제

```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="see-also"></a>참조

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
