---
title: 'CAtlService모듈: :시작 기능'
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: 50054bbb34bcc31a1d11dd8bfab797f98e4e82f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317286"
---
# <a name="catlservicemoduletstart-function"></a>CAtlService모듈: :시작 기능

서비스가 실행되면 `_tWinMain` 호출됩니다. `CAtlServiceModuleT::WinMain` `CAtlServiceModuleT::Start`

`CAtlServiceModuleT::Start`각 서비스를 시작 `SERVICE_TABLE_ENTRY` 함수에 매핑하는 구조의 배열을 설정합니다. 이 배열은 Win32 API 함수인 [StartServiceCtrlDispatch.로](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw)전달됩니다. 이론적으로 하나의 EXE는 여러 서비스를 처리할 수 `SERVICE_TABLE_ENTRY` 있으며 배열에는 여러 구조가 있을 수 있습니다. 그러나 현재 ATL 에서 생성된 서비스는 EXE당 하나의 서비스만 지원합니다. 따라서 배열에는 서비스 이름과 `_ServiceMain` 시작 함수가 포함된 단일 항목이 있습니다. `_ServiceMain`는 비정적 멤버 `CAtlServiceModuleT` 함수를 호출하는 정적 `ServiceMain`멤버 함수입니다.

> [!NOTE]
> `StartServiceCtrlDispatcher` SCM(서비스 제어 관리자)에 연결하지 못하면 프로그램이 서비스로 실행되지 않을 수 있습니다. 이 경우 프로그램이 로컬 `CAtlServiceModuleT::Run` 서버로 실행될 수 있도록 프로그램이 직접 호출됩니다. 로컬 서버로 프로그램을 실행하는 것에 대한 자세한 내용은 [디버깅 팁](../atl/debugging-tips.md)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[Services](../atl/atl-services.md)<br/>
[CAtlService모듈: :시작](../atl/reference/catlservicemodulet-class.md#start)
