---
title: 입력-출력 처리에 대한 권장 사항
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
ms.openlocfilehash: c365120a385c440f09f0ee4c0a2fc52afb55834f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371731"
---
# <a name="recommendations-for-handling-inputoutput"></a>입력/출력 처리에 대한 권장 사항

파일 기반 I/O를 사용할지 여부는 다음 의사 결정 트리의 질문에 응답하는 방법에 따라 달라집니다.

**응용 프로그램의 기본 데이터가 디스크 파일에 상주합니까?**

- 예. 기본 데이터는 디스크 파일에 있습니다.

   **응용 프로그램이 파일 열기에서 전체 파일을 메모리로 읽고 파일 저장의 전체 파일을 디스크에 다시 작성합니까?**

  - 예: 기본 MFC 문서 케이스입니다. 직렬화를 사용합니다. `CDocument`

  - 아니오: 일반적으로 파일의 트랜잭션 기반 업데이트의 경우입니다. 트랜잭션별로 파일을 업데이트하며 직렬화가 필요하지 `CDocument` 않습니다.

- 아니요, 기본 데이터는 디스크 파일에 상주하지 않습니다.

   **데이터가 ODBC 데이터 원본에 상주합니까?**

  - 예. 데이터는 ODBC 데이터 원본에 있습니다.

      MFC의 데이터베이스 지원을 사용합니다. 이 경우 표준 MFC 구현에는 `CDatabase` [MFC: 문서 및 뷰가 있는 데이터베이스 클래스 사용문서에서](../data/mfc-using-database-classes-with-documents-and-views.md)설명한 대로 개체가 포함됩니다. 응용 프로그램은 응용 프로그램 마법사 "데이터베이스 보기 및 파일 지원" 옵션의 목적인 보조 파일을 읽고 쓸 수도 있습니다. 이 경우 보조 파일에 대해 직렬화를 사용합니다.

  - 아니요, 데이터는 ODBC 데이터 원본에 상주하지 않습니다.

      이 경우의 예: 데이터는 ODBC가 아닌 DBMS에 있습니다. 데이터는 OLE 또는 DDE와 같은 다른 메커니즘을 통해 읽습니다.

      이러한 경우 직렬화를 사용하지 않으며 응용 프로그램에 는 열기 및 저장 메뉴 항목이 없습니다. MFC ODBC 응용 `CDocument` 프로그램이 문서를 사용하여 개체를 저장하는 `CRecordset` 것처럼 여전히 홈 베이스로 사용할 수 있습니다. 그러나 프레임워크의 기본 파일 열기/저장 문서 직렬화를 사용하지는 않습니다.

파일 메뉴에서 열기, 저장 및 저장 명령을 지원하기 위해 프레임워크는 문서 직렬화를 제공합니다. 직렬화는 클래스에서 `CObject`파생된 개체를 포함하여 데이터를 영구 저장소, 일반적으로 디스크 파일로 읽고 씁니다. 직렬화는 사용하기 쉽고 많은 요구 사항을 제공하지만 많은 데이터 액세스 응용 프로그램에서는 부적절할 수 있습니다. 데이터 액세스 응용 프로그램은 일반적으로 트랜잭션별로 데이터를 업데이트합니다. 한 번에 전체 데이터 파일을 읽고 쓰는 대신 트랜잭션의 영향을 받는 레코드를 업데이트합니다.

직렬화에 대한 자세한 내용은 [직렬화를](../mfc/serialization-in-mfc.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[Serialization: Serialization과 데이터베이스 입출력 비교](../mfc/serialization-serialization-vs-database-input-output.md)
