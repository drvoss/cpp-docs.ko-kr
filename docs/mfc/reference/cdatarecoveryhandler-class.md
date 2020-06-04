---
title: CData리커버리핸들러 클래스
ms.date: 03/27/2019
f1_keywords:
- CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveAllDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::CreateDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAllAutosavedFiles
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAutosavedFile
- AFXDATARECOVERY/CDataRecoveryHandler::GenerateAutosaveFileName
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::GetDocumentListName
- AFXDATARECOVERY/CDataRecoveryHandler::GetNormalDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRecoveredDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::GetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::Initialize
- AFXDATARECOVERY/CDataRecoveryHandler::QueryRestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::ReadOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::RemoveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::ReopenPreviousDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::RestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::SaveOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::SetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::SetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::UpdateDocumentInfo
helpviewer_keywords:
- CDataRecoveryHandler [MFC], CDataRecoveryHandler
- CDataRecoveryHandler [MFC], AutosaveAllDocumentInfo
- CDataRecoveryHandler [MFC], AutosaveDocumentInfo
- CDataRecoveryHandler [MFC], CreateDocumentInfo
- CDataRecoveryHandler [MFC], DeleteAllAutosavedFiles
- CDataRecoveryHandler [MFC], DeleteAutosavedFile
- CDataRecoveryHandler [MFC], GenerateAutosaveFileName
- CDataRecoveryHandler [MFC], GetAutosaveInterval
- CDataRecoveryHandler [MFC], GetAutosavePath
- CDataRecoveryHandler [MFC], GetDocumentListName
- CDataRecoveryHandler [MFC], GetNormalDocumentTitle
- CDataRecoveryHandler [MFC], GetRecoveredDocumentTitle
- CDataRecoveryHandler [MFC], GetRestartIdentifier
- CDataRecoveryHandler [MFC], GetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], GetShutdownByRestartManager
- CDataRecoveryHandler [MFC], Initialize
- CDataRecoveryHandler [MFC], QueryRestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], ReadOpenDocumentList
- CDataRecoveryHandler [MFC], RemoveDocumentInfo
- CDataRecoveryHandler [MFC], ReopenPreviousDocuments
- CDataRecoveryHandler [MFC], RestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], SaveOpenDocumentList
- CDataRecoveryHandler [MFC], SetAutosaveInterval
- CDataRecoveryHandler [MFC], SetAutosavePath
- CDataRecoveryHandler [MFC], SetRestartIdentifier
- CDataRecoveryHandler [MFC], SetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], SetShutdownByRestartManager
- CDataRecoveryHandler [MFC], UpdateDocumentInfo
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
ms.openlocfilehash: bdfcbea6c345235358384691388afcdbbd2d0a42
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321941"
---
# <a name="cdatarecoveryhandler-class"></a>CData리커버리핸들러 클래스

응용 `CDataRecoveryHandler` 프로그램이 예기치 않게 종료되면 문서를 자동으로 저장하고 복원합니다.

## <a name="syntax"></a>구문

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[C데이터 복구 처리기::CData 복구 처리기](#cdatarecoveryhandler)|`CDataRecoveryHandler` 개체를 생성합니다.|

### <a name="methods"></a>메서드

|||
|-|-|
|[CData 복구 처리기::자동 저장AllDocumentInfo](#autosavealldocumentinfo)|클래스에 등록된 각 파일을 `CDataRecoveryHandler` 자동으로 저장합니다.|
|[CData 복구 처리기::자동 저장 문서 정보](#autosavedocumentinfo)|지정된 문서를 자동으로 저장합니다.|
|[CData 복구 처리기::문서 정보 만들기](#createdocumentinfo)|열려 있는 문서 목록에 문서를 추가합니다.|
|[CData 복구 처리기::DeleteAllAllsave파일](#deleteallautosavedfiles)|현재 자동 저장된 모든 파일을 삭제합니다.|
|[CData 복구 처리기::DeleteAuto저장파일](#deleteautosavedfile)|지정된 자동 저장된 파일을 삭제합니다.|
|[CData 복구 처리기:생성자동 저장 파일 이름](#generateautosavefilename)|제공된 문서 파일 이름과 연결된 자동 저장 파일의 이름을 생성합니다.|
|[CData 복구 처리기::GetAutosave간격](#getautosaveinterval)|자동 저장 시도 사이의 간격을 반환합니다.|
|[CData 복구 처리기::GetAutosavePath](#getautosavepath)|자동 저장된 파일의 경로를 반환합니다.|
|[CData 복구 처리기::GetDocumentListName](#getdocumentlistname)|개체에서 문서 이름을 `CDocument` 검색합니다.|
|[CData 복구 처리기:일반 문서 제목 가져옵니다.](#getnormaldocumenttitle)|지정된 문서의 일반 제목을 검색합니다.|
|[CData 복구 처리기::복구 된 문서 제목](#getrecovereddocumenttitle)|복구된 문서의 제목을 만들고 반환합니다.|
|[CData 복구 처리기::Get다시 시작 식별자](#getrestartidentifier)|응용 프로그램에 대 한 고유 한 다시 시작 식별자를 검색합니다.|
|[CData 복구 처리기::GetSave문서InfoOnIdle](#getsavedocumentinfoonidle)|현재 `CDataRecoveryHandler` 유휴 루프에서 자동 저장을 수행하는지 여부를 나타냅니다.|
|[CData 복구 처리기::GetShutdownBy다시 시작 관리자](#getshutdownbyrestartmanager)|다시 시작 관리자가 응용 프로그램을 종료했는지 여부를 나타냅니다.|
|[C데이터 복구 처리기:초기화](#initialize)|`CDataRecoveryHandler` 을(를) 초기화합니다.|
|[CData 복구 처리기::쿼리복원자동 저장 문서](#queryrestoreautosaveddocuments)|`CDataRecoveryHandler` 자동 저장한 각 문서에 대해 사용자에게 대화 상자를 표시합니다. 대화 상자는 사용자가 자동 저장된 문서를 복원할지 여부를 결정합니다.|
|[CData 복구 처리기::읽기 열린 문서 목록](#readopendocumentlist)|레지스트리에서 열린 문서 목록을 로드합니다.|
|[CData 복구 처리기::제거 문서정보](#removedocumentinfo)|열려 있는 문서 목록에서 제공된 문서를 제거합니다.|
|[C데이터 복구 처리기::이전 문서 다시 열기](#reopenpreviousdocuments)|이전에 열려 있는 문서를 엽니다.|
|[CData 복구 처리기:복원자동 저장 문서](#restoreautosaveddocuments)|사용자 입력에 따라 자동 저장된 문서를 복원합니다.|
|[CData 복구 처리기::저장 열린 문서 목록](#saveopendocumentlist)|열려 있는 문서의 현재 목록을 Windows 레지스트리에 저장합니다.|
|[CData 복구 처리기::SetAutosave간격](#setautosaveinterval)|자동 저장 주기 사이의 시간을 밀리초 단위로 설정합니다.|
|[CData 복구 처리기::SetAutosavePath](#setautosavepath)|자동 저장된 파일이 저장되는 디렉터리를 설정합니다.|
|[CData 복구 처리기::SetRestart식별자](#setrestartidentifier)|의 이 인스턴스에 대한 고유 다시 `CDataRecoveryHandler`시작 식별자를 설정합니다.|
|[CData 복구 처리기::세트 저장 문서InfoOnIdle](#setsavedocumentinfoonidle)|현재 유휴 주기 동안 열려 있는 문서 정보를 Windows 레지스트리에 `CDataRecoveryHandler` 저장할지 여부를 설정합니다.|
|[CData 복구 처리기::SetShutdownBy 다시 시작 관리자](#setshutdownbyrestartmanager)|응용 프로그램의 이전 종료가 다시 시작 관리자에 의해 발생했는지 여부를 설정합니다.|
|[CData 복구 처리기::업데이트 문서정보](#updatedocumentinfo)|사용자가 문서를 저장했기 때문에 문서에 대한 정보를 업데이트합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|m_bRestoringPreviousOpenDocs|데이터 복구 처리기가 이전에 열린 문서를 다시 열지 여부를 나타냅니다.|
|m_bSaveDocumentInfoOnIdle|데이터 복구 처리기가 다음 유휴 루프에서 문서를 자동으로 저장하는지 여부를 나타냅니다.|
|m_bShutdownByRestartManager|다시 시작 관리자로 인해 응용 프로그램이 종료되는지 여부를 나타냅니다.|
|m_dwRestartManagerSupportFlags|다시 시작 관리자가 응용 프로그램에 제공하는 지원을 나타내는 플래그입니다.|
|m_lstAutosavesToDelete|원본 문서가 닫혔을 때 삭제되지 않은 자동 저장파일 목록입니다. 응용 프로그램이 종료되면 다시 시작 관리자가 파일을 다시 삭제합니다.|
|m_mapDocNameToAutosaveName|자동 저장된 파일 이름에 대한 문서 이름 의 맵입니다.|
|m_mapDocNameToDocumentPtr|[CDocument](../../mfc/reference/cdocument-class.md) 포인터에 대한 문서 이름 의 맵입니다.|
|m_mapDocNameToRestoreBool|자동 저장된 문서를 복원할지 여부를 나타내는 부울 매개변수에 대한 문서 이름 의 맵입니다.|
|m_mapDocumentPtrToDocName|문서 이름에 `CDocument` 대한 포인터의 맵입니다.|
|m_mapDocumentPtrToDocTitle|문서 제목에 `CDocument` 대한 포인터의 맵입니다. 이러한 제목은 파일을 저장하는 데 사용됩니다.|
|m_nAutosaveInterval|자동 저장 사이의 시간(밀리초)입니다.|
|m_nTimerID|자동 저장 타이머의 식별자입니다.|
|m_strAutosavePath|자동 저장된 문서가 저장되는 위치입니다.|
|m_strRestartIdentifier|다시 시작 관리자에 대한 GUID의 문자열 표현입니다.|

## <a name="remarks"></a>설명

다시 시작 관리자는 `CDataRecoveryHandler` 클래스를 사용하여 열려 있는 모든 문서를 추적하고 필요에 따라 자동으로 저장합니다. 자동 저장을 사용하려면 [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle 메서드를](#setsavedocumentinfoonidle) 사용합니다. 이 메서드는 `CDataRecoveryHandler` 다음 유휴 루프에서 자동 저장을 수행 하도록 지시 합니다. 다시 시작 관리자는 `SetSaveDocumentInfoOnIdle` 자동 `CDataRecoveryHandler` 저장을 수행해야 하는 경우 호출합니다.

클래스의 모든 메서드는 `CDataRecoveryHandler` 가상입니다. 사용자 지정 데이터 복구 처리기를 만들려면 이 클래스의 메서드를 재정의합니다. 사용자 고유의 데이터 복구 처리기를 만들거나 관리자를 다시 시작하지 않는 한 CDataRecoveryHandler를 인스턴스화하지 마십시오. [CWinApp 클래스는](../../mfc/reference/cwinapp-class.md) `CDataRecoveryHandler` 필요에 따라 개체를 만듭니다.

개체를 `CDataRecoveryHandler` 사용하려면 먼저 [CDataRecoveryHandler::초기화를](#initialize)호출해야 합니다.

클래스는 다시 시작 관리자에 밀접하게 `CDataRecoveryHandler` 연결되어 있기 때문에 `m_dwRestartManagerSupportFlags`전역 매개 변수에 따라 다릅니다. `CDataRecoveryHandler` 이 매개 변수는 다시 시작 관리자가 가진 권한과 응용 프로그램과 상호 작용하는 방법을 결정합니다. 다시 시작 관리자를 기존 응용 프로그램에 통합하려면 주 `m_dwRestartManagerSupportFlags` 응용 프로그램의 생성자에서 적절한 값을 할당해야 합니다. 다시 시작 관리자를 사용하는 방법에 대한 자세한 내용은 관리자 [지원 다시 시작 을 추가하는 방법을](../../mfc/how-to-add-restart-manager-support.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** afxdatarecovery.h

## <a name="cdatarecoveryhandlerautosavealldocumentinfo"></a><a name="autosavealldocumentinfo"></a>CData 복구 처리기::자동 저장AllDocumentInfo

클래스에 등록된 각 파일을 `CDataRecoveryHandler` 자동으로 저장합니다.

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>Return Value

TRUE 모든 `CDataRecoveryHandler` 문서를 저장한 경우; 문서가 저장되지 않은 경우 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 저장 해야 하는 문서가 없는 경우 TRUE를 반환 합니다. 또한 응용 프로그램 `CWinApp` 검색 또는 `CDocManager` 오류 발생 하는 경우 문서를 저장 하지 않고 TRUE를 반환 합니다.

이 메서드를 사용하려면 AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART 또는 AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL `m_dwRestartManagerSupportFlags`에서 설정해야 합니다. 자세한 내용은 [받는 방법: 관리자 지원 다시 시작 을 추가](../../mfc/how-to-add-restart-manager-support.md)참조 하십시오.

## <a name="cdatarecoveryhandlerautosavedocumentinfo"></a><a name="autosavedocumentinfo"></a>CData 복구 처리기::자동 저장 문서 정보

지정된 문서를 자동으로 저장합니다.

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*p문서*|【인】 저장할 포인터입니다. `CDocument`|
|*bReset수정플래그*|【인】 TRUE는 `CDataRecoveryHandler` *pDocument를* 수정할 것을 고려한다는 것을 나타냅니다. FALSE는 프레임워크가 *pDocument를* 수정되지 않은 것으로 간주한다는 것을 나타냅니다. 이 플래그의 효과에 대한 자세한 내용은 비고 섹션을 참조하십시오.|

### <a name="return-value"></a>Return Value

TRUE 는 적절한 플래그가 설정되어 있고 `CDocument` *pDocument가* 유효한 개체인 경우

### <a name="remarks"></a>설명

각 `CDocument` 개체에는 마지막 저장 이후 변경되었는지 나타내는 플래그가 있습니다. [CDocument::IsModified를](../../mfc/reference/cdocument-class.md#ismodified) 사용하여 이 플래그의 상태를 확인합니다. 마지막 `CDocument` 저장 이후 a가 변경되지 `AutosaveDocumentInfo` 않은 경우 해당 문서에 대해 자동으로 저장된 파일을 삭제합니다. 마지막 저장 이후 문서가 변경된 경우 문서를 닫으면 닫기 전에 문서를 저장하라는 메시지가 표시됩니다.

> [!NOTE]
> *bResetModifiedFlag를* 사용하여 문서의 상태를 수정되지 않은 상태로 변경하면 사용자가 저장되지 않은 데이터가 손실될 수 있습니다. 프레임워크에서 수정되지 않은 문서를 고려하는 경우 문서를 닫으면 사용자에게 저장하라는 메시지가 표시되지 않습니다.

이 메서드는 *pDocument가* 유효한 `CDocument` 개체가 아닌 경우 [ASSERT](diagnostic-services.md#assert) 매크로에 대한 예외를 throw합니다.

이 메서드를 사용하려면 AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART 또는 AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL *m_dwRestartManagerSupportFlags*설정해야 합니다.

## <a name="cdatarecoveryhandlercdatarecoveryhandler"></a><a name="cdatarecoveryhandler"></a>C데이터 복구 처리기::CData 복구 처리기

`CDataRecoveryHandler` 개체를 생성합니다.

```
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,
    int nAutosaveInterval);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*dwRestart관리자지원플래그*|【인】 다시 시작 관리자의 옵션이 지원되는 옵션을 나타냅니다.|
|*n자동 저장 간격*|【인】 자동 저장 사이의 시간입니다. 이 매개 변수는 밀리초 단위입니다.|

### <a name="remarks"></a>설명

새 `CDataRecoveryHandler` **프로젝트** 마법사를 사용할 때 MFC 프레임워크는 응용 프로그램에 대한 개체를 자동으로 만듭니다. 데이터 복구 동작이나 다시 시작 관리자를 사용자 지정하지 않는 `CDataRecoveryHandler` 한 개체를 만들 수 없습니다.

## <a name="cdatarecoveryhandlercreatedocumentinfo"></a><a name="createdocumentinfo"></a>CData 복구 처리기::문서 정보 만들기

열려 있는 문서 목록에 문서를 추가합니다.

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*p문서*|【인】 에 대한 `CDocument`포인터입니다. 이 메서드는 이 `CDocument`에 대한 문서 정보를 만듭니다.|

### <a name="return-value"></a>Return Value

기본 구현은 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 문서를 추가하기 전에 *pDocument가* 문서 목록에 이미 있는지 확인합니다. *pDocument가* 목록에 이미 있는 경우 이 메서드는 *pDocument*와 연결된 자동 저장 파일을 삭제합니다.

이 메서드를 사용하려면 AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART 또는 AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL *m_dwRestartManagerSupportFlags*설정해야 합니다.

## <a name="cdatarecoveryhandlerdeleteallautosavedfiles"></a><a name="deleteallautosavedfiles"></a>CData 복구 처리기::DeleteAllAllsave파일

현재 자동 저장된 모든 파일을 삭제합니다.

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>Return Value

기본 구현은 항상 TRUE를 반환합니다.

## <a name="cdatarecoveryhandlerdeleteautosavedfile"></a><a name="deleteautosavedfile"></a>CData 복구 처리기::DeleteAuto저장파일

지정된 자동 저장된 파일을 삭제합니다.

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*str자동 저장 파일*|【인】 자동 저장된 파일 이름이 포함된 문자열입니다.|

### <a name="return-value"></a>Return Value

기본 구현은 항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 메서드가 자동 저장된 파일을 삭제할 수 없는 경우 파일의 이름을 목록에 저장합니다. 해당 목록에 지정된 각 `CDataRecoveryHandler` 자동 저장 파일을 삭제하려고 시도하는 소멸자입니다.

## <a name="cdatarecoveryhandlergenerateautosavefilename"></a><a name="generateautosavefilename"></a>CData 복구 처리기:생성자동 저장 파일 이름

제공된 문서 파일 이름과 연결된 자동 저장 파일의 이름을 생성합니다.

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>매개 변수

*strDocument 이름*<br/>
【인】 문서 이름이 포함된 문자열입니다. `GenerateAutosaveFileName`는 이 문서 이름을 사용하여 해당 자동 저장 파일 이름을 생성합니다.

### <a name="return-value"></a>Return Value

*strDocumentName*에서 생성된 파일 이름 자동 저장 .

### <a name="remarks"></a>설명

각 문서 이름에는 자동 저장 파일 이름이 있는 일대일 매핑이 있습니다.

## <a name="cdatarecoveryhandlergetautosaveinterval"></a><a name="getautosaveinterval"></a>CData 복구 처리기::GetAutosave간격

자동 저장 시도 사이의 간격을 반환합니다.

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>Return Value

자동 저장 시도 사이의 밀리초 수입니다.

## <a name="cdatarecoveryhandlergetautosavepath"></a><a name="getautosavepath"></a>CData 복구 처리기::GetAutosavePath

자동 저장된 파일의 경로를 반환합니다.

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>Return Value

자동 저장된 문서가 저장되는 위치입니다.

## <a name="cdatarecoveryhandlergetdocumentlistname"></a><a name="getdocumentlistname"></a>CData 복구 처리기::GetDocumentListName

개체에서 문서 이름을 `CDocument` 검색합니다.

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*p문서*|【인】 에 대한 `CDocument`포인터입니다. `GetDocumentListName`에서 문서 이름을 `CDocument`검색합니다.|

### <a name="return-value"></a>Return Value

*pDocument의*문서 이름 .

### <a name="remarks"></a>설명

은 `CDataRecoveryHandler` 문서 이름을 *m_mapDocNameToAutosaveName,* *m_mapDocNameToDocumentPtr*및 *m_mapDocNameToRestoreBool*의 키로 사용합니다. 이러한 매개 `CDataRecoveryHandler` 변수를 `CDocument` 사용하면 개체, 자동 저장 파일 이름 및 자동 저장 설정을 모니터링할 수 있습니다.

## <a name="cdatarecoveryhandlergetnormaldocumenttitle"></a><a name="getnormaldocumenttitle"></a>CData 복구 처리기:일반 문서 제목 가져옵니다.

지정된 문서의 일반 제목을 검색합니다.

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*p문서*|【인】 에 대한 `CDocument`포인터입니다.|

### <a name="return-value"></a>Return Value

지정된 문서의 일반 제목입니다.

### <a name="remarks"></a>설명

문서의 일반 제목은 일반적으로 경로가 없는 문서의 파일 이름입니다. 이 제목은 저장 대화 상자의 **파일 이름** 필드의 **제목입니다.**

## <a name="cdatarecoveryhandlergetrecovereddocumenttitle"></a><a name="getrecovereddocumenttitle"></a>CData 복구 처리기::복구 된 문서 제목

복구된 문서의 제목을 만들고 반환합니다.

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>매개 변수

*스트라이멘트 제목*<br/>
【인】 문서의 일반 제목입니다.

### <a name="return-value"></a>Return Value

복구된 문서 제목입니다.

### <a name="remarks"></a>설명

기본적으로 문서의 복구된 제목은 **[복구됨]이** 추가된 일반 제목입니다. 복구된 제목은 사용자가 자동 저장된 `CDataRecoveryHandler` 문서를 복원하도록 쿼리할 때 사용자에게 표시됩니다.

## <a name="cdatarecoveryhandlergetrestartidentifier"></a><a name="getrestartidentifier"></a>CData 복구 처리기::Get다시 시작 식별자

응용 프로그램에 대 한 고유 한 다시 시작 식별자를 검색합니다.

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>Return Value

고유한 다시 시작 식별자입니다.

### <a name="remarks"></a>설명

다시 시작 식별자는 응용 프로그램의 각 실행에 대해 고유합니다.

현재 `CDataRecoveryHandler` 열려 있는 문서에 대한 정보를 레지스트리에 저장합니다. 다시 시작 관리자가 응용 프로그램을 종료하고 다시 시작하면 다시 시작 식별자를 `CDataRecoveryHandler`에 제공합니다. 는 `CDataRecoveryHandler` 다시 시작 식별자를 사용하여 이전에 열려 있는 문서 목록을 검색합니다. 이렇게 하면 `CDataRecoveryHandler` 자동 저장된 파일을 찾고 복원할 수 있습니다.

## <a name="cdatarecoveryhandlergetsavedocumentinfoonidle"></a><a name="getsavedocumentinfoonidle"></a>CData 복구 처리기::GetSave문서InfoOnIdle

현재 `CDataRecoveryHandler` 유휴 루프에서 자동 저장을 수행하는지 여부를 나타냅니다.

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>Return Value

TRUE는 `CDataRecoveryHandler` 현재 유휴 루프에서 자동 저장을 나타냅니다. FALSE는 그렇지 않음을 나타냅니다.

## <a name="cdatarecoveryhandlergetshutdownbyrestartmanager"></a><a name="getshutdownbyrestartmanager"></a>CData 복구 처리기::GetShutdownBy다시 시작 관리자

다시 시작 관리자가 응용 프로그램을 종료했는지 여부를 나타냅니다.

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>Return Value

TRUE는 다시 시작 관리자가 응용 프로그램을 종료했음을 나타냅니다. FALSE는 그렇지 않음을 나타냅니다.

## <a name="cdatarecoveryhandlerinitialize"></a><a name="initialize"></a>C데이터 복구 처리기:초기화

`CDataRecoveryHandler` 을(를) 초기화합니다.

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>Return Value

TRUE 초기화가 성공하면 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

초기화 프로세스는 레지스트리에서 자동 저장 파일을 저장하기 위한 경로를 로드합니다. 메서드가 `Initialize` 이 디렉터리를 찾을 수 없거나 경로가 NULL인 경우 `Initialize` 실패하고 반환합니다. `FALSE`

[CDataRecoveryHandler::SetAutosavePath를](#setautosavepath) 사용하여 응용 프로그램이 `CDataRecoveryHandler`을 초기화한 후 자동 저장 경로를 변경합니다.

또한 `Initialize` 메서드는 다음 자동 저장이 발생할 때 모니터링 하는 타이머를 시작 합니다. [CDataRecoveryHandler::Set자동 저장 간격을](#setautosaveinterval) 사용하여 응용 프로그램이 을 초기화한 후 자동 저장 간격을 `CDataRecoveryHandler`변경합니다.

## <a name="cdatarecoveryhandlerqueryrestoreautosaveddocuments"></a><a name="queryrestoreautosaveddocuments"></a>CData 복구 처리기::쿼리복원자동 저장 문서

`CDataRecoveryHandler` 자동 저장한 각 문서에 대해 사용자에게 대화 상자를 표시합니다. 대화 상자는 사용자가 자동 저장된 문서를 복원할지 여부를 결정합니다.

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>설명

응용 프로그램이 유니코드인 경우 이 메서드는 사용자에게 [CTaskDialog를](../../mfc/reference/ctaskdialog-class.md) 표시합니다. 그렇지 않으면 프레임워크에서 [AfxMessageBox를](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) 사용하여 사용자를 쿼리합니다.

사용자로부터 모든 응답을 수집한 후 `QueryRestoreAutosavedDocuments` *m_mapDocNameToRestoreBool*멤버 변수에 정보를 저장합니다. 이 메서드는 자동 저장 된 문서를 복원 하지 않습니다.

## <a name="cdatarecoveryhandlerreadopendocumentlist"></a><a name="readopendocumentlist"></a>CData 복구 처리기::읽기 열린 문서 목록

레지스트리에서 열린 문서 목록을 로드합니다.

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>Return Value

TRUE는 `ReadOpenDocumentList` 레지스트리에서 하나 이상의 문서에 대한 정보를 로드했음을 나타냅니다. FALSE는 문서 정보가 로드되지 않은 것을 나타냅니다.

### <a name="remarks"></a>설명

이 함수는 레지스트리에서 열린 문서 정보를 로드하고 *m_mapDocNameToAutosaveName*멤버 변수에 저장합니다.

모든 `ReadOpenDocumentList` 데이터를 로드하면 레지스트리에서 문서 정보가 삭제됩니다.

## <a name="cdatarecoveryhandlerremovedocumentinfo"></a><a name="removedocumentinfo"></a>CData 복구 처리기::제거 문서정보

열려 있는 문서 목록에서 제공된 문서를 제거합니다.

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*p문서*|【인】 제거할 문서에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

*pDocument가* 목록에서 제거된 경우 TRUE입니다. 오류가 발생한 경우 FALSE입니다.

### <a name="remarks"></a>설명

사용자가 문서를 닫으면 프레임워크는 이 메서드를 사용하여 열려 있는 문서 목록에서 문서를 제거합니다.

열려 `RemoveDocumentInfo` 있는 문서 목록에서 *pDocument를* 찾을 수 없는 경우 아무 작업도 수행하지 않으며 TRUE를 반환합니다.

이 메서드를 사용 하려면 *AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES m_dwRestartManagerSupportFlags*설정 해야 합니다.

## <a name="cdatarecoveryhandlerreopenpreviousdocuments"></a><a name="reopenpreviousdocuments"></a>C데이터 복구 처리기::이전 문서 다시 열기

이전에 열려 있는 문서를 엽니다.

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>Return Value

TRUE 문서가 하나 이상 열려 있는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 이전에 열려 있는 문서의 가장 최근 저장을 엽니다. 문서가 저장되지 않았거나 자동 저장되지 않은 경우 해당 파일 형식의 템플릿을 기반으로 빈 문서를 `ReopenPreviousDocuments` 엽니다.

이 메서드를 사용 하려면 *AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES m_dwRestartManagerSupportFlags*설정 해야 합니다. 이 매개 변수가 `ReopenPreviousDocuments` 설정되지 않은 경우 아무 것도 수행하지 않고 FALSE를 반환합니다.

이전에 열려 있는 문서 목록에 저장된 문서가 `ReopenPreviousDocuments` 없는 경우 아무 것도 수행하지 않고 FALSE를 반환합니다.

## <a name="cdatarecoveryhandlerrestoreautosaveddocuments"></a><a name="restoreautosaveddocuments"></a>CData 복구 처리기:복원자동 저장 문서

사용자 입력에 따라 자동 저장된 문서를 복원합니다.

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>Return Value

이 메서드가 문서를 성공적으로 복원하는 경우 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드는 [CDataRecoveryHandler::QueryRestoreAutosaved문서](#queryrestoreautosaveddocuments) 호출 사용자가 복원 하려는 문서를 결정 합니다. 사용자가 자동 저장된 문서를 복원하지 않기로 `RestoreAutosavedDocuments` 결정하면 자동 저장 파일을 삭제합니다. 그렇지 `RestoreAutosavedDocuments` 않으면 열려 있는 문서를 자동 저장 버전으로 바꿉습니다.

이 메서드를 사용하려면 AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES 또는 AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES `m_dwRestartManagerSupportFlags`에서 설정해야 합니다.

## <a name="cdatarecoveryhandlersaveopendocumentlist"></a><a name="saveopendocumentlist"></a>CData 복구 처리기::저장 열린 문서 목록

열려 있는 문서의 현재 목록을 Windows 레지스트리에 저장합니다.

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>Return Value

저장할 열린 문서가 없거나 성공적으로 저장된 경우 TRUE입니다. FALSE 레지스트리에 저장할 문서가 있지만 오류가 발생했기 때문에 저장되지 않은 경우 false입니다.

### <a name="remarks"></a>설명

다시 시작 관리자는 `SaveOpenDocumentList` 응용 프로그램이 예기치 않게 종료되거나 업그레이드를 위해 종료될 때 호출합니다. 응용 프로그램이 다시 시작되면 [CDataRecoveryHandler::ReadOpenDocumentList를](#readopendocumentlist) 사용하여 열려 있는 문서 목록을 검색합니다.

이 메서드는 열려 있는 문서 목록만 저장 합니다. 방법 [CDataRecoveryHandler::자동 저장문서Info는](#autosavedocumentinfo) 문서 자체 저장에 대 한 책임.

## <a name="cdatarecoveryhandlersetautosaveinterval"></a><a name="setautosaveinterval"></a>CData 복구 처리기::SetAutosave간격

자동 저장 주기 사이의 시간을 밀리초 단위로 설정합니다.

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>매개 변수

*n자동 저장 간격*<br/>
【인】 밀리초 단위로 새 자동 저장 간격입니다.

## <a name="cdatarecoveryhandlersetautosavepath"></a><a name="setautosavepath"></a>CData 복구 처리기::SetAutosavePath

자동 저장된 파일이 저장되는 디렉터리를 설정합니다.

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*스트라오토세이브패스*|【인】 파일이 자동으로 저장되는 경로입니다.|

### <a name="remarks"></a>설명

자동 저장 디렉토리를 변경해도 현재 자동 저장된 파일은 이동하지 않습니다.

## <a name="cdatarecoveryhandlersetrestartidentifier"></a><a name="setrestartidentifier"></a>CData 복구 처리기::SetRestart식별자

의 이 인스턴스에 대한 고유 다시 `CDataRecoveryHandler`시작 식별자를 설정합니다.

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*strRestart식별자*|【인】 다시 시작 관리자의 고유 식별자입니다.|

### <a name="remarks"></a>설명

다시 시작 관리자는 레지스트리의 열린 문서에 대한 정보를 기록합니다. 이 정보는 고유한 다시 시작 식별자를 키로 저장합니다. 다시 시작 식별자는 응용 프로그램의 각 인스턴스에 대해 고유하므로 응용 프로그램의 여러 인스턴스가 예기치 않게 종료될 수 있으며 다시 시작 관리자는 각 식별자를 복구할 수 있습니다.

## <a name="cdatarecoveryhandlersetsavedocumentinfoonidle"></a><a name="setsavedocumentinfoonidle"></a>CData 복구 처리기::세트 저장 문서InfoOnIdle

현재 유휴 주기 동안 열려 있는 문서 정보를 Windows 레지스트리에 `CDataRecoveryHandler` 저장할지 여부를 설정합니다.

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*bSaveOnIdle*|【인】 현재 유휴 주기 동안 문서 정보를 저장하는 TRUE; FALSE는 저장을 수행하지 않습니다.|

## <a name="cdatarecoveryhandlersetshutdownbyrestartmanager"></a><a name="setshutdownbyrestartmanager"></a>CData 복구 처리기::SetShutdownBy 다시 시작 관리자

응용 프로그램의 이전 종료가 다시 시작 관리자에 의해 발생했는지 여부를 설정합니다.

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*bShutdownBy다시시작관리자*|【인】 TRUE는 다시 시작 관리자가 응용 프로그램을 종료했음을 나타냅니다. FALSE는 응용 프로그램이 다른 이유로 종료되었음을 나타냅니다.|

### <a name="remarks"></a>설명

프레임워크는 이전 종료가 예기치 않은 것인지 또는 다시 시작 관리자에 의해 시작되었는지 여부에 따라 다르게 작동합니다.

## <a name="cdatarecoveryhandlerupdatedocumentinfo"></a><a name="updatedocumentinfo"></a>CData 복구 처리기::업데이트 문서정보

사용자가 문서를 저장했기 때문에 문서에 대한 정보를 업데이트합니다.

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*p문서*|【인】 저장된 문서에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 자동 저장된 문서를 삭제하고 문서 정보를 업데이트한 경우 TRUE입니다. 오류가 발생한 경우 FALSE입니다.

### <a name="remarks"></a>설명

사용자가 문서를 저장하면 응용 프로그램은 더 이상 필요하지 않으므로 자동 저장된 파일을 제거합니다. `UpdateDocumentInfo`[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)를 호출하여 자동 저장된 파일을 삭제합니다. `UpdateDocumentInfo`그런 다음 해당 정보를 삭제하지만 저장된 문서는 `RemoveDocumentInfo` 여전히 열려 있기 때문에 *pDocument의* 정보를 현재 열려 있는 문서 목록에 추가합니다.

이 메서드를 사용 하려면 *AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES m_dwRestartManagerSupportFlags*설정 해야 합니다.

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)
