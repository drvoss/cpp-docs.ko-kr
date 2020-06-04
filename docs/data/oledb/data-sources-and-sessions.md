---
title: 데이터 소스 및 세션
ms.date: 11/19/2018
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
ms.openlocfilehash: 0514f6a9285936c85608f08774c1d377fd72d6ab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211057"
---
# <a name="data-sources-and-sessions"></a>데이터 소스 및 세션

다음 그림은 데이터 원본에 대 한 연결 및 액세스를 지 원하는 클래스를 보여 줍니다. 각 클래스는 표준 OLE DB 구성 요소 구현을 기반으로 합니다.

![데이터 소스 및 세션 클래스](../../data/oledb/media/vcdatasourcesessionclasses.gif "데이터 소스 및 세션 클래스") <br/>
데이터 소스 및 세션 클래스

클래스는 다음과 같습니다.

- [Cdatasource](../../data/oledb/cdatasource-class.md) 이 클래스는 OLE DB 공급자를 통해 데이터 소스에 대 한 연결을 만들고 관리 하는 데이터 소스 개체를 인스턴스화합니다. 데이터 소스는 데이터 소스 주소와 인증 정보 같은 정보를 연결 문자열 형태로 가지고 있습니다.

   또한 도우미 클래스 [CEnumerator](../../data/oledb/cenumerator-class.md) 는 시스템에 등록 된 사용 가능한 공급자 목록을 가져오기 위해 연결을 설정 하기 전에 자주 사용 됩니다. 이렇게 되면 사용자는 공급자를 데이터 소스로서 선택할 수 있게 됩니다. 예를 들어 **데이터 연결 속성** 대화 상자는이 클래스를 사용 하 여 **공급자** 탭의 공급자 목록을 채웁니다. `SQLBrowseConnect` 또는 `SQLDriverConnect` 함수와 동일 합니다.

- [Csession](../../data/oledb/csession-class.md) 이 클래스는 데이터 소스에 대 한 단일 액세스 세션을 나타내는 session 개체를 인스턴스화합니다. 그러나 데이터 소스에 여러 세션을 만들 수 있습니다. 각 세션마다 데이터 소스의 데이터에 액세스하기 위해 행 집합, 명령 및 기타 개체를 만들 수 있습니다. 세션은 트랜잭션을 처리합니다.

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)
