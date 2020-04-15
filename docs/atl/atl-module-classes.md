---
title: ATL 모듈 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
ms.openlocfilehash: 2b72cac0da06b70a40e01fcc75da52f1678f3f64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317366"
---
# <a name="atl-module-classes"></a>ATL 모듈 클래스

이 항목에서는 ATL 7.0에서 새로 접한 모듈 클래스에 대해 설명합니다.

## <a name="ccommodule-replacement-classes"></a>CComModule 교체 클래스

이전 버전의 ATL이 사용되었습니다. `CComModule` ATL 7.0에서 `CComModule` 기능은 여러 클래스로 대체됩니다.

- [카틀베이스 모듈](../atl/reference/catlbasemodule-class.md) ATL을 사용하는 대부분의 응용 프로그램에 필요한 정보를 포함합니다. 모듈 및 리소스 인스턴스의 HINSTANCE를 포함합니다.

- [카틀컴모듈](../atl/reference/catlcommodule-class.md) ATL의 COM 클래스에 필요한 정보를 포함합니다.

- [카틀윈 모듈](../atl/reference/catlwinmodule-class.md) ATL의 창 클래스에 필요한 정보를 포함합니다.

- [CAtlDebugInterfaces모듈](../atl/reference/catldebuginterfacesmodule-class.md) 인터페이스 디버깅에 대한 지원이 포함되어 있습니다.

- [카틀 모듈](../atl/reference/catlmodule-class.md) 다음 `CAtlModule`-derived 클래스는 특정 응용 프로그램 유형에 필요한 정보를 포함하도록 사용자 지정됩니다. 이러한 클래스의 대부분의 멤버는 재정의할 수 있습니다.

  - [카틀들모듈](../atl/reference/catldllmodulet-class.md) DLL 응용 프로그램에 사용됩니다. 표준 내보내기에 대한 코드를 제공합니다.

  - [카틀렉스 모듈](../atl/reference/catlexemodulet-class.md) EXE 응용 프로그램에 사용됩니다. EXE에 필요한 코드를 제공합니다.

  - [카틀서비스모듈](../atl/reference/catlservicemodulet-class.md) Windows NT 및 Windows 2000 서비스를 만드는 데 대한 지원을 제공합니다.

`CComModule`이전 버전과의 호환성을 위해 계속 사용할 수 있습니다.

## <a name="reasons-for-distributing-ccommodule-functionality"></a>CComModule 기능을 배포하는 이유

다음과 같은 `CComModule` 이유로 여러 개의 새 클래스에 배포되었습니다.

- 기능을 `CComModule` 세분화하여 만듭니다.

   COM, 창, 인터페이스 디버깅 및 응용 프로그램별(DLL 또는 EXE) 기능에 대한 지원은 이제 별도의 클래스에 있습니다.

- 이러한 각 모듈의 전역 인스턴스를 자동으로 선언합니다.

   필요한 모듈 클래스의 전역 인스턴스가 프로젝트에 연결됩니다.

- Init 및 Term 메서드를 호출할 필요가 없습니다.

   Init 및 Term 메서드는 모듈 클래스의 생성자 및 소멸자로 이동했습니다. 더 이상 Init 및 Term을 호출할 필요가 없습니다.

## <a name="see-also"></a>참고 항목

[개념](../atl/active-template-library-atl-concepts.md)<br/>
[클래스 개요](../atl/atl-class-overview.md)
