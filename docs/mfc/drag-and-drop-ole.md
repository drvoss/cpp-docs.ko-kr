---
title: OLE 끌어서 놓기
description: Microsoft Foundation Classes (MFC) OLE 끌어서 놓기, 놓기 소스 구현 방법, 놓기 대상 및 끌어서 놓기를 사용자 지정 하는 방법에 대 한 개요입니다.
ms.date: 02/09/2020
helpviewer_keywords:
- OLE server applications [MFC], drag and drop
- drag and drop [MFC]
- OLE applications [MFC], drag and drop
- File Manager drag and drop support [MFC]
- drag and drop [MFC], about OLE drag and drop
- OLE drag and drop [MFC]
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
ms.openlocfilehash: 23680765377d325bdc1f8878daf4d4fc553a1304
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623184"
---
# <a name="ole-drag-and-drop"></a>OLE 끌어서 놓기

OLE의 끌어서 놓기 기능은 주로 데이터를 복사 하 여 붙여 넣는 데 사용할 수 있는 바로 가기입니다. 클립보드를 사용 하 여 데이터를 복사 하거나 붙여 넣는 경우 여러 단계가 필요 합니다. 데이터를 선택 하 고 **편집** 메뉴에서 **잘라내기** 또는 **복사** 를 선택 합니다. 그런 다음 대상 앱 또는 창으로 이동 하 고 대상 위치에 커서를 놓습니다. 마지막으로 **Edit**  >  메뉴에서**붙여넣기** 편집을 선택 합니다.

OLE 끌어서 놓기 기능은 파일 관리자 끌어서 놓기 메커니즘과는 다릅니다. 파일 관리자는 파일 이름만 처리할 수 있으며 파일 이름을 응용 프로그램에 전달 하도록 특별히 설계 되었습니다. OLE에서 끌어서 놓기는 훨씬 더 일반적입니다. 클립보드에 저장할 수 있는 모든 데이터를 끌어서 놓을 수 있습니다.

OLE 끌어서 놓기를 사용 하는 경우 프로세스에서 두 단계를 제거 합니다. 원본 창 ("drop source")에서 데이터를 선택한 다음 대상 ("놓기 대상")으로 끌어 옵니다. 마우스 단추를 놓으면 해당 파일을 삭제 합니다. 작업은 메뉴에 대 한 필요성을 제거 하며 복사/붙여넣기 시퀀스 보다 빠릅니다. 요구 사항은 하나 뿐입니다. 즉, 놓기 소스와 놓기 대상은 모두 열려 있어야 하 고 최소한 화면에 부분적으로 표시 되어야 합니다.

OLE 끌어서 놓기를 사용 하 여 한 위치에서 다른 위치로 데이터를 쉽게 전송할 수 있습니다. 문서 내에서 다른 문서 사이 또는 응용 프로그램 간에 데이터를 쉽게 전송할 수 있습니다. 컨테이너 또는 서버 응용 프로그램에서 구현 될 수 있습니다. 모든 응용 프로그램은 놓기 소스, 놓기 대상 또는 둘 다 일 수 있습니다. 응용 프로그램에서 drop source 및 drop target 지원을 둘 다 구현 하는 경우 자식 창이 나 한 창 내에서 끌어서 놓을 수 있습니다. 이 기능을 사용 하면 응용 프로그램을 훨씬 쉽게 사용할 수 있습니다.

[데이터 개체 및 데이터 소스 (OLE)](data-objects-and-data-sources-ole.md) 문서에서는 응용 프로그램에서 데이터 전송을 구현 하는 방법을 설명 합니다. MFC OLE 샘플 [OCLIENT](../overview/visual-cpp-samples.md) 및 [HIERSVR](../overview/visual-cpp-samples.md)를 검토 하는 것도 유용 합니다.

## <a name="implement-a-drop-source"></a><a name="implement-a-drop-source"></a>놓기 소스 구현

응용 프로그램에서 끌어서 놓기 작업에 데이터를 제공 하도록 하려면 drop source를 구현 합니다. Drop source의 기본 구현은 비교적 간단 합니다. 첫 번째 단계는 끌기 작업을 시작할 이벤트를 결정 하는 것입니다. 권장 사용자 인터페이스 지침은 일부 선택 된 데이터 내의 지점에서 **WM_LBUTTONDOWN** 이벤트가 발생 하는 경우와 같이 끌기 작업의 시작을 정의 합니다. MFC OLE 샘플 [OCLIENT](../overview/visual-cpp-samples.md) 및 [HIERSVR](../overview/visual-cpp-samples.md) 는 이러한 지침을 따릅니다.

응용 프로그램이 컨테이너이 고 선택한 데이터가 연결 된 또는 형식의 포함 된 개체인 경우 `COleClientItem` 해당 `DoDragDrop` 멤버 함수를 호출 합니다. 그렇지 않으면 개체를 생성 하 고, `COleDataSource` 선택 항목을 사용 하 여 초기화 하 고, 데이터 소스 개체의 `DoDragDrop` 멤버 함수를 호출 합니다. 응용 프로그램이 서버 이면를 사용 `COleServerItem::DoDragDrop` 합니다. 표준 끌어서 놓기 동작을 사용자 지정 하는 방법에 대 한 자세한 내용은 [끌어서 놓기 사용자 지정](#customize-drag-and-drop)섹션을 참조 하세요.

`DoDragDrop`가 **DROPEFFECT_MOVE**을 반환 하는 경우 소스 문서에서 원본 데이터를 즉시 삭제 합니다. 의 다른 반환 값 `DoDragDrop` 은 놓기 소스에 영향을 주지 않습니다.

자세한 내용은 [ole 데이터 개체 및 데이터 원본: 생성 및 소멸](data-objects-and-data-sources-creation-and-destruction.md) 및 [ole 데이터 개체 및 데이터 소스: 조작](data-objects-and-data-sources-manipulation.md) 을 참조 하세요.\.

## <a name="implement-a-drop-target"></a><a name="implement-a-drop-target"></a>놓기 대상 구현

놓기 소스 보다 놓기 대상을 구현 하는 데 약간의 작업이 필요 하지만 상대적으로 간단 합니다.

### <a name="to-implement-an-ole-drop-target"></a>OLE 놓기 대상을 구현 하려면

1. 아직 없는 경우 `AfxOleInit` 응용 프로그램의 멤버 함수에서에 대 한 호출을 추가 `InitInstance` 합니다. OLE 라이브러리를 초기화 하려면이 호출이 필요 합니다.

1. 놓기 대상으로 지정할 응용 프로그램의 각 뷰에 멤버 변수를 추가 합니다. 이 멤버 변수는 형식 `COleDropTarget` 이거나 여기에서 파생 된 클래스 여야 합니다.

1. **WM_CREATE** 메시지를 처리 하는 뷰 클래스의 함수에서 (일반적으로 `OnCreate` ) 새 멤버 변수의 멤버 함수를 호출 합니다 `Register` . `Revoke`뷰가 제거 될 때 자동으로 호출 됩니다.

1. 다음 함수를 재정의 합니다. 응용 프로그램 전체에서 동일한 동작을 원하는 경우 뷰 클래스에서 이러한 함수를 재정의 합니다. 격리 된 사례의 동작을 수정 하거나 비 windows에서 놓기를 사용 하도록 설정 하려는 경우 `CView` 파생 클래스에서 이러한 함수를 재정의 `COleDropTarget` 합니다.

   | 재정의 | 허용 하려면 |
   | -------- | -------- |
   | `OnDragEnter` | 창에서 발생 하는 Drop 작업입니다. 커서를 창으로 처음 가져가면 호출 됩니다. |
   | `OnDragLeave` | 끌기 작업이 지정 된 창을 벗어나면 특수 한 동작입니다. |
   | `OnDragOver` | 창에서 발생 하는 Drop 작업입니다. 커서를 창에서 끌 때 호출 됩니다. |
   | `OnDrop` | 지정 된 창에 삭제 되는 데이터 처리 |
   | `OnScrollBy` | 대상 창에서 스크롤이 필요한 경우의 특별 한 동작입니다. |

MAINVIEW를 참조 하세요. 이러한 함수를 함께 사용 하는 방법에 대 한 예제는 MFC OLE 샘플 [OCLIENT](../overview/visual-cpp-samples.md) 의 일부인 CPP 파일입니다.

자세한 내용은 [ole 데이터 개체 및 데이터 원본: 생성 및 소멸](data-objects-and-data-sources-creation-and-destruction.md) 및 [ole 데이터 개체 및 데이터 소스: 조작](data-objects-and-data-sources-manipulation.md) 을 참조 하세요.\.

## <a name="customize-drag-and-drop"></a><a name="customize-drag-and-drop"></a>끌어서 놓기 사용자 지정

대부분의 애플리케이션에서는 끌어 놓기 기능의 기본 구현으로도 충분합니다. 그러나 일부 응용 프로그램에서는이 표준 동작을 변경 해야 할 수도 있습니다. 이 섹션에서는 이러한 기본값을 변경 하는 데 필요한 단계에 대해 설명 합니다. 이 방법을 사용 하 여 복합 문서를 지원 하지 않는 응용 프로그램을 놓기 원본으로 만들 수 있습니다.

표준 OLE 끌어서 놓기 동작을 사용자 지정 하거나 비 OLE 응용 프로그램이 있는 경우 데이터를 포함 하는 개체를 만들어야 합니다 `COleDataSource` . 사용자가 끌어 놓기 작업을 시작하면 코드가 끌어 놓기 작업을 지원하는 다른 클래스 대신 이 개체에서 `DoDragDrop` 함수를 호출해야 합니다.

필요에 따라 `COleDropSource` 개체를 만들어서 변경하려는 동작 유형에 따라 놓기를 제어하고 일부 함수를 재정의할 수 있습니다. 그런 다음 이러한 함수의 기본 동작을 변경하도록 이 놓기 소스 개체가 `COleDataSource::DoDragDrop`으로 전달됩니다. 이러한 여러 옵션을 통해 애플리케이션에서 끌어 놓기 작업을 지원하는 데 유연성을 크게 향상시킬 수 있습니다. 데이터 원본에 대 한 자세한 내용은 [데이터 개체 및 데이터 원본 (OLE)](data-objects-and-data-sources-ole.md)문서를 참조 하세요.

다음 함수를 재정의해서 끌어 놓기 작업을 사용자 지정할 수 있습니다.

| 재정의 | 사용자 지정 |
| -------- | ------------ |
| `OnBeginDrag` | 를 호출한 후에 끌기 작업을 시작 하는 방법 `DoDragDrop` 입니다. |
| `GiveFeedback` | 여러 놓기 결과에 대한 시각적 피드백(예: 커서 모양). |
| `QueryContinueDrag` | 끌어 놓기 작업의 종료. 이 함수를 사용하면 놓기 작업 중 보조키 상태를 확인할 수 있습니다. |

## <a name="see-also"></a>참고 항목

[OLE](ole-in-mfc.md)\
[OLE 데이터 개체 및 데이터 원본](data-objects-and-data-sources-ole.md)\
[OLE 데이터 개체 및 데이터 원본: 생성 및 소멸](data-objects-and-data-sources-creation-and-destruction.md)\
[OLE 데이터 개체 및 데이터 소스: 조작](data-objects-and-data-sources-manipulation.md)\
[COleClientItem::D oDragDrop](reference/coleclientitem-class.md#dodragdrop)\
[COleDataSource 클래스](reference/coledatasource-class.md)\
[COleDataSource::D oDragDrop](reference/coledatasource-class.md#dodragdrop)\
[COleDropSource 클래스](reference/coledropsource-class.md)\
[COleDropTarget 클래스](reference/coledroptarget-class.md)\
[CView:: System.windows.uielement.ondragleave](reference/cview-class.md#ondragleave)
