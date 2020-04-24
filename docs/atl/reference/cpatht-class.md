---
title: CPathT 클래스
ms.date: 03/27/2019
f1_keywords:
- CPathT
- ATLPATH/ATL::CPathT
- ATLPATH/ATL::CPathT::PCXSTR
- ATLPATH/ATL::CPathT::PXSTR
- ATLPATH/ATL::CPathT::XCHAR
- ATLPATH/ATL::CPathT::CPathT
- ATLPATH/ATL::CPathT::AddBackslash
- ATLPATH/ATL::CPathT::AddExtension
- ATLPATH/ATL::CPathT::Append
- ATLPATH/ATL::CPathT::BuildRoot
- ATLPATH/ATL::CPathT::Canonicalize
- ATLPATH/ATL::CPathT::Combine
- ATLPATH/ATL::CPathT::CommonPrefix
- ATLPATH/ATL::CPathT::CompactPath
- ATLPATH/ATL::CPathT::CompactPathEx
- ATLPATH/ATL::CPathT::FileExists
- ATLPATH/ATL::CPathT::FindExtension
- ATLPATH/ATL::CPathT::FindFileName
- ATLPATH/ATL::CPathT::GetDriveNumber
- ATLPATH/ATL::CPathT::GetExtension
- ATLPATH/ATL::CPathT::IsDirectory
- ATLPATH/ATL::CPathT::IsFileSpec
- ATLPATH/ATL::CPathT::IsPrefix
- ATLPATH/ATL::CPathT::IsRelative
- ATLPATH/ATL::CPathT::IsRoot
- ATLPATH/ATL::CPathT::IsSameRoot
- ATLPATH/ATL::CPathT::IsUNC
- ATLPATH/ATL::CPathT::IsUNCServer
- ATLPATH/ATL::CPathT::IsUNCServerShare
- ATLPATH/ATL::CPathT::MakePretty
- ATLPATH/ATL::CPathT::MatchSpec
- ATLPATH/ATL::CPathT::QuoteSpaces
- ATLPATH/ATL::CPathT::RelativePathTo
- ATLPATH/ATL::CPathT::RemoveArgs
- ATLPATH/ATL::CPathT::RemoveBackslash
- ATLPATH/ATL::CPathT::RemoveBlanks
- ATLPATH/ATL::CPathT::RemoveExtension
- ATLPATH/ATL::CPathT::RemoveFileSpec
- ATLPATH/ATL::CPathT::RenameExtension
- ATLPATH/ATL::CPathT::SkipRoot
- ATLPATH/ATL::CPathT::StripPath
- ATLPATH/ATL::CPathT::StripToRoot
- ATLPATH/ATL::CPathT::UnquoteSpaces
- ATLPATH/ATL::CPathT::m_strPath
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
ms.openlocfilehash: 76273e7fbfa50e610b437e11859821374413d008
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032136"
---
# <a name="cpatht-class"></a>CPathT 클래스

이 클래스는 경로를 나타냅니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>매개 변수

*StringType*<br/>
경로에 사용할 ATL/MFC 문자열 [클래스입니다(CStringT](../../atl-mfc-shared/reference/cstringt-class.md)참조).

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CPathT::PCXSTR](#pcxstr)|상수 문자열 형식입니다.|
|[CPathT::PXSTR](#pxstr)|문자열 유형입니다.|
|[CPathT::XCHAR](#xchar)|문자 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C패스트::C패스트](#cpatht)|경로의 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPathT::추가 슬래시](#addbackslash)|이 메서드를 호출하여 문자열 끝에 백슬래시를 추가하여 경로에 대한 올바른 구문을 만듭니다.|
|[CPathT::추가 확장](#addextension)|이 메서드를 호출하여 파일에 확장프로그램을 추가합니다.|
|[CPathT::부속](#append)|이 메서드를 호출하여 문자열을 현재 경로에 부가합니다.|
|[CPathT::빌드 루트](#buildroot)|지정된 드라이브 번호에서 루트 경로를 만들려면 이 메서드를 호출합니다.|
|[CPathT:::표준화](#canonicalize)|이 메서드를 호출하여 경로를 표준 형식으로 변환합니다.|
|[CPathT::결합](#combine)|이 메서드를 호출하여 디렉터리 이름을 나타내는 문자열과 파일 경로 이름을 나타내는 문자열을 하나의 경로로 연결합니다.|
|[CPathT::공통 사전 수정](#commonprefix)|지정된 경로가 현재 경로와 공통 접두사를 공유하는지 여부를 확인하려면 이 메서드를 호출합니다.|
|[CPathT::컴팩트 패스](#compactpath)|경로 구성요소를 타원으로 대체하여 지정된 픽셀 너비 내에 맞게 파일 경로를 잘리려면 이 메서드를 호출합니다.|
|[CPathT::콤팩트패스엑스](#compactpathex)|경로 구성요소를 타원으로 대체하여 지정된 수의 문자 내에 맞게 파일 경로를 잘리려면 이 메서드를 호출합니다.|
|[CPathT::파일 존재](#fileexists)|이 메서드를 호출하여 이 경로 이름의 파일이 있는지 확인합니다.|
|[CPathT::찾기 확장](#findextension)|이 메서드를 호출하여 경로 내의 파일 확장자의 위치를 찾습니다.|
|[CPathT::파일 이름 찾기](#findfilename)|이 메서드를 호출하여 경로 내에서 파일 이름의 위치를 찾습니다.|
|[CPathT::겟드라이브 넘버](#getdrivenumber)|이 메서드를 호출하여 'A' 범위 내의 드라이브 문자에서 'Z'로 의 경로를 검색하고 해당 드라이브 번호를 반환합니다.|
|[CPathT::GetExtension](#getextension)|이 메서드를 호출하여 경로에서 파일 확장프로그램을 가져옵니다.|
|[CPathT::IsDirectory](#isdirectory)|이 메서드를 호출하여 경로가 유효한 디렉터리인지 확인합니다.|
|[CPathT::IsFileSpec](#isfilespec)|이 메서드를 호출하여 경로 구분 문자(예: ':' 또는 '')에\\대한 경로를 검색합니다. 경로 구분 문자가 없는 경우 경로는 파일 사양 경로로 간주됩니다.|
|[CPathT::IsPrefix](#isprefix)|이 메서드를 호출하여 경로에 *pszPrefix*로 전달된 형식의 유효한 접두사가 포함되어 있는지 확인합니다.|
|[CPathT::상대적입니다.](#isrelative)|이 메서드를 호출하여 경로가 상대적인지 확인합니다.|
|[CPathT::IsRoot](#isroot)|이 메서드를 호출하여 경로가 디렉터리 루트인지 확인합니다.|
|[CPathT::IsSameRoot](#issameroot)|이 메서드를 호출하여 다른 경로에 현재 경로가 있는 공통 루트 구성 요소가 있는지 확인합니다.|
|[CPathT::이스운크](#isunc)|이 메서드를 호출하여 경로가 서버 및 공유에 대한 유효한 UNC(범용 명명 규칙) 경로인지 확인합니다.|
|[CPathT::IsUNCServer](#isuncserver)|이 메서드를 호출하여 경로가 서버에만 유효한 UNC(범용 명명 규칙) 경로인지 확인합니다.|
|[CPathT::IsUNCServerShare](#isuncservershare)|이 메서드를 호출하여 경로가 유효한 UNC(범용 명명 \\ \ 규칙) 공유 경로인지, *서버*\ *공유인지*확인합니다.|
|[CPathT::메이크프리티](#makepretty)|이 메서드를 호출하여 경로를 모든 소문자로 변환하여 경로에 일관된 모양을 지정합니다.|
|[C패스트::매치스펙](#matchspec)|와일드카드 일치 유형이 포함된 문자열의 경로를 검색하려면 이 메서드를 호출합니다.|
|[CPathT::견적 공백](#quotespaces)|공백이 포함된 경우 이 메서드를 호출하여 따옴표로 패스를 둘러싸습니다.|
|[CPathT::상대 경로](#relativepathto)|한 파일이나 폴더에서 다른 파일또는 폴더로의 상대 경로를 만들려면 이 메서드를 호출합니다.|
|[CPathT::제거아르그](#removeargs)|이 메서드를 호출하여 경로에서 명령줄 인수를 제거합니다.|
|[CPathT::제거백슬래시](#removebackslash)|이 메서드를 호출하여 경로에서 후행 백슬래시를 제거합니다.|
|[CPathT::제거 공백](#removeblanks)|이 메서드를 호출하여 경로에서 모든 행간 및 후행 공백을 제거합니다.|
|[CPathT::제거확장](#removeextension)|이 메서드를 호출하여 파일 확장명이 있는 경우 경로에서 파일 확장프로그램을 제거합니다.|
|[CPathT::제거파일스펙](#removefilespec)|이 메서드를 호출하여 후행 파일 이름과 백슬래시가 있는 경우 경로에서 백슬래시를 제거합니다.|
|[CPathT::이름 바꾸기확장](#renameextension)|이 메서드를 호출하여 경로의 파일 이름 확장명을 새 확장명으로 바꿉니다. 파일 이름에 확장이 포함되어 있지 않으면 확장이 문자열의 끝에 연결됩니다.|
|[CPathT::스킵루트](#skiproot)|드라이브 문자 또는 UNC 서버/공유 경로 부분을 무시하고 경로를 구문 분석하려면 이 메서드를 호출합니다.|
|[C패스::스트립패스](#strippath)|이 메서드를 호출하여 정규화된 경로 및 파일 이름의 경로 부분을 제거합니다.|
|[CPathT::스트립토루트](#striptoroot)|루트 정보를 제외한 경로의 모든 부분을 제거하려면 이 메서드를 호출합니다.|
|[CPathT::인용부호 없는 공간](#unquotespaces)|이 메서드를 호출하여 경로의 시작과 끝에서 따옴표를 제거합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CPathT::연산자 const stringType &](#operator_const_stringtype_amp)|이 연산자는 개체를 문자열처럼 처리할 수 있도록 합니다.|
|[CPathT::연산자 CPathT::PCXSTR](#operator_cpatht__pcxstr)|이 연산자는 개체를 문자열처럼 처리할 수 있도록 합니다.|
|[CPathT::연산자 문자열 유형 &](#operator_stringtype_amp)|이 연산자는 개체를 문자열처럼 처리할 수 있도록 합니다.|
|[CPathT::연산자 +=](#operator_add_eq)|이 연산자는 경로에 문자열을 적용합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CPathT::m_strPath](#m_strpath)|경로입니다.|

## <a name="remarks"></a>설명

`CPath`및 `CPathA` `CPathW` 다음과 같이 `CPathT` 정의된 인스턴스화입니다.

`typedef CPathT< CString > CPath;`

`typedef CPathT< CStringA > CPathA;`

`typedef CPathT< CStringW > CPathW;`

## <a name="requirements"></a>요구 사항

**헤더:** atlpath.h

## <a name="cpathtaddbackslash"></a><a name="addbackslash"></a>CPathT::추가 슬래시

이 메서드를 호출하여 문자열 끝에 백슬래시를 추가하여 경로에 대한 올바른 구문을 만듭니다. 경로에 후행 백슬래시가 이미 있는 경우 백슬래시가 추가되지 않습니다.

```cpp
void AddBackslash();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathAddBackSlash](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)을 참조하십시오.

## <a name="cpathtaddextension"></a><a name="addextension"></a>CPathT::추가 확장

이 메서드를 호출하여 파일에 확장프로그램을 추가합니다.

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>매개 변수

*psz내란이*<br/>
추가할 파일 확장명입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

자세한 내용은 [PathAddExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)을 참조하십시오.

## <a name="cpathtappend"></a><a name="append"></a>CPathT::부속

이 메서드를 호출하여 문자열을 현재 경로에 부가합니다.

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>매개 변수

*pszMore*<br/>
추가할 문자열입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

자세한 내용은 [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)을 참조하십시오.

## <a name="cpathtbuildroot"></a><a name="buildroot"></a>CPathT::빌드 루트

지정된 드라이브 번호에서 루트 경로를 만들려면 이 메서드를 호출합니다.

```cpp
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>매개 변수

*Idrive*<br/>
드라이브 번호(0은 A: 1, 1은 B:, 등등).

### <a name="remarks"></a>설명

자세한 내용은 [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)을 참조하십시오.

## <a name="cpathtcanonicalize"></a><a name="canonicalize"></a>CPathT:::표준화

이 메서드를 호출하여 경로를 표준 형식으로 변환합니다.

```cpp
void Canonicalize();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)를 참조하십시오.

## <a name="cpathtcombine"></a><a name="combine"></a>CPathT::결합

이 메서드를 호출하여 디렉터리 이름을 나타내는 문자열과 파일 경로 이름을 나타내는 문자열을 하나의 경로로 연결합니다.

```cpp
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>매개 변수

*pszDir*<br/>
디렉터리 경로입니다.

*pszFile*<br/>
파일 경로입니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathCombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)을 참조하십시오.

## <a name="cpathtcommonprefix"></a><a name="commonprefix"></a>CPathT::공통 사전 수정

지정된 경로가 현재 경로와 공통 접두사를 공유하는지 여부를 확인하려면 이 메서드를 호출합니다.

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>매개 변수

*pszOther*<br/>
현재 경로와 비교할 경로입니다.

### <a name="return-value"></a>Return Value

공통 접두사를 반환합니다.

### <a name="remarks"></a>설명

접두사는 이러한 유형 중 하나입니다:\\\\"C: ", ",", ".,", "...". \\\\". 자세한 내용은 [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)을 참조하십시오.

## <a name="cpathtcompactpath"></a><a name="compactpath"></a>CPathT::컴팩트 패스

경로 구성요소를 타원으로 대체하여 지정된 픽셀 너비 내에 맞게 파일 경로를 잘리려면 이 메서드를 호출합니다.

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>매개 변수

*Hdc*<br/>
글꼴 메트릭에 사용되는 장치 컨텍스트입니다.

*nWidth*<br/>
문자열이 강제로 맞도록 하는 너비(픽셀 단위)입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

자세한 내용은 [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)을 참조하십시오.

## <a name="cpathtcompactpathex"></a><a name="compactpathex"></a>CPathT::콤팩트패스엑스

경로 구성요소를 타원으로 대체하여 지정된 수의 문자 내에 맞게 파일 경로를 잘리려면 이 메서드를 호출합니다.

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>매개 변수

*nMaxChars*<br/>
NULL 문자 종료를 포함하여 새 문자열에 포함될 최대 문자 수입니다.

*dwFlags*<br/>
예약되어 있습니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

자세한 내용은 [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)를 참조하십시오.

## <a name="cpathtcpatht"></a><a name="cpatht"></a>C패스트::C패스트

생성자입니다.

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>매개 변수

*pszPath*<br/>
경로 문자열에 대한 포인터입니다.

*path*<br/>
경로 문자열입니다.

## <a name="cpathtfileexists"></a><a name="fileexists"></a>CPathT::파일 존재

이 메서드를 호출하여 이 경로 이름의 파일이 있는지 확인합니다.

```
BOOL FileExists() const;
```

### <a name="return-value"></a>Return Value

파일이 있는 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)을 참조하십시오.

## <a name="cpathtfindextension"></a><a name="findextension"></a>CPathT::찾기 확장

이 메서드를 호출하여 경로 내의 파일 확장자의 위치를 찾습니다.

```
int FindExtension() const;
```

### <a name="return-value"></a>Return Value

확장 앞에 있는 "."의 위치를 반환합니다. 확장이 발견되지 않으면 -1을 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathFindExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)을 참조하십시오.

## <a name="cpathtfindfilename"></a><a name="findfilename"></a>CPathT::파일 이름 찾기

이 메서드를 호출하여 경로 내에서 파일 이름의 위치를 찾습니다.

```
int FindFileName() const;
```

### <a name="return-value"></a>Return Value

파일 이름의 위치를 반환합니다. 파일 이름을 찾을 수 없는 경우 -1을 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathFindFile Name](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)을 참조하십시오.

## <a name="cpathtgetdrivenumber"></a><a name="getdrivenumber"></a>CPathT::겟드라이브 넘버

이 메서드를 호출하여 'A' 범위 내의 드라이브 문자에서 'Z'로 의 경로를 검색하고 해당 드라이브 번호를 반환합니다.

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>Return Value

경로에 드라이브 문자가 있는 경우 드라이브 번호를 0에서 25까지('A'에서 'Z'로 해당)에서 정수로 반환하거나 -1을 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)를 참조하십시오.

## <a name="cpathtgetextension"></a><a name="getextension"></a>CPathT::GetExtension

이 메서드를 호출하여 경로에서 파일 확장프로그램을 가져옵니다.

```
StringType GetExtension() const;
```

### <a name="return-value"></a>Return Value

파일 확장프로그램을 반환합니다.

## <a name="cpathtisdirectory"></a><a name="isdirectory"></a>CPathT::IsDirectory

이 메서드를 호출하여 경로가 유효한 디렉터리인지 확인합니다.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Return Value

경로가 디렉터리인 경우 0이 아닌 값(16)을 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsDirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)를 참조하십시오.

## <a name="cpathtisfilespec"></a><a name="isfilespec"></a>CPathT::IsFileSpec

이 메서드를 호출하여 경로 구분 문자(예: ':' 또는 '')에\\대한 경로를 검색합니다. 경로 구분 문자가 없는 경우 경로는 파일 사양 경로로 간주됩니다.

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>Return Value

경로 내에 경로 구분 문자가 없는 경우 TRUE를 반환하거나 경로 구분 문자가 있는 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)을 참조하십시오.

## <a name="cpathtisprefix"></a><a name="isprefix"></a>CPathT::IsPrefix

이 메서드를 호출하여 경로에 *pszPrefix*로 전달된 형식의 유효한 접두사가 포함되어 있는지 확인합니다.

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>매개 변수

*pszPrefix*<br/>
검색할 접두사입니다. 접두사는 이러한 유형 중 하나입니다:\\\\"C: ", ",", ".,", "...". \\\\".

### <a name="return-value"></a>Return Value

경로에 접두사가 포함된 경우 TRUE를 반환하거나 FALSE를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)을 참조하십시오.

## <a name="cpathtisrelative"></a><a name="isrelative"></a>CPathT::상대적입니다.

이 메서드를 호출하여 경로가 상대적인지 확인합니다.

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>Return Value

경로가 상대적인 경우 TRUE를 반환하거나 절대인 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)을 참조하십시오.

## <a name="cpathtisroot"></a><a name="isroot"></a>CPathT::IsRoot

이 메서드를 호출하여 경로가 디렉터리 루트인지 확인합니다.

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>Return Value

경로가 루트인 경우 TRUE를 반환하거나 FALSE인 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)을 참조하십시오.

## <a name="cpathtissameroot"></a><a name="issameroot"></a>CPathT::IsSameRoot

이 메서드를 호출하여 다른 경로에 현재 경로가 있는 공통 루트 구성 요소가 있는지 확인합니다.

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>매개 변수

*pszOther*<br/>
다른 경로입니다.

### <a name="return-value"></a>Return Value

두 문자열에 동일한 루트 구성 요소가 있거나 FALSE가 있는 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)을 참조하십시오.

## <a name="cpathtisunc"></a><a name="isunc"></a>CPathT::이스운크

이 메서드를 호출하여 경로가 서버 및 공유에 대한 유효한 UNC(범용 명명 규칙) 경로인지 확인합니다.

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>Return Value

경로가 유효한 UNC 경로인 경우 TRUE를 반환하거나 FALSE그렇지 않으면 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)을 참조하십시오.

## <a name="cpathtisuncserver"></a><a name="isuncserver"></a>CPathT::IsUNCServer

이 메서드를 호출하여 경로가 서버에만 유효한 UNC(범용 명명 규칙) 경로인지 확인합니다.

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>Return Value

문자열이 서버에 대해서만 유효한 UNC 경로인 경우 TRUE를 반환합니다(공유 이름 없음) 또는 FALSE 그렇지 않은 경우

### <a name="remarks"></a>설명

자세한 내용은 [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)를 참조하십시오.

## <a name="cpathtisuncservershare"></a><a name="isuncservershare"></a>CPathT::IsUNCServerShare

이 메서드를 호출하여 경로가 유효한 UNC(범용 명명 \\ \ 규칙) 공유 경로인지, *서버*\ *공유인지*확인합니다.

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>Return Value

경로가 \\ \ 양식 *서버*\ *공유에*있는 경우 TRUE를 반환하거나 FALSE를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsUNCServerShare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)을 참조하십시오.

## <a name="cpathtm_strpath"></a><a name="m_strpath"></a>CPathT::m_strPath

경로입니다.

```
StringType m_strPath;
```

### <a name="remarks"></a>설명

`StringType`은 에 대한 `CPathT`템플릿 매개 변수입니다.

## <a name="cpathtmakepretty"></a><a name="makepretty"></a>CPathT::메이크프리티

이 메서드를 호출하여 경로를 모든 소문자로 변환하여 경로에 일관된 모양을 지정합니다.

```
BOOL MakePretty();
```

### <a name="return-value"></a>Return Value

경로가 변환된 경우 TRUE를 반환하거나 FALSE를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)을 참조하십시오.

## <a name="cpathtmatchspec"></a><a name="matchspec"></a>C패스트::매치스펙

와일드카드 일치 유형이 포함된 문자열의 경로를 검색하려면 이 메서드를 호출합니다.

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>매개 변수

*pszSpec*<br/>
검색할 파일 형식을 사용하여 null-종료된 문자열에 대한 포인터입니다. 예를 들어 현재 경로의 파일이 DOC 파일인지 여부를 테스트하려면 *pszSpec을* "*.doc"으로 설정해야 합니다.

### <a name="return-value"></a>Return Value

문자열이 일치하는 경우 TRUE를 반환하거나 FALSE를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)을 참조하십시오.

## <a name="cpathtoperator-"></a><a name="operator_add_eq"></a>CPathT::연산자 +=

이 연산자는 경로에 문자열을 적용합니다.

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>매개 변수

*pszMore*<br/>
추가할 문자열입니다.

### <a name="return-value"></a>Return Value

업데이트된 경로를 반환합니다.

## <a name="cpathtoperator-const-stringtype-amp"></a><a name="operator_const_stringtype_amp"></a>CPathT::연산자 const 문자열 유형&amp;

이 연산자는 개체를 문자열처럼 처리할 수 있도록 합니다.

```
operator const StringType&() const throw();
```

### <a name="return-value"></a>Return Value

이 개체에서 관리하는 현재 경로를 나타내는 문자열을 반환합니다.

## <a name="cpathtoperator-cpathtpcxstr"></a><a name="operator_cpatht__pcxstr"></a>CPathT::연산자 CPathT::PCXSTR

이 연산자는 개체를 문자열처럼 처리할 수 있도록 합니다.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Return Value

이 개체에서 관리하는 현재 경로를 나타내는 문자열을 반환합니다.

## <a name="cpathtoperator-stringtype-amp"></a><a name="operator_stringtype_amp"></a>CPathT::연산자 문자열 유형&amp;

이 연산자는 개체를 문자열처럼 처리할 수 있도록 합니다.

```
operator StringType&() throw();
```

### <a name="return-value"></a>Return Value

이 개체에서 관리하는 현재 경로를 나타내는 문자열을 반환합니다.

## <a name="cpathtpcxstr"></a><a name="pcxstr"></a>CPathT::PCXSTR

상수 문자열 형식입니다.

```
typedef StringType::PCXSTR PCXSTR;
```

### <a name="remarks"></a>설명

`StringType`은 에 대한 `CPathT`템플릿 매개 변수입니다.

## <a name="cpathtpxstr"></a><a name="pxstr"></a>CPathT::PXSTR

문자열 유형입니다.

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>설명

`StringType`은 에 대한 `CPathT`템플릿 매개 변수입니다.

## <a name="cpathtquotespaces"></a><a name="quotespaces"></a>CPathT::견적 공백

공백이 포함된 경우 이 메서드를 호출하여 따옴표로 패스를 둘러싸습니다.

```cpp
void QuoteSpaces();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)을 참조하십시오.

## <a name="cpathtrelativepathto"></a><a name="relativepathto"></a>CPathT::상대 경로

한 파일이나 폴더에서 다른 파일또는 폴더로의 상대 경로를 만들려면 이 메서드를 호출합니다.

```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```

### <a name="parameters"></a>매개 변수

*pszFrom*<br/>
상대 경로의 시작입니다.

*dwAttrFrom에서*<br/>
*pszFrom의*파일 속성입니다. 이 값에 FILE_ATTRIBUTE_DIRECTORY 포함되어 있으면 *pszFrom는* 디렉터리로 가정합니다. 그렇지 않으면 *pszFrom파일로* 가정합니다.

*pszTo*<br/>
상대 경로의 끝점입니다.

*dwAttrTo*<br/>
*pszTo의*파일 속성 . 이 값에 FILE_ATTRIBUTE_DIRECTORY 포함되어 있으면 *pszTo는* 디렉터리로 가정합니다. 그렇지 않으면 *pszTo는* 파일로 가정합니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

자세한 내용은 [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)를 참조하십시오.

## <a name="cpathtremoveargs"></a><a name="removeargs"></a>CPathT::제거아르그

이 메서드를 호출하여 경로에서 명령줄 인수를 제거합니다.

```cpp
void RemoveArgs();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)을 참조하십시오.

## <a name="cpathtremovebackslash"></a><a name="removebackslash"></a>CPathT::제거백슬래시

이 메서드를 호출하여 경로에서 후행 백슬래시를 제거합니다.

```cpp
void RemoveBackslash();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathRemoveBack슬래시](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)를 참조하십시오.

## <a name="cpathtremoveblanks"></a><a name="removeblanks"></a>CPathT::제거 공백

이 메서드를 호출하여 경로에서 모든 행간 및 후행 공백을 제거합니다.

```cpp
void RemoveBlanks();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathRemoveBlanks](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)를 참조하십시오.

## <a name="cpathtremoveextension"></a><a name="removeextension"></a>CPathT::제거확장

이 메서드를 호출하여 파일 확장명이 있는 경우 경로에서 파일 확장프로그램을 제거합니다.

```cpp
void RemoveExtension();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)을 참조하십시오.

## <a name="cpathtremovefilespec"></a><a name="removefilespec"></a>CPathT::제거파일스펙

이 메서드를 호출하여 후행 파일 이름과 백슬래시가 있는 경우 경로에서 백슬래시를 제거합니다.

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

자세한 내용은 [PathRemoveFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)을 참조하십시오.

## <a name="cpathtrenameextension"></a><a name="renameextension"></a>CPathT::이름 바꾸기확장

이 메서드를 호출하여 경로의 파일 이름 확장명을 새 확장명으로 바꿉니다. 파일 이름에 확장이 포함되어 있지 않으면 확장이 경로의 끝에 첨부됩니다.

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>매개 변수

*psz내란이*<br/>
새 파일 이름 확장자 앞에 "." 문자가 옵니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

자세한 내용은 [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)을 참조하십시오.

## <a name="cpathtskiproot"></a><a name="skiproot"></a>CPathT::스킵루트

이 메서드를 호출하여 드라이브 문자 또는 UNC(범용 명명 규칙) 서버/공유 경로 부분을 무시하고 경로를 구문 분석합니다.

```
int SkipRoot() const;
```

### <a name="return-value"></a>Return Value

루트(드라이브 문자 또는 UNC 서버/공유)를 따르는 하위 경로의 시작 위치를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)을 참조하십시오.

## <a name="cpathtstrippath"></a><a name="strippath"></a>C패스::스트립패스

이 메서드를 호출하여 정규화된 경로 및 파일 이름의 경로 부분을 제거합니다.

```cpp
void StripPath();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)을 참조하십시오.

## <a name="cpathtstriptoroot"></a><a name="striptoroot"></a>CPathT::스트립토루트

루트 정보를 제외한 경로의 모든 부분을 제거하려면 이 메서드를 호출합니다.

```
BOOL StripToRoot();
```

### <a name="return-value"></a>Return Value

경로에서 유효한 드라이브 문자가 발견되었거나 FALSE가 그렇지 않으면 TRUE를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)을 참조하십시오.

## <a name="cpathtunquotespaces"></a><a name="unquotespaces"></a>CPathT::인용부호 없는 공간

이 메서드를 호출하여 경로의 시작과 끝에서 따옴표를 제거합니다.

```cpp
void UnquoteSpaces();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)을 참조하십시오.

## <a name="cpathtxchar"></a><a name="xchar"></a>CPathT::XCHAR

문자 형식입니다.

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>설명

`StringType`은 에 대한 `CPathT`템플릿 매개 변수입니다.

## <a name="see-also"></a>참조

[클래스](../../atl/reference/atl-classes.md)<br/>
[CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md)
