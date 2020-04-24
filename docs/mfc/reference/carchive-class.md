---
title: CArchive 클래스
ms.date: 11/04/2016
f1_keywords:
- CArchive
- AFX/CArchive
- AFX/CArchive::CArchive
- AFX/CArchive::Abort
- AFX/CArchive::Close
- AFX/CArchive::Flush
- AFX/CArchive::GetFile
- AFX/CArchive::GetObjectSchema
- AFX/CArchive::IsBufferEmpty
- AFX/CArchive::IsLoading
- AFX/CArchive::IsStoring
- AFX/CArchive::MapObject
- AFX/CArchive::Read
- AFX/CArchive::ReadClass
- AFX/CArchive::ReadObject
- AFX/CArchive::ReadString
- AFX/CArchive::SerializeClass
- AFX/CArchive::SetLoadParams
- AFX/CArchive::SetObjectSchema
- AFX/CArchive::SetStoreParams
- AFX/CArchive::Write
- AFX/CArchive::WriteClass
- AFX/CArchive::WriteObject
- AFX/CArchive::WriteString
- AFX/CArchive::m_pDocument
helpviewer_keywords:
- CArchive [MFC], CArchive
- CArchive [MFC], Abort
- CArchive [MFC], Close
- CArchive [MFC], Flush
- CArchive [MFC], GetFile
- CArchive [MFC], GetObjectSchema
- CArchive [MFC], IsBufferEmpty
- CArchive [MFC], IsLoading
- CArchive [MFC], IsStoring
- CArchive [MFC], MapObject
- CArchive [MFC], Read
- CArchive [MFC], ReadClass
- CArchive [MFC], ReadObject
- CArchive [MFC], ReadString
- CArchive [MFC], SerializeClass
- CArchive [MFC], SetLoadParams
- CArchive [MFC], SetObjectSchema
- CArchive [MFC], SetStoreParams
- CArchive [MFC], Write
- CArchive [MFC], WriteClass
- CArchive [MFC], WriteObject
- CArchive [MFC], WriteString
- CArchive [MFC], m_pDocument
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
ms.openlocfilehash: ef8b6ec9060e8c15dd45f8203dadd2a2aca9e168
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753110"
---
# <a name="carchive-class"></a>CArchive 클래스

해당 개체가 삭제된 후에도 지속되는 영구 이진 양식(일반적으로 디스크 저장소)에 복잡한 개체 네트워크를 저장할 수 있습니다.

## <a name="syntax"></a>구문

```
class CArchive
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CArchive::CArchive](#carchive)|`CArchive` 개체를 만듭니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C 아카이브 ::중단](#abort)|예외를 throw 하지 않고 아카이브를 닫습니다.|
|[CArchive::Close](#close)|기록되지 않은 데이터를 플러시하고 `CFile`에서 연결을 끊습니다.|
|[CArchive::Flush](#flush)|아카이브 버퍼에서 기록되지 않은 데이터를 플러시합니다.|
|[C아카이브::GetFile](#getfile)|이 `CFile` 아카이브에 대한 개체 포인터를 가져옵니다.|
|[CArchive::GetObjectSchema](#getobjectschema)|`Serialize` 함수에서 호출되어 역직렬화되는 개체의 버전을 결정합니다.|
|[C아카이브::IsBufferEmpty](#isbufferempty)|Windows 소켓 수신 프로세스 중에 버퍼가 비워졌는지 여부를 확인합니다.|
|[CArchive::IsLoading](#isloading)|아카이브가 로드되고 있는지 여부를 결정합니다.|
|[C아카이브::저장](#isstoring)|아카이브가 저장되고 있는지 여부를 결정합니다.|
|[CArchive::MapObject](#mapobject)|파일에 직렬화되지 는 않지만 하위 개체를 참조할 수 있는 객체를 맵에 배치합니다.|
|[CArchive::Read](#read)|원시 바이트를 읽습니다.|
|[C아카이브::읽기 클래스](#readclass)|에 이전에 저장된 클래스 `WriteClass`참조를 읽습니다.|
|[CArchive::ReadObject](#readobject)|로드를 위해 `Serialize` 개체의 함수를 호출합니다.|
|[CArchive::ReadString](#readstring)|한 줄의 텍스트를 읽습니다.|
|[C아카이브::직렬화클래스](#serializeclass)|의 방향에 따라 개체에 `CArchive` 대한 클래스 참조를 읽거나 씁니다. `CArchive`|
|[CArchive::SetLoadParams](#setloadparams)|로드 배열이 증가하는 크기를 설정합니다. 개체가 로드되기 전에 호출해야 `MapObject` `ReadObject` 하거나 호출되기 전에 호출해야 합니다.|
|[C아카이브::세트오브젝트스키마](#setobjectschema)|아카이브 개체에 저장된 개체 스키마를 설정합니다.|
|[C아카이브::세트스토어파라름](#setstoreparams)|리시브화 프로세스 중에 고유한 개체를 식별하는 데 사용되는 맵의 해시 테이블 크기와 블록 크기를 설정합니다.|
|[CArchive::Write](#write)|원시 바이트를 씁니다.|
|[C아카이브::쓰기 클래스](#writeclass)|에 대한 `CRuntimeClass` 참조를 `CArchive`씁니다.|
|[CArchive::WriteObject](#writeobject)|저장을 위해 `Serialize` 개체의 함수를 호출합니다.|
|[CArchive::WriteString](#writestring)|한 줄의 텍스트를 씁니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C보관::연산자&lt;&lt;](#operator_lt_lt)|개체 및 기본 형식을 아카이브에 저장합니다.|
|[C보관::연산자&gt;&gt;](#operator_gt_gt)|아카이브에서 개체 및 기본 형식을 로드합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C아카이브:m_pDocument](#m_pdocument)||

## <a name="remarks"></a>설명

`CArchive`기본 클래스가 없습니다.

나중에 영구 저장소에서 개체를 로드하여 메모리에 다시 구성할 수 있습니다. 데이터를 영구적으로 만드는 이 프로세스를 "직렬화"라고 합니다.

아카이브 개체를 일종의 이진 스트림으로 생각할 수 있습니다. 입력/출력 스트림과 마찬가지로 아카이브는 파일과 연결되며 저장소에서 데이터를 버퍼링하고 읽을 수 있습니다. 입력/출력 스트림은 ASCII 문자의 시퀀스를 처리하지만 아카이브는 이진 개체 데이터를 효율적이고 중복되지 않는 형식으로 처리합니다.

개체를 만들려면 먼저 [CFile](../../mfc/reference/cfile-class.md) 개체를 `CArchive` 만들어야 합니다. 또한 아카이브의 로드/저장소 상태가 파일의 열기 모드와 호환되도록 해야 합니다. 파일당 하나의 활성 아카이브로 제한됩니다.

개체를 `CArchive` 생성할 때 열린 파일을 나타내는 `CFile` 클래스(또는 파생 클래스)의 개체에 연결합니다. 또한 아카이브를 로드 또는 저장에 사용할지 여부를 지정합니다. 개체는 `CArchive` 기본 형식뿐만 아니라 직렬화를 위해 설계된 [CObject](../../mfc/reference/cobject-class.md)-derived 클래스의 개체도 처리할 수 있습니다. Serializable 클래스는 일반적으로 `Serialize` 멤버 함수를 포함하며, 일반적으로 `CObject` 클래스 아래에 설명된 대로 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로를 사용합니다.

오버로드된 추출 **>>**() 및 **<<** 삽입 () 연산자는 기본 형식과 `CObject`-derived 클래스를 모두 지원하는 편리한 아카이브 프로그래밍 인터페이스입니다.

`CArchive`또한 MFC 윈도우 소켓 클래스 [C소켓](../../mfc/reference/csocket-class.md) 및 [CSocketFile와](../../mfc/reference/csocketfile-class.md)프로그래밍을 지원합니다. [IsBufferEmpty](#isbufferempty) 멤버 함수는 해당 사용을 지원합니다.

자세한 내용은 [직렬화](../../mfc/serialization-in-mfc.md) 및 [Windows 소켓: 아카이브가 있는 소켓 사용](../../mfc/windows-sockets-using-sockets-with-archives.md)문서를 참조하십시오. `CArchive`

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CArchive`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="carchiveabort"></a><a name="abort"></a>C 아카이브 ::중단

예외를 throw 하지 않고 아카이브를 닫도록 이 함수를 호출합니다.

```cpp
void Abort ();
```

### <a name="remarks"></a>설명

`CArchive` 소멸자는 일반적으로 호출되며, `Close` `CFile` 연결된 개체에 저장되지 않은 데이터를 플러시합니다. 이로 인해 예외가 발생할 수 있습니다.

이러한 예외를 catch할 `Abort` `CArchive` 때는 개체를 파괴해도 추가 예외가 발생하지 않도록 사용하는 것이 좋습니다. 예외를 `CArchive::Abort` 처리할 때 [CArchive::Close와](#close)달리 실패를 `Abort` 무시하기 때문에 실패에 대한 예외를 throw하지 않습니다.

**힙에** 개체를 `CArchive` 할당하는 데 새 개체를 사용한 경우 파일을 닫은 후 삭제해야 합니다.

### <a name="example"></a>예제

  [CArchive::WriteClass](#writeclass)에 대한 예제를 참조하십시오.

## <a name="carchivecarchive"></a><a name="carchive"></a>C아카이브::C아카이브

개체를 `CArchive` 생성하고 개체를 로드하거나 저장하는 데 사용할지 여부를 지정합니다.

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>매개 변수

*pFile*<br/>
영구 데이터의 `CFile` 궁극적인 원본 또는 대상인 개체에 대한 포인터입니다.

*nMode*<br/>
개체를 로드할지 아카이브에 저장할지 여부를 지정하는 플래그입니다. *nMode* 매개 변수는 다음 값 중 하나를 가져야 합니다.

- `CArchive::load`아카이브에서 데이터를 로드합니다. 읽기 `CFile` 권한만 필요합니다.

- `CArchive::store`데이터를 아카이브에 저장합니다. 쓰기 `CFile` 권한이 필요합니다.

- `CArchive::bNoFlushOnDelete`아카이브 소멸자가 호출될 `Flush` 때 아카이브가 자동으로 호출되지 않도록 합니다. 이 플래그를 설정하면 소멸자가 호출되기 전에 명시적으로 호출해야 `Close` 합니다. 그렇지 않으면 데이터가 손상됩니다.

*nBufSize*<br/>
내부 파일 버퍼의 크기를 바이트로 지정하는 정수입니다. 기본 버퍼 크기는 4,096바이트입니다. 큰 개체를 정기적으로 보관하는 경우 파일 버퍼 크기의 배수인 더 큰 버퍼 크기를 사용하는 경우 성능이 향상됩니다.

*lpBuf*<br/>
*nBufSize*크기의 사용자가 제공한 버퍼에 대한 선택적 포인터입니다. 이 매개 변수를 지정하지 않으면 아카이브는 로컬 힙에서 버퍼를 할당하고 개체가 소멸될 때 버퍼를 해제합니다. 아카이브는 사용자가 제공한 버퍼를 해제하지 않습니다.

### <a name="remarks"></a>설명

아카이브를 만든 후에는 이 사양을 변경할 수 없습니다.

아카이브를 닫을 때까지 작업을 사용하여 `CFile` 파일 상태를 변경할 수 없습니다. 이러한 작업은 아카이브의 무결성을 손상시게 됩니다. [GetFile](#getfile) 멤버 함수에서 아카이브의 파일 개체를 얻은 다음 [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) 함수를 사용하여 직렬화 하는 동안 언제든지 파일 포인터의 위치에 액세스할 수 있습니다. 파일 포인터의 위치를 얻기 전에 [CArchive::Flush를](#flush) 호출해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

## <a name="carchiveclose"></a><a name="close"></a>C아카이브::닫기

버퍼에 남아 있는 데이터를 플러시하고, 아카이브를 닫고, 파일에서 아카이브를 분리합니다.

```cpp
void Close();
```

### <a name="remarks"></a>설명

아카이브에 대한 추가 작업은 허용되지 않습니다. 아카이브를 닫은 후 동일한 파일에 대해 다른 아카이브를 만들거나 파일을 닫을 수 있습니다.

멤버 함수는 `Close` 모든 데이터가 아카이브에서 파일로 전송되도록 하고 아카이브를 사용할 수 없게 만듭니다. 파일에서 저장소 매체로의 전송을 완료하려면 먼저 [CFile::Close를](../../mfc/reference/cfile-class.md#close) 사용한 `CFile` 다음 개체를 삭제해야 합니다.

### <a name="example"></a>예제

  [CArchive::WriteString](#writestring)에 대한 예제를 참조하십시오.

## <a name="carchiveflush"></a><a name="flush"></a>C 아카이브 :: 플러시

아카이브 버퍼에 남아 있는 모든 데이터를 파일에 기록하도록 강제합니다.

```cpp
void Flush();
```

### <a name="remarks"></a>설명

멤버 함수는 `Flush` 모든 데이터가 아카이브에서 파일로 전송되도록 합니다. 파일에서 저장소 매체로의 전송을 완료하려면 [CFile::Close를](../../mfc/reference/cfile-class.md#close) 호출해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

## <a name="carchivegetfile"></a><a name="getfile"></a>C아카이브::GetFile

이 `CFile` 아카이브에 대한 개체 포인터를 가져옵니다.

```
CFile* GetFile() const;
```

### <a name="return-value"></a>Return Value

사용 중 개체에 대한 `CFile` 상수 포인터입니다.

### <a name="remarks"></a>설명

를 사용하기 `GetFile`전에 아카이브를 플러시해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

## <a name="carchivegetobjectschema"></a><a name="getobjectschema"></a>C아카이브::겟오브젝트스키마

함수에서 이 `Serialize` 함수를 호출하여 현재 역직렬화중인 개체의 버전을 확인합니다.

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>Return Value

역직렬화 하는 동안 읽을 개체의 버전입니다.

### <a name="remarks"></a>설명

이 함수를 호출하는 `CArchive` 것은 개체가 로드될 때만 유효합니다(CArchive::IsLoading은 영하지 않음을 반환합니다). [CArchive::IsLoading](#isloading) `Serialize` 함수의 첫 번째 호출이어야 하며 한 번만 호출해야 합니다. 반환 값(UINT)-1은 버전 번호를 알 수 없음을 나타냅니다.

-derived 클래스는 `CObject`스키마 버전 자체(IMPLEMENT_SERIAL **매크로)와**결합된 VERSIONABLE_SCHEMA 사용하여 "버전이 가능한 개체", 즉 멤버 함수가 여러 버전을 읽을 수 있는 `Serialize` 개체를 만들 수 있습니다. VERSIONABLE_SCHEMA 않고 기본 프레임워크 기능은 버전이 일치하지 않으면 예외를 throw하는 것입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

## <a name="carchiveisbufferempty"></a><a name="isbufferempty"></a>C아카이브::IsBufferEmpty

이 멤버 함수를 호출하여 아카이브 개체의 내부 버퍼가 비어 있는지 확인합니다.

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>Return Value

아카이브의 버퍼가 비어 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 MFC Windows 소켓 클래스의 `CSocketFile`프로그래밍을 지원하기 위해 제공됩니다. `CFile` 개체와 연결된 아카이브에 사용할 필요가 없습니다.

개체와 연결된 `IsBufferEmpty` 아카이브와 함께 사용하는 이유는 아카이브의 버퍼에 두 개 이상의 메시지 또는 레코드가 포함될 수 있기 때문입니다. `CSocketFile` 하나의 메시지를 받은 후에는 `IsBufferEmpty` 버퍼가 비어 있을 때까지 데이터를 계속 받는 루프를 제어하는 데 사용해야 합니다. 자세한 내용은 `IsBufferEmpty`를 사용하는 방법을 보여 주는 클래스 `CAsyncSocket`의 [Receive](../../mfc/reference/casyncsocket-class.md#receive) 멤버 함수를 참조하세요.

자세한 내용은 [Windows 소켓: 아카이브가 있는 소켓 사용.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="carchiveisloading"></a><a name="isloading"></a>C아카이브::로딩 중

아카이브가 데이터를 로드하는지 여부를 결정합니다.

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>Return Value

아카이브가 현재 로드에 사용되는 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 `Serialize` 보관된 클래스의 함수에 의해 호출됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

## <a name="carchiveisstoring"></a><a name="isstoring"></a>C아카이브::저장

아카이브가 데이터를 저장하는지 여부를 결정합니다.

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>Return Value

아카이브가 현재 저장에 사용되는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 `Serialize` 보관된 클래스의 함수에 의해 호출됩니다.

아카이브의 `IsStoring` 상태가 0이 아닌 경우 `IsLoading` 해당 상태는 0이고 그 반대의 경우도 마찬가지입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

## <a name="carchivemapobject"></a><a name="mapobject"></a>C아카이브::맵오브젝트

이 멤버 함수를 호출하여 실제로 파일에 직렬화되지는 않지만 하위 개체가 참조할 수 있는 객체를 맵에 배치합니다.

```cpp
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>매개 변수

*pOb*<br/>
저장 중인 개체에 대한 상수 포인터입니다.

### <a name="remarks"></a>설명

예를 들어 문서를 직렬화하지 는 않지만 문서의 일부인 항목을 직렬화할 수 있습니다. 을 `MapObject`호출하면 해당 항목 또는 하위 개체가 문서를 참조할 수 있습니다. 또한 직렬화된 하위 항목은 *m_pDocument* 백 포인터를 직렬화할 수 있습니다.

개체에 `MapObject` 저장하고 로드할 때 `CArchive` 호출할 수 있습니다. `MapObject`직렬화 및 역직렬화 중에 `CArchive` 개체가 유지 관리하는 내부 데이터 구조에 지정된 개체를 추가하지만 [ReadObject](#readobject) 및 [WriteObject와](#writeobject)달리 개체에서 직렬화를 호출하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

## <a name="carchivem_pdocument"></a><a name="m_pdocument"></a>C아카이브:m_pDocument

기본적으로 NULL로 설정하면 이 `CDocument` 포인터를 `CArchive` 인스턴스 사용자가 원하는 모든 것으로 설정할 수 있습니다.

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>설명

이 포인터의 일반적인 용도는 직렬화되는 모든 개체에 직렬화 프로세스에 대한 추가 정보를 전달하는 것입니다. 이는 문서 내의 개체가 필요한 경우 `CDocument`문서에 액세스할 수 있는 방식으로 직렬화되는 문서(-파생 클래스)로 포인터를 초기화하여 달성됩니다. 이 포인터는 직렬화 하는 동안 개체에서도 `COleClientItem` 사용 됩니다.

프레임워크는 사용자가 파일 열기 또는 저장 명령을 *실행하면* m_pDocument 직렬화되는 문서로 설정합니다. 파일 열기 또는 저장 이외의 이유로 개체 연결 및 포함(OLE) 컨테이너 문서를 직렬화하는 경우 *m_pDocument*명시적으로 설정해야 합니다. 예를 들어 컨테이너 문서를 Clipboard에 직렬화할 때 이 작업을 수행합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]

## <a name="carchiveoperator-ltlt"></a><a name="operator_lt_lt"></a>C보관::연산자&lt;&lt;

표시된 개체 또는 기본 형식을 아카이브에 저장합니다.

```
friend CArchive& operator<<(
    CArchive& ar,
    const CObject* pOb);

throw(
    CArchiveException*,
    CFileException*);

CArchive& AFXAPI operator<<(
    CArchive& ar,
    const RECT& rect);

CArchive& AFXAPI operator<<(
    CArchive& ar,
    POINT point);

CArchive& AFXAPI operator<<(
    CArchive& ar,
    SIZE size);

template<typename BaseType,
    class StringTraits> CArchive& operator<<(
    const ATL::CStringT<BaseType,
    StringTraits>& str);

CArchive& operator<<(BYTE by);
CArchive& operator<<(WORD w);
CArchive& operator<<(LONG l);
CArchive& operator<<(DWORD dw);
CArchive& operator<<(float f);
CArchive& operator<<(double d);
CArchive& operator<<(int i);
CArchive& operator<<(short w);
CArchive& operator<<(char ch);
CArchive& operator<<(wchar_t ch);
CArchive& operator<<(unsigned u);
CArchive& operator<<(bool b);
CArchive& operator<<(ULONGLONG dwdw);
CArchive& operator<<(LONGLONG dwdw);
```

### <a name="return-value"></a>Return Value

한 `CArchive` 줄에 여러 삽입 연산자가 활성화되는 참조입니다.

### <a name="remarks"></a>설명

위의 마지막 두 버전은 특히 64비트 정수 저장용입니다.

클래스 구현에서 IMPLEMENT_SERIAL 매크로를 사용한 경우 삽입 연산자가 `CObject` 보호된 `WriteObject`호출에 대해 오버로드되었습니다. 이 함수는 클래스의 `Serialize` 함수를 호출합니다.

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 삽입 연산자(<<)는 진단 덤프 및 아카이브에 저장을 지원합니다.

### <a name="example"></a>예제

이 예제에서는 **int** `CArchive` 및 **long** 형식의 삽입 연산자 << 사용을 보여 줍니다.

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>예제

이 예제 2에서는 `CArchive` `CStringT` 형식과 삽입 연산자 << 사용을 보여 줍니다.

[!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]

## <a name="carchiveoperator-gtgt"></a><a name="operator_gt_gt"></a>C보관::연산자&gt;&gt;

표시된 개체 또는 기본 형식을 아카이브에서 로드합니다.

```
friend CArchive& operator>>(
    CArchive& ar,
    CObject *& pOb);

throw(
    CArchiveException*,
    CFileException*,
    CMemoryException*);

friend CArchive& operator>>(
    CArchive& ar,
    const CObject *& pOb);

throw(
    CArchiveException*,
    CFileException*,
    CMemoryException*);

CArchive& AFXAPI operator>>(
    CArchive& ar,
    const RECT& rect);

CArchive& AFXAPI operator>>(
    CArchive& ar,
    POINT point);

CArchive& AFXAPI operator>>(
    CArchive& ar,
    SIZE size);

template<typename BaseType,
    class StringTraits> CArchive& operator>>(
    ATL::CStringT<BaseType,
    StringTraits>& str);

CArchive& operator>>(BYTE& by);
CArchive& operator>>(WORD& w);
CArchive& operator>>(int& i);
CArchive& operator>>(LONG& l);
CArchive& operator>>(DWORD& dw);
CArchive& operator>>(float& f);
CArchive& operator>>(double& d);
CArchive& operator>>(short& w);
CArchive& operator>>(char& ch);
CArchive& operator>>(wchar_t& ch);
CArchive& operator>>(unsigned& u);
CArchive& operator>>(bool& b);
CArchive& operator>>(ULONGLONG& dwdw);
CArchive& operator>>(LONGLONG& dwdw);
```

### <a name="return-value"></a>Return Value

한 `CArchive` 줄에 여러 추출 연산자가 사용할 수 있는 참조입니다.

### <a name="remarks"></a>설명

위의 마지막 두 버전은 특히 64비트 정수 로드를 위한 것입니다.

클래스 구현에서 IMPLEMENT_SERIAL 매크로를 사용한 경우 추출 연산자는 `CObject` 보호된 `ReadObject` 함수를 호출하기 위해 오버로드됩니다(영해가 아닌 런타임 클래스 포인터). 이 함수는 클래스의 `Serialize` 함수를 호출합니다.

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 추출 연산자(>>)는 아카이브에서 로드를 지원합니다.

### <a name="example"></a>예제

이 예제에서는 **int** `CArchive` 형식과 >> 추출 연산자의 사용을 보여 줍니다.

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>예제

이 예제에서는 <`CArchive` \< 삽입 및 추출 연산자의 사용을 보여 `CStringT` 주며 형식과 >> .

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

## <a name="carchiveread"></a><a name="read"></a>C아카이브::읽기

아카이브에서 지정된 바이트 수를 읽습니다.

```
UINT Read(void* lpBuf, UINT nMax);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
아카이브에서 읽은 데이터를 수신하는 사용자 제공 버퍼에 대한 포인터입니다.

*nMax*<br/>
아카이브에서 읽을 바이트 수를 지정하는 서명되지 않은 정수입니다.

### <a name="return-value"></a>Return Value

실제로 읽은 바이트 수를 포함하는 서명되지 않은 정수입니다. 반환 값이 요청된 수보다 적으면 파일의 끝에 도달한 것입니다. 파일 끝 조건에도 예외가 throw되지 않습니다.

### <a name="remarks"></a>설명

아카이브는 바이트를 해석하지 않습니다.

개체에 `Read` 포함된 일반 구조를 `Serialize` 읽기 위해 함수 내에서 멤버 함수를 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

## <a name="carchivereadclass"></a><a name="readclass"></a>C아카이브::읽기 클래스

이 멤버 함수를 호출하여 [WriteClass](#writeclass)에 이전에 저장된 클래스에 대한 참조를 읽습니다.

```
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,
    UINT* pSchema = NULL,
    DWORD* pObTag = NULL);
```

### <a name="parameters"></a>매개 변수

*pClassRefRequested*<br/>
요청한 클래스 참조에 해당하는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조에 대한 포인터입니다. NULL일 수 있습니다.

*pSchema*<br/>
이전에 저장된 런타임 클래스의 스키마에 대한 포인터입니다.

*pObTag*<br/>
개체의 고유한 태그를 참조하는 숫자입니다. [ReadObject](#readobject)의 구현에 의해 내부적으로 사용됩니다. 고급 프로그래밍에만 노출됩니다. *pObTag는* 일반적으로 NULL이어야 합니다.

### <a name="return-value"></a>Return Value

[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

*pClassRefRequested가* NULL이 `ReadClass` 아닌 경우 보관된 클래스 정보가 런타임 클래스와 호환되는지 확인합니다. 호환되지 않는 경우 `ReadClass` [CArchiveException을](../../mfc/reference/carchiveexception-class.md)throw합니다.

런타임 클래스는 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)사용해야 합니다. 그렇지 `ReadClass` 않으면 [CNotSupported예외를](../../mfc/reference/cnotsupportedexception-class.md)throw합니다.

*pSchema가* NULL이면 저장된 클래스의 스키마를 [CArchive::GetObjectSchema를](#getobjectschema)호출하여 검색할 수 있습니다. <strong>\*</strong>그렇지 않으면 *pSchema이전에* 저장되었던 런타임 클래스의 스키마를 포함합니다.

클래스 참조의 읽기 및 쓰기를 모두 처리 하는 `ReadClass` 대신 [SerializeClass](#serializeclass)를 사용할 수 있습니다.

### <a name="example"></a>예제

  [CArchive::WriteClass](#writeclass)에 대한 예제를 참조하십시오.

## <a name="carchivereadobject"></a><a name="readobject"></a>C아카이브::읽기 개체

아카이브에서 개체 데이터를 읽고 적절한 형식의 개체를 생성합니다.

```
CObject* ReadObject(const CRuntimeClass* pClass);
```

### <a name="parameters"></a>매개 변수

*pClass*<br/>
읽을 것으로 예상되는 개체에 해당하는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조에 대한 상수 포인터입니다.

### <a name="return-value"></a>Return Value

[CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)를 사용하여 올바른 파생 클래스로 안전하게 캐스팅해야 하는 [CObject](../../mfc/reference/cobject-class.md) 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 `CArchive` **>>** [CObject](../../mfc/reference/cobject-class.md) 포인터에 대해 오버로드된 추출() 연산자에서 호출됩니다. `ReadObject`을 차례로 보관된 `Serialize` 클래스의 함수를 호출합니다.

[RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) 매크로에서 가져오는 비영점 *pClass* 매개 변수를 제공하는 경우 함수는 보관된 개체의 런타임 클래스를 확인합니다. 이는 클래스의 구현에서 IMPLEMENT_SERIAL 매크로를 사용했다고 가정합니다.

### <a name="example"></a>예제

  [CArchive::WriteObject](#writeobject)에 대한 예제를 참조하십시오.

## <a name="carchivereadstring"></a><a name="readstring"></a>C아카이브::읽기 문자열

`CArchive` 이 멤버 함수를 호출하여 개체와 연결된 파일에서 텍스트 데이터를 버퍼로 읽습니다.

```
BOOL ReadString(CString& rString);
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```

### <a name="parameters"></a>매개 변수

*rString*<br/>
CArchive 개체와 연결된 파일에서 읽은 후 결과 문자열을 포함하는 [CString에](../../atl-mfc-shared/reference/cstringt-class.md) 대한 참조입니다.

*lpsz*<br/>
null 종료된 텍스트 문자열을 수신할 사용자 제공 버퍼에 대한 포인터를 지정합니다.

*nMax*<br/>
읽을 최대 문자 수를 지정합니다. *lpsz* 버퍼의 크기보다 작아야 합니다.

### <a name="return-value"></a>Return Value

BOOL을 반환 하는 버전에서, TRUE 성공 하는 경우; 그렇지 않으면 거짓.

`LPTSTR`를 반환 하는 버전에서 텍스트 데이터를 포함 하는 버퍼에 대 한 포인터; 파일 끝에 도달하면 NULL입니다.

### <a name="remarks"></a>설명

*nMax* 매개 변수가 있는 멤버 함수 버전에서 버퍼는 *nMax* - 1 문자의 한계까지 유지됩니다. 캐리지 리턴 라인 피드 쌍에 의해 판독이 중지됩니다. 후행 줄 바호 문자는 항상 제거됩니다. null 문자('\0')는 두 경우 모두 추가됩니다.

[CArchive::Read는](#read) 텍스트 모드 입력에도 사용할 수 있지만 캐리지 리턴 라인 피드 쌍에서는 종료되지 않습니다.

### <a name="example"></a>예제

  [CArchive::WriteString](#writestring)에 대한 예제를 참조하십시오.

## <a name="carchiveserializeclass"></a><a name="serializeclass"></a>C아카이브::직렬화클래스

기본 클래스의 버전 정보를 저장하고 로드하려는 경우 이 멤버 함수를 호출합니다.

```cpp
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>매개 변수

*pClassRef*<br/>
기본 클래스에 대한 런타임 클래스 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

`SerializeClass`의 방향에 `CArchive`따라 클래스에 `CArchive` 대한 참조를 읽거나 개체에 씁니다. `SerializeClass` [ReadClass](#readclass) 및 [WriteClass](#writeclass) 대신 기본 클래스 개체를 직렬화하는 편리한 방법으로 사용합니다. `SerializeClass` 더 적은 코드와 적은 매개 변수가 필요합니다.

와 `ReadClass` `SerializeClass` 같은 것은 보관된 클래스 정보가 런타임 클래스와 호환되는지 확인합니다. 호환되지 않는 경우 `SerializeClass` [CArchiveException을](../../mfc/reference/carchiveexception-class.md)throw합니다.

런타임 클래스는 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)사용해야 합니다. 그렇지 `SerializeClass` 않으면 [CNotSupported예외를](../../mfc/reference/cnotsupportedexception-class.md)throw합니다.

[RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) 매크로를 사용하여 *pRuntimeClass* 매개 변수에 대한 값을 검색합니다. 기본 클래스는 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로를 사용했어야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

## <a name="carchivesetloadparams"></a><a name="setloadparams"></a>C 아카이브 ::설정로드파라름

아카이브에서 많은 수의 `SetLoadParams` `CObject`-파생 개체를 읽으려고 할 때 호출합니다.

```cpp
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>매개 변수

*nGrowBy*<br/>
크기 증가가 필요한 경우 할당할 요소 슬롯의 최소 수입니다.

### <a name="remarks"></a>설명

`CArchive`은 로드 배열을 사용하여 아카이브에 저장된 개체에 대한 참조를 확인합니다. `SetLoadParams`을 사용하면 로드 배열이 증가하는 크기를 설정할 수 있습니다.

개체가 로드된 후 또는 `SetLoadParams` [MapObject](#mapobject) 또는 [ReadObject가](#readobject) 호출된 후 호출해서는 안 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

## <a name="carchivesetobjectschema"></a><a name="setobjectschema"></a>C아카이브::세트오브젝트스키마

이 멤버 함수를 호출하여 아카이브 개체에 저장된 개체 스키마를 *nSchema로*설정합니다.

```cpp
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>매개 변수

*nSchema*<br/>
개체의 스키마를 지정합니다.

### <a name="remarks"></a>설명

[GetObjectSchema에](#getobjectschema) 대한 다음 호출은 *nSchema에*저장된 값을 반환합니다.

고급 `SetObjectSchema` 버전 링밍에 사용; 예를 들어 파생 클래스의 `Serialize` 함수에서 특정 버전을 강제로 읽으려는 경우입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

## <a name="carchivesetstoreparams"></a><a name="setstoreparams"></a>C아카이브::세트스토어파라름

많은 `SetStoreParams` 수의 `CObject`-파생 개체를 아카이브에 저장할 때 사용합니다.

```cpp
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>매개 변수

*nHashSize*<br/>
인터페이스 포인터 맵에 대한 해시 테이블의 크기입니다. 소수여야 합니다.

*nBlockSize*<br/>
매개 변수를 확장하기 위한 메모리 할당 세분성을 지정합니다. 최상의 성능을 위해 2의 힘이어야합니다.

### <a name="remarks"></a>설명

`SetStoreParams`을 사용하면 직렬화 프로세스 중에 고유한 개체를 식별하는 데 사용되는 맵의 해시 테이블 크기와 블록 크기를 설정할 수 있습니다.

개체가 저장된 `SetStoreParams` 후 또는 [MapObject](#mapobject) 또는 [WriteObject가](#writeobject) 호출된 후 호출해서는 안 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

## <a name="carchivewrite"></a><a name="write"></a>C아카이브::쓰기

지정된 수의 바이트를 아카이브에 씁니다.

```cpp
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
아카이브에 기록할 데이터를 포함하는 사용자 제공 버퍼에 대한 포인터입니다.

*nMax*<br/>
아카이브에 기록할 바이트 수를 지정하는 정수입니다.

### <a name="remarks"></a>설명

아카이브는 바이트의 서식을 지정하지 않습니다.

함수 내의 `Write` 멤버 함수를 사용하여 개체에 포함된 일반 구조를 작성할 수 있습니다. `Serialize`

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

## <a name="carchivewriteclass"></a><a name="writeclass"></a>C아카이브::쓰기 클래스

파생 `WriteClass` 클래스를 직렬화하는 동안 기본 클래스의 버전 및 클래스 정보를 저장하는 데 사용합니다.

```cpp
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>매개 변수

*pClassRef*<br/>
요청한 클래스 참조에 해당하는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

`WriteClass`에 기본 클래스에 대 한 [CRuntimeClass에](../../mfc/reference/cruntimeclass-structure.md) 대 한 참조를 `CArchive`씁니다. [CArchive::ReadClass를](#readclass) 사용하여 참조를 검색합니다.

`WriteClass`보관된 클래스 정보가 런타임 클래스와 호환되는지 확인합니다. 호환되지 않는 경우 `WriteClass` [CArchiveException을](../../mfc/reference/carchiveexception-class.md)throw합니다.

런타임 클래스는 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)사용해야 합니다. 그렇지 `WriteClass` 않으면 [CNotSupported예외를](../../mfc/reference/cnotsupportedexception-class.md)throw합니다.

클래스 참조의 읽기 및 쓰기를 모두 처리 하는 `WriteClass` 대신 [SerializeClass](#serializeclass)를 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

## <a name="carchivewriteobject"></a><a name="writeobject"></a>C아카이브::쓰기 개체

지정된 `CObject` 것을 아카이브에 저장합니다.

```cpp
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>매개 변수

*pOb*<br/>
저장 중인 개체에 대한 상수 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 `CArchive` 삽입 () **<<** 연산자 `CObject`에 대해 오버로드하여 호출됩니다. `WriteObject`을 차례로 보관된 `Serialize` 클래스의 함수를 호출합니다.

보관을 사용하려면 IMPLEMENT_SERIAL 매크로를 사용해야 합니다. `WriteObject`ASCII 클래스 이름을 아카이브에 씁니다. 이 클래스 이름은 로드 프로세스 중에 나중에 유효성을 검사합니다. 특수 인코딩 구성표는 클래스의 여러 개체에 대한 클래스 이름의 불필요한 중복을 방지합니다. 또한 이 스키마는 둘 이상의 포인터의 대상인 개체의 중복 저장소를 방지합니다.

정확한 개체 인코딩 방법(ASCII 클래스 이름의 존재 포함)은 구현 세부 정보이며 라이브러리의 이후 버전에서 변경될 수 있습니다.

> [!NOTE]
> 모든 객체를 보관하기 전에 모든 객체를 만들고 삭제하고 업데이트합니다. 보관을 개체 수정과 혼합하면 아카이브가 손상됩니다.

### <a name="example"></a>예제

클래스의 `CAge`정의에 대 한 [CObList::CObList에](../../mfc/reference/coblist-class.md#coblist)대 한 예제를 참조 합니다.

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

## <a name="carchivewritestring"></a><a name="writestring"></a>C아카이브::쓰기 스트링

이 멤버 함수를 사용하여 버퍼의 데이터를 개체와 `CArchive` 연결된 파일에 기록합니다.

```cpp
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>매개 변수

*lpsz*<br/>
null 종료된 텍스트 문자열을 포함하는 버퍼에 대한 포인터를 지정합니다.

### <a name="remarks"></a>설명

null 문자('\0')를 종료하는 문자는 파일에 기록되지 않습니다. 또한 줄 바선이 자동으로 작성되지 않습니다.

`WriteString`디스크 전체 조건을 포함한 여러 조건에 대한 응답으로 예외를 throw합니다.

`Write`사용할 수 있지만 null 문자를 종료하는 대신 요청된 바이트 수를 파일에 씁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[C소켓 클래스](../../mfc/reference/csocket-class.md)<br/>
[C소켓 파일 클래스](../../mfc/reference/csocketfile-class.md)
