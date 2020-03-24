---
title: db_source (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_source
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
ms.openlocfilehash: 6346a8d6f60313dc17bbcbad062aa888857f0b67
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167279"
---
# <a name="db_source"></a>db_source

데이터 원본에 대 한 연결을 만듭니다.

## <a name="syntax"></a>구문

```cpp
[ db_source(db_source, name, hresult) ]
```

### <a name="parameters"></a>매개 변수

*db_source*<br/>
데이터 원본에 연결 하는 데 사용 되는 연결 문자열입니다. 연결 문자열의 형식에 대해서는 MDAC (Microsoft Data Access Components) SDK의 [연결 문자열 및 데이터 링크](/previous-versions/windows/desktop/ms718376(v=vs.85)) 를 참조 하세요.

*name*<br/>
필드 클래스에서 **db_source** 를 사용 하는 경우 *name* 은 **db_source** 특성이 적용 된 데이터 원본 개체의 인스턴스입니다 (예 1 참조). 메서드 구현에서 인라인 **db_source** 를 사용 하는 경우 *name* 은 데이터 원본에 액세스 하는 데 사용할 수 있는 변수 (메서드에 대 한 로컬)입니다 (예제 2 참조). 이 *이름을* `db_command`의 *source_name* 매개 변수에 전달 하 여 데이터 소스를 명령과 연결 합니다.

*hresult*<br/>
(선택 사항) 이 데이터베이스 명령의 HRESULT를 수신할 변수를 식별합니다. 변수가 없으면 특성에 의해 자동으로 삽입됩니다.

## <a name="remarks"></a>설명

**db_source** 는 [Cdatasource](../../data/oledb/cdatasource-class.md) 와 [cdatasource](../../data/oledb/csession-class.md) 개체를 만듭니다 .이 개체는 OLE DB 소비자 데이터 원본과의 연결을 나타냅니다.

클래스에서 **db_source** 를 사용 하는 경우 `CSession` 개체는 클래스의 멤버가 됩니다.

메서드에서 **db_source** 를 사용 하는 경우 삽입 된 코드는 메서드 범위 내에서 실행 되 고 `CSession` 개체는 지역 변수로 생성 됩니다.

**db_source** 는 클래스 또는 메서드 내에 데이터 소스 속성을 추가 합니다. *Db_source* *name* 매개 변수를 *source_name* 매개 변수로 사용 하는 `db_command`와 함께 사용 됩니다.

소비자 특성 공급자가 클래스에 이 특성을 적용하는 경우 컴파일러는 클래스의 이름을 _\_*YourClassName*Accessor로 바꿉니다. 여기서 *YourClassName*은 클래스에 지정한 이름입니다. 컴파일러는 또한YourClassName\_Accessor에서 파생되는 *YourClassName*이라는 클래스를 만듭니다.  클래스 뷰에 두 클래스 모두 표시됩니다.

응용 프로그램에서 사용 되는이 특성의 예는 [Multiread](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer)를 참조 하세요.

## <a name="example"></a>예제

이 샘플에서는 Northwind 데이터베이스를 사용 하 `ds` 데이터 소스에 대 한 연결을 만들기 위해 클래스에 대 한 **db_source** 를 호출 합니다. `ds`은 `CMyCommand` 클래스에 내부적으로 사용할 수 있는 데이터 소스에 대 한 핸들입니다.

```cpp
// db_source_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[
  db_source(L"my_connection_string", name="ds"),
  db_command(L"select * from Products")
]
class CMyCommand {};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**클래스**, **구조체**, 멤버, 메서드, 로컬|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|None|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 특성](ole-db-consumer-attributes.md)
