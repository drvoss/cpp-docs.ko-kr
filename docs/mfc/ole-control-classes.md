---
title: OLE 컨트롤 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
ms.openlocfilehash: 47c28520d592c4bd49ab6cb40edbb2f5ddf59846
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447641"
---
# <a name="ole-control-classes"></a>OLE 컨트롤 클래스

이러한 클래스는 OLE 컨트롤을 작성할 때 사용 하는 기본 클래스입니다. OLE 컨트롤 모듈의 `COleControlModule` 클래스는 응용 프로그램의 [CWinApp](../mfc/reference/cwinapp-class.md) 클래스와 같습니다. 각 모듈은 하나 이상의 OLE 컨트롤을 구현 합니다. 이러한 컨트롤은 `COleControl` 개체로 표현 됩니다. 이러한 컨트롤은 `CConnectionPoint` 개체를 사용 하 여 해당 컨테이너와 통신 합니다.

`CPictureHolder` 및 `CFontHolder` 클래스는 그림 및 글꼴에 대 한 COM 인터페이스를 캡슐화 하는 반면 `COlePropertyPage` 및 `CPropExchange` 클래스는 컨트롤에 대 한 속성 페이지와 속성 지 속성을 구현 하는 데 도움이 됩니다.

[COleControlModule](../mfc/reference/colecontrolmodule-class.md)<br/>
OLE 컨트롤 모듈의 `CWinApp` 클래스를 바꿉니다. `COleControlModule` 클래스에서 파생 하 여 OLE 컨트롤 모듈 개체를 개발 합니다. OLE 컨트롤의 모듈을 초기화 하는 데 사용할 수 있는 멤버 함수를 제공 합니다.

[COleControl](../mfc/reference/colecontrol-class.md)<br/>
`COleControl` 클래스에서 파생 하 여 OLE 컨트롤을 개발 합니다. `CWnd`에서 파생 되는이 클래스는 Windows 창 개체의 모든 기능과 이벤트 실행과 같은 추가 OLE 관련 기능 및 메서드 및 속성을 지 원하는 기능을 상속 합니다.

[CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)<br/>
`CConnectionPoint` 클래스는 연결 지점 이라고 하는 다른 OLE 개체와 통신 하는 데 사용 되는 특별 한 형식의 인터페이스를 정의 합니다. 연결 지점은 이벤트 발생 및 변경 알림과 같은 다른 개체에 대 한 작업을 시작할 수 있는 송신 인터페이스를 구현 합니다.

[CPictureHolder](../mfc/reference/cpictureholder-class.md)<br/>
Windows 그림 개체와 `IPicture` COM 인터페이스의 기능을 캡슐화 합니다. OLE 컨트롤의 사용자 지정 그림 속성을 구현 하는 데 사용 됩니다.

[CFontHolder](../mfc/reference/cfontholder-class.md)<br/>
Windows 글꼴 개체와 `IFont` COM 인터페이스의 기능을 캡슐화 합니다. OLE 컨트롤의 스톡 글꼴 속성을 구현 하는 데 사용 됩니다.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
대화 상자와 유사한 그래픽 인터페이스의 OLE 컨트롤 속성을 표시 합니다.

[CPropExchange](../mfc/reference/cpropexchange-class.md)<br/>
OLE 컨트롤에 대 한 속성 지 속성 구현을 지원 합니다. 대화 상자에 대 한 [CDataExchange](../mfc/reference/cdataexchange-class.md) 와 유사 합니다.

[CMonikerFile](../mfc/reference/cmonikerfile-class.md)<br/>
모니커 또는 모니커에 만들 수 있는 문자열 표현을 사용 하 여 모니커가 이름인 스트림에 동기적으로 바인딩합니다.

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)<br/>
`CMonikerFile`와 유사 하 게 작동 합니다. 그러나 모니커는 모니커가 이름인 스트림에 비동기적으로 바인딩합니다.

[CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)<br/>
비동기적으로 로드할 수 있는 OLE 컨트롤 속성을 구현합니다.

[CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)<br/>
비동기적으로 전송되고 메모리 파일에 캐싱되는 OLE 컨트롤 속성을 구현합니다.

[COleCmdUI](../mfc/reference/colecmdui-class.md)<br/>
활성 문서가 컨테이너의 사용자 인터페이스에서 시작 되는 명령 (예: FileNew, Open, Print 등)을 받아 컨테이너가 활성 문서의 사용자 인터페이스에서 발생 하는 명령을 받을 수 있도록 허용 합니다.

[COleSafeArray](../mfc/reference/colesafearray-class.md)<br/>
임의의 형식 및 차원 배열에서 작동 합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../mfc/class-library-overview.md)
