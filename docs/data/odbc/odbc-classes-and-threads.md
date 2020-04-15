---
title: ODBC 클래스와 스레드
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: aaf54a3a1d616cde5742dad45955bd415f612d60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368697"
---
# <a name="odbc-classes-and-threads"></a>ODBC 클래스와 스레드

MFC 4.2부터 MFC ODBC 클래스에 대한 다중 스레딩 지원이 있습니다. 그러나 MFC는 DAO 클래스에 대한 다중 스레딩 지원을 제공하지 않습니다.

ODBC 클래스에 대한 다중 스레딩 지원에는 몇 가지 제한 사항이 있습니다. 이러한 클래스는 ODBC API를 래핑하기 때문에 빌드되는 구성 요소의 다중 스레딩 지원으로 제한됩니다. 예를 들어 많은 ODBC 드라이버는 스레드에서 안전하지 않습니다. 따라서 MFC ODBC 클래스는 이러한 드라이버 중 하나와 함께 사용하는 경우 스레드에서 안전하지 않습니다. 특정 드라이버가 스레드에서 안전한지 확인해야 합니다.

다중 스레드 응용 프로그램을 만들 때는 여러 스레드를 사용하여 동일한 개체를 조작할 때 매우 주의해야 합니다. 예를 들어 두 `CRecordset` 스레드에서 동일한 개체를 사용하면 데이터를 검색할 때 문제가 발생할 수 있습니다. 한 스레드의 가져오기 작업은 다른 스레드에서 가져온 데이터를 덮어쓸 수 있습니다. 별도의 스레드에서 MFC ODBC 클래스를 사용하는 것이 더 `CDatabase` 일반적인 방법은 스레드 간에 열린 개체를 공유하여 `CRecordset` 각 스레드의 별도 개체와 동일한 ODBC 연결을 사용하는 것입니다. 미개봉된 `CDatabase` 객체를 다른 스레드의 `CRecordset` 개체에 전달해서는 안 됩니다.

> [!NOTE]
> 동일한 개체를 조작하는 스레드가 여러 개 있어야 하는 경우 중요한 섹션과 같은 적절한 동기화 메커니즘을 구현해야 합니다. 와 같은 `Open`특정 작업은 보호되지 않습니다. 이러한 작업은 별도의 스레드에서 동시에 호출되지 않도록 해야 합니다.

다중 스레드 응용 프로그램 만들기에 대한 자세한 내용은 [다중 스레딩 항목을](../../parallel/multithreading-support-for-older-code-visual-cpp.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[개방형 데이터베이스 연결(ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[데이터 액세스 프로그래밍(MFC/ATL)](../../data/data-access-programming-mfc-atl.md)
