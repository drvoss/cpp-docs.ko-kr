---
title: CDataConnection 클래스
ms.date: 03/27/2019
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
- CDataConnection.Open
- ATL.CDataConnection.Open
- CDataConnection::Open
- ATL::CDataConnection::Open
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
helpviewer_keywords:
- CDataConnection class
- CDataConnection class, constructor
- Copy method
- Open method
- OpenNewSession method
- BOOL operator
- operator bool
- BOOL operator
- operator bool
- CDataSource& operator
- operator & (CDataSource)
- CDataSource* operator
- operator * (CDataSource)
- operator CSession&
- CSession& operator
- operator CSession*
- CSession* operator
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
ms.openlocfilehash: fe954e218a099fa7956748904a4baa89f741c52f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368609"
---
# <a name="cdataconnection-class"></a>CDataConnection 클래스

데이터 원본과의 연결을 관리합니다.

## <a name="syntax"></a>구문

```cpp
class CDataConnection
```

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[C데이터 연결](#cdataconnection)|생성자입니다. `CDataConnection` 개체를 인스턴스화하고 초기화합니다.|
|[복사](#copy)|기존 데이터 연결의 복사본을 만듭니다.|
|[열기](#open)|초기화 문자열을 사용하여 데이터 원본에 대한 연결을 엽니다.|
|[오픈뉴세션](#opennewsession)|현재 연결에서 새 세션을 엽니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 BOOL](#op_bool)|현재 세션이 열려 있는지 여부를 결정합니다.|
|[연산자 bool](#op_bool_ole)|현재 세션이 열려 있는지 여부를 결정합니다.|
|[운영자 CDataSource&](#op_cdata_amp)|포함된 `CDataSource` 개체에 대한 참조를 반환합니다.|
|[연산자 CDataSource*](#op_cdata_star)|포함된 `CDataSource` 개체에 대한 포인터를 반환합니다.|
|[운영자 CSession&](#op_csession_amp)|포함된 `CSession` 개체에 대한 참조를 반환합니다.|
|[연산자 CSession*](#op_csession_star)|포함된 `CSession` 개체에 대한 포인터를 반환합니다.|

## <a name="remarks"></a>설명

`CDataConnection`는 필요한 개체(데이터 원본 및 세션)와 데이터 원본에 연결할 때 수행해야 하는 작업 중 일부를 캡슐화하기 때문에 클라이언트를 만드는 데 유용한 클래스입니다.

을 `CDataConnection`사용하지 않으면 `CDataSource` 개체를 만들고 [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) 메서드를 호출한 다음 [CSession](../../data/oledb/csession-class.md) 개체의 인스턴스를 만들고 [Open](../../data/oledb/csession-open.md) 메서드를 `Open`호출한 다음 [CCommand](../../data/oledb/ccommand-class.md) 개체를 만들고 * 메서드를 호출해야 합니다.

을 `CDataConnection`사용하면 연결 개체를 만들고 초기화 문자열을 전달한 다음 해당 연결을 사용하여 명령을 열기만 하면 됩니다. 데이터베이스에 대한 연결을 반복적으로 사용하려는 경우 연결을 열어 두는 것이 좋으며 `CDataConnection` 편리한 방법을 제공합니다.

> [!NOTE]
> 여러 세션을 처리해야 하는 데이터베이스 응용 프로그램을 만드는 경우 [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)을 사용해야 합니다.

## <a name="cdataconnectioncdataconnection"></a><a name="cdataconnection"></a>C데이터 연결::CData연결

`CDataConnection` 개체를 인스턴스화하고 초기화합니다.

### <a name="syntax"></a>구문

```cpp
CDataConnection();
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>매개 변수

*Ds*<br/>
【인】 기존 데이터 연결에 대한 참조입니다.

### <a name="remarks"></a>설명

첫 번째 재정의는 `CDataConnection` 기본 설정으로 새 오브젝트를 만듭니다.

두 번째 재정의는 `CDataConnection` 지정한 데이터 연결 객체와 동일한 설정으로 새 객체를 만듭니다.

## <a name="cdataconnectioncopy"></a><a name="copy"></a>CData연결::복사

기존 데이터 연결의 복사본을 만듭니다.

### <a name="syntax"></a>구문

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>매개 변수

*Ds*<br/>
【인】 복사할 기존 데이터 연결에 대한 참조입니다.

## <a name="cdataconnectionopen"></a><a name="open"></a>CData연결::열기

초기화 문자열을 사용하여 데이터 원본에 대한 연결을 엽니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>매개 변수

*szInitString*<br/>
【인】 데이터 원본의 초기화 문자열입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT.

## <a name="cdataconnectionopennewsession"></a><a name="opennewsession"></a>CData연결::열기 새세션

현재 연결 개체의 데이터 원본을 사용하여 새 세션을 엽니다.

### <a name="syntax"></a>구문

```cpp
HRESULT OpenNewSession(CSession & session) throw();
```

#### <a name="parameters"></a>매개 변수

*세션*<br/>
[인/아웃] 새 세션 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

새 세션에서는 현재 연결 개체의 포함된 데이터 원본 개체를 부모로 사용하고 데이터 원본과 동일한 모든 정보에 액세스할 수 있습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT.

## <a name="cdataconnectionoperator-bool"></a><a name="op_bool"></a>CData연결::연산자 BOOL

현재 세션이 열려 있는지 여부를 결정합니다.

### <a name="syntax"></a>구문

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>설명

**BOOL(MFC** 형식 def) 값을 반환합니다. **TRUE는** 현재 세션이 열려 있다는 것을 의미합니다. **FALSE는** 현재 세션이 닫혔을 때를 의미합니다.

## <a name="cdataconnectionoperator-bool-ole-db"></a><a name="op_bool_ole"></a>CDataConnection::연산자 bool (올레 DB)

현재 세션이 열려 있는지 여부를 결정합니다.

### <a name="syntax"></a>구문

```cpp
operator bool() throw();
```

### <a name="remarks"></a>설명

**bool(C++** 데이터 형식) 값을 반환합니다. **true는** 현재 세션이 열려 있다는 것을 의미합니다. **false는** 현재 세션이 닫혔을 때를 의미합니다.

## <a name="cdataconnectionoperator-cdatasourceamp"></a><a name="op_cdata_amp"></a>CData연결::연산자 CDatasource&amp;

포함된 `CDataSource` 개체에 대한 참조를 반환합니다.

### <a name="syntax"></a>구문

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>설명

이 연산자는 포함된 `CDataSource` 개체에 대한 참조를 `CDataConnection` 반환하므로 `CDataSource` 참조가 예상되는 개체를 전달할 수 있습니다.

### <a name="example"></a>예제

참조를 사용하는 함수(예: `func` 아래)가 있는 경우 대신 개체를 `CDataSource&` `CDataConnection` 전달하는 데 사용할 수 있습니다. `CDataSource`

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="cdataconnectionoperator-cdatasource"></a><a name="op_cdata_star"></a>CData연결::연산자 CDataSource*

포함된 `CDataSource` 개체에 대한 포인터를 반환합니다.

### <a name="syntax"></a>구문

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>설명

이 연산자는 `CDataSource` 포인터가 예상되는 위치에 `CDataConnection` 개체를 전달할 수 있게 해주는, 포함된 `CDataSource` 개체에 대한 포인터를 반환합니다.

사용 예제는 [운영자 CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) 참조하세요.

## <a name="cdataconnectionoperator-csessionamp"></a><a name="op_csession_amp"></a>CData연결::연산자 CSession&amp;

포함된 `CSession` 개체에 대한 참조를 반환합니다.

### <a name="syntax"></a>구문

```cpp
operator const CSession&();
```

### <a name="remarks"></a>설명

이 연산자는 포함된 `CSession` 개체에 대한 참조를 `CDataConnection` 반환하므로 `CSession` 참조가 예상되는 개체를 전달할 수 있습니다.

### <a name="example"></a>예제

참조를 사용하는 함수(예: `func` 아래)가 있는 경우 대신 개체를 `CSession&` `CDataConnection` 전달하는 데 사용할 수 있습니다. `CSession`

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="cdataconnectionoperator-csession"></a><a name="op_csession_star"></a>CData연결::연산자 CSession*

포함된 `CSession` 개체에 대한 포인터를 반환합니다.

### <a name="syntax"></a>구문

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>설명

이 연산자는 `CSession` 포인터가 예상되는 위치에 `CDataConnection` 개체를 전달할 수 있게 해주는, 포함된 `CSession` 개체에 대한 포인터를 반환합니다.

### <a name="example"></a>예제

사용 예제는 [운영자 CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md) 참조하세요.

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)
