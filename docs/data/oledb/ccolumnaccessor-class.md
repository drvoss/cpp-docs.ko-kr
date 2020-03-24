---
title: CColumnAccessor 클래스
ms.date: 11/04/2016
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
ms.openlocfilehash: 2a3b1dac51a8300a915a7177c36f15512b583fa0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212112"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor 클래스

삽입 된 소비자 코드를 생성 합니다.

## <a name="syntax"></a>구문

```cpp
class CColumnAccessor : public CAccessorBase
```

## <a name="remarks"></a>주의

삽입 된 코드에서 모든 열은 별도의 접근자로 바인딩됩니다. 이 클래스는 삽입 된 코드 (예: 디버그할 때 발생할 수 있음)에서 사용 되지만 일반적으로이 클래스 또는 해당 메서드를 직접 사용할 필요는 없습니다.

`CColumnAccessor`는 다음과 같은 스텁 메서드를 구현 합니다. 각 메서드는 다른 접근자 클래스 메서드의 기능에 해당 합니다.

- 생성자를 `CColumnAccessor` 합니다. `CColumnAccessor` 개체를 인스턴스화하고 초기화 합니다.

- `CreateAccessor`는 열 바인딩 구조에 메모리를 할당 하 고 열 데이터 멤버를 초기화 합니다.

- `BindColumns` 접근자에 열을 바인딩합니다.

- `SetParameterBuffer`은 매개 변수에 대 한 버퍼를 할당 합니다.

- `AddParameter` 매개 변수 항목을 매개 변수 항목 구조에 추가 합니다.

- `HasOutputColumns` 접근자에 출력 열이 있는지 여부를 확인 합니다.

- `HasParameters` 접근자에 매개 변수가 있는지 여부를 확인 합니다.

- `BindParameters` 생성 된 매개 변수를 열에 바인딩합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)
