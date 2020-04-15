---
title: 등록
ms.date: 11/04/2016
helpviewer_keywords:
- servers [MFC], initializing
- initializing servers [MFC]
- OLE, registration
- installing servers [MFC]
- registry [MFC], OLE item database
- registration databases [MFC]
- servers [MFC], installing
- OLE server applications [MFC], registering servers
ms.assetid: 991d5684-72c1-4f9e-a09a-9184ed12bbb9
ms.openlocfilehash: 82411e53620e92eff3484f7d3f7955030fd439ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372836"
---
# <a name="registration"></a>등록

사용자가 응용 프로그램에 OLE 항목을 삽입하려는 경우 OLE는 선택할 개체 유형 목록을 제공합니다. OLE는 모든 서버 응용 프로그램에서 제공하는 정보를 포함하는 시스템 등록 데이터베이스에서 이 목록을 가져옵니다. 서버가 자신을 등록할 때 시스템 등록 데이터베이스(레지스트리)에 넣는 항목은 제공하는 개체의 각 유형, 파일 확장자 및 그 자체에 대한 경로를 설명합니다.

프레임워크와 OLE 시스템 동적 링크 라이브러리(DLL)는 이 레지스트리를 사용하여 시스템에서 사용할 수 있는 OLE 항목 유형을 결정합니다. OLE 시스템 DLL은 또한 이 레지스트리를 사용하여 연결된 개체 또는 포함된 개체가 활성화될 때 서버 응용 프로그램을 시작하는 방법을 결정합니다.

이 문서에서는 각 서버 응용 프로그램이 설치될 때와 실행될 때마다 수행해야 하는 작업을 설명합니다.

시스템 등록 데이터베이스 및 업데이트에 사용되는 .reg 파일의 형식에 대한 자세한 내용은 *OLE 프로그래머의 참조를*참조하십시오.

## <a name="server-installation"></a><a name="_core_server_installation"></a>서버 설치

서버 응용 프로그램을 처음 설치할 때 는 지원하는 모든 유형의 OLE 항목을 등록해야 합니다. 독립 실행형 응용 프로그램으로 실행할 때마다 서버가 시스템 등록 데이터베이스를 업데이트할 수도 있습니다. 이렇게 하면 서버의 실행 파일이 이동되면 등록 데이터베이스가 최신 상태로 유지됩니다.

> [!NOTE]
> 응용 프로그램 마법사에서 생성된 MFC 응용 프로그램은 독립 실행형 응용 프로그램으로 실행될 때 자동으로 등록됩니다.

설치 하는 동안 응용 프로그램을 등록 하려는 경우, RegEdit.exe 프로그램을 사용 하 여. 응용 프로그램에 설치 프로그램을 포함하는 경우 설치 프로그램이 "RegEdit /S *앱 이름*.reg"를 실행하도록 합니다. (/S 플래그는 자동 작업을 나타냅니다. 즉 명령의 성공적인 완료를 보고 하는 대화 상자가 표시 되지 않습니다.) 그렇지 않으면 사용자에게 RegEdit를 수동으로 실행하도록 지시합니다.

> [!NOTE]
> 응용 프로그램 마법사에서 만든 .reg 파일에는 실행 파일에 대한 전체 경로가 포함되지 않습니다. 설치 프로그램은 실행 파일에 대한 전체 경로를 포함하도록 .reg 파일을 수정하거나 설치 디렉터리를 포함하도록 PATH 환경 변수를 수정해야 합니다.

RegEdit는 .reg 텍스트 파일의 내용을 등록 데이터베이스에 병합합니다. 데이터베이스를 확인하거나 복구하려면 레지스트리 편집기를 사용합니다. 필수 OLE 항목을 삭제하지 않도록 주의하십시오.

## <a name="server-initialization"></a><a name="_core_server_initialization"></a>서버 초기화

응용 프로그램 마법사를 사용하여 서버 응용 프로그램을 만들면 마법사가 자동으로 모든 초기화 작업을 완료합니다. 이 섹션에서는 서버 응용 프로그램을 수동으로 작성하는 경우 수행해야 하는 작업을 설명합니다.

컨테이너 응용 프로그램에서 서버 응용 프로그램을 시작하면 OLE 시스템 DLL은 서버의 명령줄에 "/포함" 옵션을 추가합니다. 서버 응용 프로그램의 동작은 컨테이너에 의해 시작되었는지 여부에 따라 다르므로 실행을 시작할 때 응용 프로그램이 가장 먼저 해야 할 일은 명령줄의 "/포함" 또는 "포함" 옵션을 확인하는 것입니다. 이 스위치가 있는 경우 서버가 활성 상태이거나 완전히 열려 있는 것으로 보여 주는 다른 리소스 집합을 로드합니다. 자세한 내용은 [메뉴 및 리소스: 서버 추가 를](../mfc/menus-and-resources-server-additions.md)참조하십시오.

또한 서버 응용 프로그램은 `CWinApp::RunEmbedded` 명령줄을 구문 분석하기 위해 해당 함수를 호출해야 합니다. 영하지 않은 값을 반환하는 경우 독립 실행형 응용 프로그램이 아닌 컨테이너 응용 프로그램에서 실행되었기 때문에 응용 프로그램에 해당 창이 표시되지 않아야 합니다. 이 함수는 시스템 등록 데이터베이스에서 서버의 항목을 `RegisterAll` 업데이트하고 인스턴스 등록을 수행하여 구성원 함수를 호출합니다.

서버 응용 프로그램이 시작될 때 인스턴스 등록을 수행할 수 있는지 확인해야 합니다. 인스턴스 등록은 OLE 시스템 DLL에 서버가 활성 상태이며 컨테이너에서 요청을 받을 준비가 되었다는 것을 알립니다. 등록 데이터베이스에 항목을 추가하지 않습니다. 에 의해 정의된 멤버 함수를 호출하여 서버의 인스턴스 등록을 `ConnectTemplate` 수행합니다. `COleTemplateServer` 이렇게 하면 `CDocTemplate` 개체가 `COleTemplateServer` 개체에 연결됩니다.

이 `ConnectTemplate` 함수는 서버의 *CLSID,* `CDocTemplate` 개체에 대한 포인터 및 서버가 여러 인스턴스를 지원하는지 여부를 나타내는 플래그의 세 가지 매개 변수를 사용합니다. 미니 서버는 여러 인스턴스를 지원할 수 있어야 합니다. 따라서 미니 서버를 시작할 때 이 플래그에 대해 **TRUE를** 전달합니다.

미니 서버를 작성하는 경우 정의에 따라 항상 컨테이너에서 시작됩니다. 명령줄을 구문 분석하여 "/포함" 옵션을 확인해야 합니다. 명령줄에 이 옵션이 없으면 사용자가 미니 서버를 독립 실행형 응용 프로그램으로 실행하려고 시도했습니다. 이 경우 시스템 등록 데이터베이스에 서버를 등록한 다음 컨테이너 응용 프로그램에서 미니 서버를 시작하도록 사용자에게 알리는 메시지 상자를 표시합니다.

## <a name="see-also"></a>참고 항목

[OLE](../mfc/ole-in-mfc.md)<br/>
[서버](../mfc/servers.md)<br/>
[CWinApp::실행 자동화](../mfc/reference/cwinapp-class.md#runautomated)<br/>
[CWinApp:::실행 임베디드](../mfc/reference/cwinapp-class.md#runembedded)<br/>
[COle템플릿서버 클래스](../mfc/reference/coletemplateserver-class.md)
