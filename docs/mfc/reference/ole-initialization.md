---
title: OLE 초기화
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: fefb7eda242ffe15e85cd9f0e16e947a067044a0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751216"
---
# <a name="ole-initialization"></a>OLE 초기화

응용 프로그램이 OLE 시스템 서비스를 사용하려면 먼저 OLE 시스템 DLL을 초기화하고 DLL이 올바른 버전인지 확인해야 합니다. 이 `AfxOleInit` 함수는 OLE 시스템 DLL을 초기화합니다.

### <a name="ole-initialization"></a>OLE 초기화

|||
|-|-|
|[AfxOleInit](#afxoleinit)|OLE 라이브러리를 초기화합니다.|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|응용 프로그램 개체의 `InitInstance` 함수에서 이 함수를 호출하여 OLE 컨트롤의 포함을 지원합니다.|

## <a name="afxenablecontrolcontainer"></a><a name="afxenablecontrolcontainer"></a>AfxEnableControl컨테이너

응용 프로그램 개체의 `InitInstance` 함수에서 이 함수를 호출하여 OLE 컨트롤의 포함을 지원합니다.

### <a name="syntax"></a>구문

```cpp
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>설명

OLE 컨트롤(현재 ActiveX 컨트롤이라고 함)에 대한 자세한 내용은 [ActiveX 컨트롤 항목을](../mfc-activex-controls.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="afxoleinit"></a><a name="afxoleinit"></a>아프올레니트

응용 프로그램에 대한 OLE 지원을 초기화합니다.

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; OLE 시스템 DLL의 잘못된 버전이 설치되어 초기화가 실패하면 0입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 MFC 응용 프로그램에 대한 OLE 지원을 초기화합니다. 이 함수를 호출하면 다음 작업이 발생합니다.

- 호출 응용 프로그램의 현재 아파트에서 COM 라이브러리를 초기화합니다. 자세한 내용은 [Ole초기화를](/windows/win32/api/ole2/nf-ole2-oleinitialize)참조하십시오.

- [IMessageFilter](/windows/win32/api/objidl/nn-objidl-imessagefilter) 인터페이스를 구현 하는 메시지 필터 개체를 만듭니다. 이 메시지 필터는 [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)에 대한 호출로 액세스할 수 있습니다.

> [!NOTE]
> **AfxOleInit이** MFC DLL에서 호출되면 호출이 실패합니다. 함수는 DLL에서 호출된 경우 OLE 시스템이 호출 응용 프로그램에서 이전에 초기화되었다고 가정하기 때문에 오류가 발생합니다.

> [!NOTE]
> MFC 응용 프로그램은 단일 스레드 아파트(STA)로 초기화되어야 합니다. 재정의에서 [CoInitializeEx를](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) 호출하는 경우 COINIT_MULTITHREADED 대신 COINIT_APARTMENTTHREADED 지정합니다. `InitInstance`

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="see-also"></a>참조

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
