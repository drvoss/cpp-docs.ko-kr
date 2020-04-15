---
title: CCommand 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
- CCommand.Close
- CCommand::Close
- CCommand.Create
- CCommand::Create
- CCommand.CreateCommand
- CreateCommand
- CCommand::CreateCommand
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
- GetParameterInfo
- CCommand.GetParameterInfo
- CCommand::GetParameterInfo
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
- CCommand.Prepare
- CCommand::Prepare
- Prepare
- CCommand.ReleaseCommand
- ReleaseCommand
- CCommand::ReleaseCommand
- SetParameterInfo
- CCommand.SetParameterInfo
- CCommand::SetParameterInfo
- Unprepare
- CCommand.Unprepare
- CCommand::Unprepare
helpviewer_keywords:
- CCommand class
- Close method
- Create method [C++]
- CreateCommand method
- GetNextResult method
- GetParameterInfo method
- Open method
- Prepare method
- ReleaseCommand method
- SetParameterInfo method
- Unprepare method
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
ms.openlocfilehash: 52c7e2ce5acdd2df33e2a6422535a337f0a43aec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368623"
---
# <a name="ccommand-class"></a>CCommand 클래스

명령을 설정하고 실행하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset,
   class TMultiple = CNoMultipleResults>
class CCommand :
   public CAccessorRowset <TAccessor, TRowset>,
   public CCommandBase,
   public TMultiple
```

### <a name="parameters"></a>매개 변수

*T 액세스 자*<br/>
명령을 사용할 접근자 클래스(예: `CDynamicParameterAccessor`" `CDynamicStringAccessor`또는) `CEnumeratorAccessor`형식입니다. 기본값은 `CNoAccessor`클래스가 매개 변수 또는 출력 열을 지원하지 않도록 지정하는 입니다.

*트로셋*<br/>
명령을 사용할 행 집합 클래스(예: `CArrayRowset` 또는)의 `CNoRowset`형식입니다. 기본값은 `CRowset`입니다.

*T멀티플*<br/>
여러 결과를 반환할 수 있는 OLE DB 명령을 사용하려면 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)를 지정합니다. 그렇지 않으면 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)를 사용합니다. 자세한 내용은 [IMultipleResults](/previous-versions/windows/desktop/ms721289(v=vs.85))을 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[닫기](#close)|현재 명령을 닫습니다.|
|[GetNext결과](#getnextresult)|여러 결과 집합을 사용할 때 다음 결과를 가져옵니다.|
|[열기](#open)|명령을 실행하고 선택적으로 바인딩합니다.|

### <a name="inherited-methods"></a>상속된 메서드

|||
|-|-|
|[만들기](#create)|지정된 세션에 대한 새 명령을 생성한 다음 명령 텍스트를 설정합니다.|
|[CreateCommand](#createcommand)|새 명령을 만듭니다.|
|[Get매개 변수 정보](#getparameterinfo)|명령의 매개 변수, 이름 및 해당 형식의 목록을 가져옵니다.|
|[준비](#prepare)|현재 명령의 유효성을 검사하고 최적화합니다.|
|[릴리스 명령](#releasecommand)|필요한 경우 매개 변수 접근자가 해제된 다음 명령을 해제합니다.|
|[세트매개 변수정보](#setparameterinfo)|각 명령 매개 변수의 기본 형식을 지정합니다.|
|[준비 취소](#unprepare)|현재 명령 실행 계획을 삭제합니다.|

## <a name="remarks"></a>설명

매개 변수 기반 작업을 수행하거나 명령을 실행해야 하는 경우 이 클래스를 사용합니다. 간단한 행 집합만 열어야 하는 경우 [대신 CTable을](../../data/oledb/ctable-class.md) 사용합니다.

사용 중인 접근자 클래스에 바인딩 매개 변수 및 데이터의 메서드가 결정됩니다.

해당 공급자는 저장 프로시저를 지원하지 않으므로 Jet용 OLE DB 공급자와 함께 저장 프로시저를 사용할 수 없습니다(쿼리 문자열에는 상수만 허용됨).

## <a name="ccommandclose"></a><a name="close"></a>CCommand::닫기

명령과 연결된 접근자 행 집합을 해제합니다.

### <a name="syntax"></a>구문

```cpp
void Close();
```

### <a name="remarks"></a>설명

명령은 행 집합, 결과 집합 접근자 및 (선택적으로) 매개 변수 접근자(매개 변수를 지원하지 않고 매개 변수 접근자가 필요하지 않은 테이블과 달리)를 사용합니다.

명령을 실행할 때 명령 후 `Close` 둘 다와 [ReleaseCommand를](../../data/oledb/ccommand-releasecommand.md) 호출해야 합니다.

동일한 명령을 반복적으로 실행하려면 호출하기 `Close` `Execute`전에 호출하여 각 결과 집합 접근자(accessor)를 해제해야 합니다. 시리즈의 끝에서 호출 하여 매개 변수 접근자 해제 `ReleaseCommand`해야 합니다. 또 다른 일반적인 시나리오는 출력 매개 변수가 있는 저장 프로시저를 호출하는 것입니다. 많은 공급자(예: SQL Server용 OLE DB 공급자)에서 결과 집합 접근자를 닫을 때까지 출력 매개 변수 값에 액세스할 수 없습니다. 반환된 행 집합 및 결과 집합 접근자가 아니라 매개 변수 접근자가 닫히도록 호출하여 `Close` 출력 매개 변수 값을 검색할 수 있습니다.

### <a name="example"></a>예제

다음 예제에서는 동일한 명령을 반복해서 실행할 때 `Close` 및 `ReleaseCommand`을 호출할 수 있는 방법을 보여 줍니다.

[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]

## <a name="ccommandgetnextresult"></a><a name="getnextresult"></a>CCommand::GetNextResult

사용 가능한 경우 다음 결과 집합을 가져옵니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,
   bool bBind = true) throw();
```

#### <a name="parameters"></a>매개 변수

*pulRows영향을 받습니다.*<br/>
[인/아웃] 명령의 영향을 받는 행 수가 반환되는 메모리에 대한 포인터입니다.

*bBind*<br/>
【인】 실행된 후 명령을 자동으로 바인딩할지 여부를 지정합니다. 기본값은 **true이며**명령이 자동으로 바인딩됩니다. *bBind를* **false로** 설정하면 수동으로 바인딩할 수 있도록 명령의 자동 바인딩이 방지됩니다. 수동 바인딩은 OLAP 사용자에게 특히 관심이 있습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT.

### <a name="remarks"></a>설명

결과 집합을 이전에 가져온 경우 이 함수는 이전 결과 집합을 해제하고 열을 바인딩 해제합니다. *bBind가* **true이면**새 열을 바인딩합니다.

템플릿 매개 변수 *TMultiple을*=`CMultipleResults`설정하여 여러 `CCommand` 결과를 지정한 경우에만 이 함수를 호출해야 합니다.

## <a name="ccommandopen"></a><a name="open"></a>CCommand:::열기

명령을 실행하고 선택적으로 바인딩합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   LPCSTR szCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   INT szCommand = NULL,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>매개 변수

*세션*<br/>
【인】 명령을 실행할 세션입니다.

*wszCommand*<br/>
【인】 실행할 명령으로 유니코드 문자열로 전달됩니다. 사용할 때 NULL일 수 있으며, 이 경우 DEFINE_COMMAND 매크로로 전달된 값에서 명령을 검색합니다. [DEFINE_COMMAND](../../data/oledb/define-command.md) `CAccessor` 자세한 내용은 [ICommand::실행을](/previous-versions/windows/desktop/ms718095(v=vs.85)) *OLE DB 프로그래머의 참조에서* 참조하십시오.

*szCommand*<br/>
【인】 이 매개 변수는 ANSI 명령 문자열을 사용 한다는 것을 제외 하 고 *wszCommand와* 동일 합니다. 이 메서드의 네 번째 형식은 NULL 값을 사용할 수 있습니다. 자세한 내용은 이 항목의 후반부 "비고"를 참조하십시오.

*pPropSet*<br/>
【인】 설정할 속성 및 값을 포함하는 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 구조의 배열에 대한 포인터입니다. Windows SDK에서 *OLE DB 프로그래머의 참조에서* [속성 집합 및 속성 그룹을](/previous-versions/windows/desktop/ms713696(v=vs.85)) 참조하십시오.

*pRows영향을 받습니다.*<br/>
[인/아웃] 명령의 영향을 받는 행 수가 반환되는 메모리에 대한 포인터입니다. * \*pRows영향을 받는* 것이 NULL이면 행 수가 반환되지 않습니다. 그렇지 `Open` 않으면 다음 조건에 따라 * \*pRows영향을* 받습니다.

|다음과 같은 경우|작업|
|--------|----------|
|요소가 `cParamSets` `pParams` 1보다 큽|pRows영향은 실행에 지정된 모든 매개 변수 집합의 영향을 받는 행의 총 수를 나타냅니다. * \**|
|영향을 받는 행 수를 사용할 수 없습니다.|pRows영향을 받는 -1로 설정됩니다. * \**|
|명령이 행을 업데이트, 삭제 또는 삽입하지 않습니다.|pRows영향을 받는 것은 정의되지 않습니다. * \**|

*guidCommand*<br/>
【인】 명령 텍스트를 구문 분석하는 데 사용할 공급자의 구문 및 일반 규칙을 지정하는 GUID입니다. 자세한 내용은 *올레 DB 프로그래머의 참조에서* [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) 및 [ICommandText::SetCommandText를](/previous-versions/windows/desktop/ms709757(v=vs.85)) 참조하십시오.

*bBind*<br/>
【인】 실행된 후 명령을 자동으로 바인딩할지 여부를 지정합니다. 기본값은 **true이며**명령이 자동으로 바인딩됩니다. *bBind를* **false로** 설정하면 수동으로 바인딩할 수 있도록 명령의 자동 바인딩이 방지됩니다. 수동 바인딩은 OLAP 사용자에게 특히 관심이 있습니다.

*ulPropSet*<br/>
【인】 *pPropSet* 인수에서 전달된 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 구조의 수입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT.

### <a name="remarks"></a>설명

처음 세 가지 `Open` 형태의 세션은 세션을 만들고 명령을 만들고 명령을 실행하여 필요에 따라 매개 변수를 바인딩합니다.

첫 번째 `Open` 형식은 유니코드 명령 문자열을 사용하며 기본값이 없습니다.

두 번째 `Open` 형식은 ANSI 명령 문자열을 사용하며 기본값은 없습니다(기존 ANSI 응용 프로그램과의 이전 버전과의 호환성을 위해 제공됨).

세 번째 `Open` 형식은 NULL의 기본값을 가진 **int** 형식 때문에 명령 문자열이 NULL이 될 수 있도록 합니다. `Open(session, NULL);` 호출또는 `Open(session);` NULL이 **int**형식이기 때문에 제공됩니다. 이 버전은 **int** 매개 변수가 NULL임을 요구하고 어설션합니다.

명령을 이미 만들었으며 단일 `Open` [준비](../../data/oledb/ccommand-prepare.md) 및 여러 실행을 수행하려는 경우의 네 번째 형식을 사용합니다.

> [!NOTE]
> `Open`호출됩니다. `Execute` `GetNextResult`

## <a name="ccommandcreate"></a><a name="create"></a>CCommand::만들기

[CCommand::CreateCommand를](../../data/oledb/ccommand-createcommand.md) 호출하여 지정된 세션에 대한 명령을 만든 다음 [ICommandText:SetCommandText를](/previous-versions/windows/desktop/ms709825(v=vs.85)) 호출하여 명령 텍스트를 지정합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::Create(const CSession& session,
   LPCWSTR wszCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();

HRESULT CCommandBase::Create(const CSession& session,
   LPCSTR szCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();
```

#### <a name="parameters"></a>매개 변수

*세션*<br/>
【인】 명령을 만들 세션입니다.

*wszCommand*<br/>
【인】 명령 문자열의 유니코드 텍스트에 대한 포인터입니다.

*szCommand*<br/>
【인】 명령 문자열의 ANSI 텍스트에 대한 포인터입니다.

*guidCommand*<br/>
【인】 명령 텍스트를 구문 분석하는 데 사용할 공급자의 구문 및 일반 규칙을 지정하는 GUID입니다. 방언에 대한 설명은 *OLE DB 프로그래머의 참조에서* [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) 를 참조하십시오.

### <a name="return-value"></a>Return Value

표준 HRESULT.

### <a name="remarks"></a>설명

첫 번째 `Create` 형식의 유니코드 명령 문자열을 받습니다. 두 번째 `Create` 형식은 ANSI 명령 문자열을 사용합니다(기존 ANSI 응용 프로그램과이전 버전과의 호환성을 위해 제공됨).

## <a name="ccommandcreatecommand"></a><a name="createcommand"></a>CCommand::만들기 명령

새 명령을 만듭니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();
```

#### <a name="parameters"></a>매개 변수

*세션*<br/>
【인】 새 `CSession` 명령과 연결할 개체입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT.

### <a name="remarks"></a>설명

이 메서드는 지정 된 세션 개체를 사용 하 여 명령을 만듭니다.

## <a name="ccommandgetparameterinfo"></a><a name="getparameterinfo"></a>CCommand::GetParameterInfo

명령의 매개 변수, 이름 및 해당 형식의 목록을 가져옵니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,
   DBPARAMINFO** ppParamInfo,
   OLECHAR** ppNamesBuffer) throw ();
```

#### <a name="parameters"></a>매개 변수

*올레 DB 프로그래머의 참조에서* [ICommandWithParameters::GetParameterInfo](/previous-versions/windows/desktop/ms714917(v=vs.85)) 를 참조하십시오.

### <a name="return-value"></a>Return Value

표준 HRESULT.

## <a name="ccommandprepare"></a><a name="prepare"></a>CCommand::P레파레

현재 명령의 유효성을 검사하고 최적화합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();
```

#### <a name="parameters"></a>매개 변수

*cExpected실행*<br/>
【인】 명령을 실행할 것으로 예상되는 횟수입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT.

### <a name="remarks"></a>설명

이 메서드는 OLE DB 메서드 [ICommandPrepare::P repare](/previous-versions/windows/desktop/ms718370(v=vs.85))를 래핑합니다.

## <a name="ccommandreleasecommand"></a><a name="releasecommand"></a>CCommand::릴리스 명령

매개 변수 접근자가 해제된 다음 명령 자체를 해제합니다.

### <a name="syntax"></a>구문

```cpp
void CCommandBase::ReleaseCommand() throw();
```

### <a name="remarks"></a>설명

`ReleaseCommand`와 `Close`함께 사용됩니다. 사용 세부 정보는 [닫기(Close)를](../../data/oledb/ccommand-close.md) 참조하십시오.

## <a name="ccommandsetparameterinfo"></a><a name="setparameterinfo"></a>CCommand::setParameterInfo

각 명령 매개 변수의 기본 형식을 지정합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,
   const DBORDINAL* pOrdinals,
   const DBPARAMBINDINFO* pParamInfo) throw();
```

#### <a name="parameters"></a>매개 변수

*올레 DB 프로그래머의 참조에서* [ICommandWithParameters::SetParameterInfo를](/previous-versions/windows/desktop/ms725393(v=vs.85)) 참조하십시오.

### <a name="return-value"></a>Return Value

표준 HRESULT.

## <a name="ccommandunprepare"></a><a name="unprepare"></a>CCommand:::준비 취소

현재 명령 실행 계획을 삭제합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::Unprepare() throw();
```

### <a name="return-value"></a>Return Value

표준 HRESULT.

### <a name="remarks"></a>설명

이 메서드는 OLE DB 메서드 [ICommandPrepare:준비 취소](/previous-versions/windows/desktop/ms719635(v=vs.85))를 래핑합니다.

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)
