---
title: '메뉴 및 리소스: 서버 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE visual editing servers [MFC]
- accelerator tables [MFC], server applications
- visual editing [MFC], application menus and resources
- server applications [MFC], accelerator table
- string tables [MFC], visual editing applications
- servers [MFC], menu additions
- resources [MFC], server applications
- OLE server applications [MFC], menus and resources
- string editing [MFC], visual editing applications
- IDP_OLE_INIT_FAILED macro [MFC]
- server applications [MFC], OLE menus and resources
- OLE initialization failure [MFC]
ms.assetid: 56ce9e8d-8f41-4db8-8dee-e8b0702d057c
ms.openlocfilehash: 8366cd8b0376766b7914c94a24cef6598761a805
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375983"
---
# <a name="menus-and-resources-server-additions"></a>메뉴 및 리소스: 서버 추가

이 문서에서는 시각적 편집 서버(구성 요소) 응용 프로그램의 메뉴 및 기타 리소스에 대해 변경해야 하는 변경 사항에 대해 설명합니다. 서버 응용 프로그램은 독립 실행형, 임베디드 또는 제자리에 있는 세 가지 모드 중 하나에서 시작할 수 있으므로 메뉴 구조 및 기타 리소스에 많은 추가가 필요합니다. 메뉴 및 [리소스(OLE)](../mfc/menus-and-resources-ole.md) 문서에 설명된 대로 최대 4개의 메뉴 집합이 있습니다. 네 가지 모두 MDI 전체 서버 응용 프로그램에 사용되며 미니 서버에는 3개만 사용됩니다. 응용 프로그램 마법사는 원하는 서버 유형에 필요한 메뉴 레이아웃을 만듭니다. 일부 사용자 지정이 필요할 수 있습니다.

응용 프로그램 마법사를 사용하지 않는 경우 HIERSVR을 살펴볼 수 있습니다. RC, MFC 샘플 응용 프로그램 [HIERSVR에](../overview/visual-cpp-samples.md)대한 리소스 스크립트는 이러한 변경 내용이 구현되는 방법을 볼 수 있습니다.

이 문서에서 다루는 주제는 다음과 같습니다.

- [서버 메뉴 추가](#_core_server_menu_additions)

- [가속기 테이블 추가](#_core_server_application_accelerator_table_additions)

- [문자열 테이블 추가](../mfc/menus-and-resources-container-additions.md)

- [미니 서버 추가](#_core_mini.2d.server_additions)

## <a name="server-menu-additions"></a><a name="_core_server_menu_additions"></a>서버 메뉴 추가

서버(구성 요소) 응용 프로그램에는 OLE 시각적 편집을 지원하기 위해 메뉴 리소스가 추가되어야 합니다. 응용 프로그램이 독립 실행형 모드에서 실행될 때 사용되는 메뉴는 변경할 필요가 없지만 응용 프로그램을 빌드하기 전에 두 개의 새 메뉴 리소스를 추가해야 합니다. 두 메뉴 리소스는 전체 및 미니 서버 응용 프로그램에서 사용됩니다.

- 내부 활성화를 지원하려면 독립 실행형 모드에서 실행할 때 사용되는 메뉴 리소스와 매우 유사한 메뉴 리소스를 만들어야 합니다. 이 메뉴의 차이점은 파일 및 창 항목(및 데이터가 아닌 응용 프로그램을 처리하는 다른 메뉴 항목)이 누락되었다는 것입니다. 컨테이너 응용 프로그램은 이러한 메뉴 항목을 제공합니다. 이 메뉴 병합 기술에 대한 자세한 정보 및 예제는 메뉴 [및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)을 참조하십시오.

- 완전히 열린 활성화를 지원하려면 독립 실행형 모드에서 실행할 때 사용되는 메뉴 리소스와 거의 동일한 메뉴 리소스를 만들어야 합니다. 이 메뉴 리소스의 유일한 수정 사항은 서버가 복합 문서에 포함된 항목에서 작동한다는 사실을 반영하기 위해 일부 항목이 다시 작성된다는 것입니다.

이 문서에 나열된 변경 내용 외에도 리소스 파일에 AFXOLESV를 포함해야 합니다. Microsoft 재단 클래스 라이브러리 구현에 필요한 RC입니다. 이 파일은 MFC\하위 디렉터리에 있습니다.

## <a name="server-application-accelerator-table-additions"></a><a name="_core_server_application_accelerator_table_additions"></a>서버 응용 프로그램 가속기 테이블 추가

두 개의 새 가속기 테이블 리소스를 서버 응용 프로그램에 추가해야 합니다. 앞서 설명한 새 메뉴 리소스에 직접 해당합니다. 첫 번째 가속기 테이블은 서버 응용 프로그램이 활성화될 때 사용됩니다. 파일 및 창 메뉴에 연결된 항목을 제외한 뷰의 가속기 테이블의 모든 항목으로 구성됩니다.

두 번째 테이블은 뷰의 가속기 테이블의 거의 정확한 복사본입니다. [서버 메뉴 추가에](#_core_server_menu_additions)언급 된 완전히 열려있는 메뉴에서 변경 된 모든 차이점 병렬 변경 .

이러한 가속기 테이블 변경의 예를 들어 IDR_HIERSVRTYPE_SRVR_IP 및 IDR_HIERSVRTYPE_SRVR_EMB 가속기 테이블을 HIERSVR의 IDR_MAINFRAME 비교합니다. MFC OLE 샘플 [HIERSVR에](../overview/visual-cpp-samples.md)포함 된 RC 파일 . 파일 및 창 가속기가 있는 테이블에서 누락되었으며 정확한 복사본이 포함된 테이블에 있습니다.

## <a name="string-table-additions-for-server-applications"></a><a name="_core_string_table_additions_for_server_applications"></a>서버 응용 프로그램에 대한 문자열 테이블 추가

OLE 초기화가 실패함을 나타내는 문자열인 서버 응용 프로그램에서 는 하나의 문자열 테이블 추가만 필요합니다. 예를 들어 응용 프로그램 마법사에서 생성하는 문자열 테이블 항목은 다음과 같습니다.

|ID|String|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE 초기화가 실패했습니다. OLE 라이브러리가 올바른 버전인지 확인합니다.|

## <a name="miniserver-additions"></a><a name="_core_mini.2d.server_additions"></a>미니 서버 추가

전체 서버의 경우 위에 나열된 것과 동일한 추가 가 미니 서버에 적용됩니다. 미니 서버는 독립 실행형 모드에서 실행할 수 없으므로 주 메뉴는 훨씬 작습니다. 응용 프로그램 마법사에서 만든 기본 메뉴에는 종료 및 정보를 포함하는 항목 메뉴만 있습니다. 미니 서버용 임베디드 및 내/소초 메뉴 및 액셀러레이터는 전체 서버의 메뉴와 동일합니다.

## <a name="see-also"></a>참고 항목

[메뉴 및 리소스(OLE)](../mfc/menus-and-resources-ole.md)<br/>
[메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)
