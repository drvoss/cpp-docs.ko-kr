---
title: "CAtlTemporaryFile 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::Close
- ATLFILE/ATL::CAtlTemporaryFile::Create
- ATLFILE/ATL::CAtlTemporaryFile::Flush
- ATLFILE/ATL::CAtlTemporaryFile::GetPosition
- ATLFILE/ATL::CAtlTemporaryFile::GetSize
- ATLFILE/ATL::CAtlTemporaryFile::HandsOff
- ATLFILE/ATL::CAtlTemporaryFile::HandsOn
- ATLFILE/ATL::CAtlTemporaryFile::LockRange
- ATLFILE/ATL::CAtlTemporaryFile::Read
- ATLFILE/ATL::CAtlTemporaryFile::Seek
- ATLFILE/ATL::CAtlTemporaryFile::SetSize
- ATLFILE/ATL::CAtlTemporaryFile::TempFileName
- ATLFILE/ATL::CAtlTemporaryFile::UnlockRange
- ATLFILE/ATL::CAtlTemporaryFile::Write
dev_langs:
- C++
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5911de856d13d9d66e8c950d446083a36811f535
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile 클래스
이 클래스는 만들고 임시 파일을 사용 하기 위한 메서드를 제공합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAtlTemporaryFile
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|생성자입니다.|  
|[CAtlTemporaryFile:: ~ CAtlTemporaryFile](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlTemporaryFile::Close](#close)|임시 파일을 닫으려면이 메서드를 호출 하 고 해당 콘텐츠를 삭제 하거나 또는 지정 된 파일 이름으로 저장 합니다.|  
|[CAtlTemporaryFile::Create](#create)|임시 파일을 만들려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::Flush](#flush)|임시 파일에 쓸 파일 버퍼에에서 남아 있는 모든 데이터 하려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::GetPosition](#getposition)|현재 파일 포인터 위치를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::GetSize](#getsize)|임시 파일의 바이트에서 크기를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::HandsOff](#handsoff)|파일에이 메서드를 호출 하는 `CAtlTemporaryFile` 개체입니다.|  
|[CAtlTemporaryFile::HandsOn](#handson)|기존 임시 파일을 열고 파일의 끝에 있는 포인터 위치를 지정 하려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::LockRange](#lockrange)|다른 프로세스에 액세스 하지 못하도록 파일에 영역을 잠그려는이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::Read](#read)|파일 포인터에 의해 지정 된 위치에서 시작 하는 임시 파일에서 데이터를 읽는이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::Seek](#seek)|임시 파일의 파일 포인터를 이동 하려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::SetSize](#setsize)|임시 파일의 크기를 설정 하려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::TempFileName](#tempfilename)|임시 파일의 이름을 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|임시 파일의 영역을 잠금 해제 하려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::Write](#write)|파일 포인터에 의해 지정 된 위치에서 시작 하는 임시 파일로 데이터를 기록 하려면이 메서드를 호출 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlTemporaryFile::operator 핸들](#operator_handle)|임시 파일에 대 한 핸들을 반환합니다.|  
  
## <a name="remarks"></a>설명  
 `CAtlTemporaryFile`만들고 임시 파일을 사용 하 여 쉽게 있습니다. 파일은 자동으로 명명 된, 열, 닫히고 삭제 됩니다. 파일 콘텐츠 파일을 닫은 후 필요한 경우 지정된 된 이름 가진 새 파일에 저장할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlfile.h  
  
## <a name="example"></a>예  
 예를 참조 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.  
  
##  <a name="catltemporaryfile"></a>CAtlTemporaryFile::CAtlTemporaryFile  
 생성자입니다.  
  
```
CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>설명  
 호출할 때까지는 파일이 실제로 열려 있지 않으면 [CAtlTemporaryFile::Create](#create)합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlTemporaryFile:: ~ CAtlTemporaryFile  
 소멸자입니다.  
  
```
~CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>설명  
 소멸자 호출 [CAtlTemporaryFile::Close](#close)합니다.  
  
##  <a name="close"></a>CAtlTemporaryFile::Close  
 임시 파일을 닫으려면이 메서드를 호출 하 고 해당 콘텐츠를 삭제 하거나 또는 지정 된 파일 이름으로 저장 합니다.  
  
```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *szNewName*  
 임시 파일의 내용을 저장 하는 새 파일에 대 한 이름입니다. 이 인수가 NULL 이면 임시 파일의 내용이 삭제 됩니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.  
  
##  <a name="create"></a>CAtlTemporaryFile::Create  
 임시 파일을 만들려면이 메서드를 호출 합니다.  
  
```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pszDir`  
 임시 파일에 대 한 경로입니다. NULL 인 경우 [GetTempPath](http://msdn.microsoft.com/library/windows/desktop/aa364992) 경로를 지정할 호출 됩니다.  
  
 `dwDesiredAccess`  
 원하는 액세스 합니다. 참조 `dwDesiredAccess` 에 [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) in the Windows SDK입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.  
  
##  <a name="flush"></a>CAtlTemporaryFile::Flush  
 임시 파일에 쓸 파일 버퍼에에서 남아 있는 모든 데이터 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 비슷한 [CAtlTemporaryFile::HandsOff](#handsoff)한다는 점을 제외 하는 파일 닫혀 있지 않습니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.  
  
##  <a name="getposition"></a>CAtlTemporaryFile::GetPosition  
 현재 파일 포인터 위치를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 바이트 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 파일 포인터 위치를 변경 하려면 [CAtlTemporaryFile::Seek](#seek)합니다.  
  
##  <a name="getsize"></a>CAtlTemporaryFile::GetSize  
 임시 파일의 바이트에서 크기를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nLen`  
 파일의 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
##  <a name="handsoff"></a>CAtlTemporaryFile::HandsOff  
 파일에이 메서드를 호출 하는 `CAtlTemporaryFile` 개체입니다.  
  
```
HRESULT HandsOff() throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 `HandsOff`및 [CAtlTemporaryFile::HandsOn](#handson) 개체에서 파일 및 필요한 경우 다시 연결 하는 데 사용 됩니다. `HandsOff`임시 파일에 쓸 파일 버퍼에에서 남아 있는 모든 데이터를 강제로 되며 다음 파일을 닫습니다. 닫고 파일을 영구적으로 삭제 하려는 경우 또는 이름이 지정 된 파일의 내용을 유지를 사용 하 고 닫고 하려는 경우 [CAtlTemporaryFile::Close](#close)합니다.  
  
##  <a name="handson"></a>CAtlTemporaryFile::HandsOn  
 기존 임시 파일을 열고 파일의 끝에 있는 포인터 위치를 지정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT HandsOn() throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 [CAtlTemporaryFile::HandsOff](#handsoff) 및 `HandsOn` 개체에서 파일 및 필요한 경우 다시 연결 하는 데 사용 됩니다.  
  
##  <a name="lockrange"></a>CAtlTemporaryFile::LockRange  
 다른 프로세스에 액세스 하지 않도록 하려면 임시 파일에 영역을 잠그려는이 메서드를 호출 합니다.  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 잠금을 시작 해야 하는 파일의 위치입니다.  
  
 `nCount`  
 바이트 범위를 잠글 수의 길이입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 파일의 바이트를 잠그면 다른 프로세스에서 해당 바이트에 액세스할 수 없습니다. 파일의 둘 이상의 영역을 잠글 수 있습니다 하지만 겹치는 지역이 없습니다. 허용 됩니다. 성공적으로 잠금 해제는 영역을 사용 하 여 [CAtlTemporaryFile::UnlockRange](#unlockrange), 이전에 잠겨 있는 영역에 정확 하 게 해당 바이트 범위를 확인 합니다. `LockRange`인접 한 영역을 병합 하지 않습니다. 두 개의 잠긴된 영역을 인접 한 경우 잠금을 해제 해야 각각 별도로 합니다.  
  
##  <a name="operator_handle"></a>CAtlTemporaryFile::operator 핸들  
 임시 파일에 대 한 핸들을 반환합니다.  
  
```  
operator HANDLE() throw();
```  
  
##  <a name="read"></a>CAtlTemporaryFile::Read  
 파일 포인터에 의해 지정 된 위치에서 시작 하는 임시 파일에서 데이터를 읽는이 메서드를 호출 합니다.  
  
```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pBuffer`  
 파일에서 읽은 데이터를 받을 버퍼에 대 한 포인터입니다.  
  
 `nBufSize`  
 버퍼 크기(바이트)입니다.  
  
 `nBytesRead`  
 읽은 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [CAtlFile::Read](../../atl/reference/catlfile-class.md#read)합니다. 파일 포인터의 위치를 변경 하려면 호출 [CAtlTemporaryFile::Seek](#seek)합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.  
  
##  <a name="seek"></a>CAtlTemporaryFile::Seek  
 임시 파일의 파일 포인터를 이동 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nOffset`  
 제공한 시작 점에서 바이트 오프셋 *dwFrom 합니다.*  
  
 `dwFrom`  
 시작 지점 (FILE_BEGIN, FILE_CURRENT, 또는 FILE_END)입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek)합니다. 현재 파일 포인터 위치를 가져오려면 호출 [CAtlTemporaryFile::GetPosition](#getposition)합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.  
  
##  <a name="setsize"></a>CAtlTemporaryFile::SetSize  
 임시 파일의 크기를 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nNewLen`  
 바이트에 있는 파일의 새 길이입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize)합니다. 반환 시, 파일 포인터는 파일의 끝에 배치 됩니다.  
  
##  <a name="tempfilename"></a>CAtlTemporaryFile::TempFileName  
 임시 파일의 이름을 반환 하려면이 메서드를 호출 합니다.  
  
```
LPCTSTR TempFileName() throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 된 `LPCTSTR` 파일 이름을 가리키는 합니다.  
  
### <a name="remarks"></a>설명  
 파일 이름이 생성 됩니다 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile) 을 호출 하 여는 [GetTempFile](http://msdn.microsoft.com/library/windows/desktop/aa364991)Windows SDK 함수입니다. 파일 확장명은 항상 "TFR" 임시 파일에 대 한입니다.  
  
##  <a name="unlockrange"></a>CAtlTemporaryFile::UnlockRange  
 임시 파일의 영역을 잠금 해제 하려면이 메서드를 호출 합니다.  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 잠금을 시작 해야 하는 파일의 위치입니다.  
  
 `nCount`  
 잠금 해제할 바이트 범위 길이입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange)합니다.  
  
##  <a name="write"></a>CAtlTemporaryFile::Write  
 파일 포인터에 의해 지정 된 위치에서 시작 하는 임시 파일로 데이터를 기록 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Write(  
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pBuffer`  
 데이터 파일에 쓸 수를 포함 하는 버퍼입니다.  
  
 `nBufSize`  
 버퍼에서 전송할 바이트 수입니다.  
  
 `pnBytesWritten`  
 쓰여진 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [CAtlFile::Write](../../atl/reference/catlfile-class.md#write)합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [CAtlFile 클래스](../../atl/reference/catlfile-class.md)
