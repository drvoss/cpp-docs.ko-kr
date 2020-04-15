---
title: ATL 경로 기능
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, path
f1_keywords:
- ATLPATH/ATL::ATLPath::AddBackslash
- ATLPATH/ATL::ATLPath::AddExtension
- ATLPATH/ATL::ATLPath::Append
- ATLPATH/ATL::ATLPath::BuildRoot
- ATLPATH/ATL::ATLPath::Canonicalize
- ATLPATH/ATL::ATLPath::Combine
- ATLPATH/ATL::ATLPath::CommonPrefix
- ATLPATH/ATL::ATLPath::CompactPath
- ATLPATH/ATL::ATLPath::CompactPathEx
- ATLPATH/ATL::ATLPath::FileExists
- ATLPATH/ATL::ATLPath::FindExtension
- ATLPATH/ATL::ATLPath::FindFileName
- ATLPATH/ATL::ATLPath::GetDriveNumber
- ATLPATH/ATL::ATLPath::IsDirectory
- ATLPATH/ATL::ATLPath::IsFileSpec
- ATLPATH/ATL::ATLPath::IsPrefix
- ATLPATH/ATL::ATLPath::IsRelative
- ATLPATH/ATL::ATLPath::IsRoot
- ATLPATH/ATL::ATLPath::IsSameRoot
- ATLPATH/ATL::ATLPath::IsUNC
- ATLPATH/ATL::ATLPath::IsUNCServer
- ATLPATH/ATL::ATLPath::IsUNCServerShare
- ATLPATH/ATL::ATLPath::MakePretty
- ATLPATH/ATL::ATLPath::MatchSpec
- ATLPATH/ATL::ATLPath::QuoteSpaces
- ATLPATH/ATL::ATLPath::RelativePathTo
- ATLPATH/ATL::ATLPath::RemoveArgs
- ATLPATH/ATL::ATLPath::RemoveBackslash
- ATLPATH/ATL::ATLPath::RemoveBlanks
- ATLPATH/ATL::ATLPath::RemoveExtension
- ATLPATH/ATL::ATLPath::RemoveFileSpec
- ATLPATH/ATL::ATLPath::RenameExtension
- ATLPATH/ATL::ATLPath::SkipRoot
- ATLPATH/ATL::ATLPath::StripPath
- ATLPATH/ATL::ATLPath::StripToRoot
- ATLPATH/ATL::ATLPath::UnquoteSpaces
ms.assetid: d1ec2b8d-7ec7-43ea-90dd-0a740d2a742b
ms.openlocfilehash: f3d8fa63e7fd20f8a0d6759fee8417b3fbc29486
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319217"
---
# <a name="atl-path-functions"></a>ATL 경로 기능

ATL은 [CPathT](cpatht-class.md)의 형태로 경로를 조작하기 위한 ATLPath 클래스를 제공합니다. 이 코드는 atlpath.h에서 찾을 수 있습니다.

### <a name="related-classes"></a>관련 수업

|||
|-|-|
|[CPathT 클래스](cpatht-class.md)|이 클래스는 경로를 나타냅니다.|

### <a name="related-typedefs"></a>관련 유형 defs

|||
|-|-|
|`CPath`|를 사용하는 `CString` [CPathT의](cpatht-class.md) 전문화.|
|`CPathA`|를 사용하는 `CStringA` [CPathT의](cpatht-class.md) 전문화.|
|`CPathW`|를 사용하는 `CStringW` [CPathT의](cpatht-class.md) 전문화.|

### <a name="functions"></a>Functions

|||
|-|-|
|[ATLPath::AddBackslash](#addbackslash)|이 함수는 [PathAddBackslash에](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)대한 오버로드된 래퍼입니다.|
|[ATLPath::AddExtension](#addextension)|이 함수는 [PathAddExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::Append](#append)|이 함수는 [PathAppend에](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)대한 오버로드된 래퍼입니다.|
|[ATLPath::BuildRoot](#buildroot)|이 함수는 [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::Canonicalize](#canonicalize)|이 함수는 [PathCanonicalize에](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)대한 오버로드된 래퍼입니다.|
|[ATLPath::Combine](#combine)|이 함수는 PathCombine 에 대한 오버로드된 [래퍼입니다.](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)|
|[ATLPath::CommonPrefix](#commonprefix)|이 함수는 [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::CompactPath](#compactpath)|이 함수는 [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::CompactPathEx](#compactpathex)|이 함수는 [PathCompactPathEx에](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)대한 오버로드된 래퍼입니다.|
|[ATLPath::FileExists](#fileexists)|이 함수는 [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::FindExtension](#findextension)|이 함수는 [PathFindExtension에](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)대한 오버로드된 래퍼입니다.|
|[ATLPath::FindFileName](#findfilename)|이 함수는 [PathFindFile Name에](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)대한 오버로드된 래퍼입니다.|
|[ATLPath::GetDriveNumber](#getdrivenumber)|이 함수는 [PathGetDriveNumber에](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)대한 오버로드된 래퍼입니다.|
|[ATLPath::IsDirectory](#isdirectory)|이 함수는 [PathIsDirectory에](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)대한 오버로드된 래퍼입니다.|
|[ATLPath::IsFileSpec](#isfilespec)|이 함수는 [PathIsFileSpec에](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)대한 오버로드된 래퍼입니다.|
|[ATLPath::IsPrefix](#isprefix)|이 함수는 [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::IsRelative](#isrelative)|이 함수는 [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::IsRoot](#isroot)|이 함수는 [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::IsSameRoot](#issameroot)|이 함수는 [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::IsUNC](#isunc)|이 함수는 [PathIsUNC에](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)대한 오버로드된 래퍼입니다.|
|[ATLPath::IsUNCServer](#isuncserver)|이 함수는 [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::IsUNCServerShare](#isuncservershare)|이 함수는 [PathIsUNCServerShare에](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)대한 오버로드래퍼입니다.|
|[ATLPath::MakePretty](#makepretty)|이 함수는 [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)에 대한 오버로드 래퍼입니다.|
|[ATLPath::MatchSpec](#matchspec)|이 함수는 [PathMatchSpec에](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)대한 오버로드된 래퍼입니다.|
|[ATLPath::QuoteSpaces](#quotespaces)|이 함수는 [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::RelativePathTo](#relativepathto)|이 함수는 [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::RemoveArgs](#removeargs)|이 함수는 [PathRemoveArgs에](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)대한 오버로드된 래퍼입니다.|
|[ATLPath::RemoveBackslash](#removebackslash)|이 함수는 [PathRemoveBackslash에](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)대한 오버로드된 래퍼입니다.|
|[ATLPath::RemoveBlanks](#removeblanks)|이 함수는 [PathRemoveBlanks에](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)대한 오버로드된 래퍼입니다.|
|[ATLPath::RemoveExtension](#removeextension)|이 함수는 [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::RemoveFileSpec](#removefilespec)|이 함수는 [PathRemoveFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::RenameExtension](#renameextension)|이 함수는 [PathRenameExtension에](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)대한 오버로드된 래퍼입니다.|
|[ATLPath::SkipRoot](#skiproot)|이 함수는 [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::StripPath](#strippath)|이 함수는 [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)에 대한 오버로드된 래퍼입니다.|
|[ATLPath::StripToRoot](#striptoroot)|이 함수는 [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)에 대한 오버로드 래퍼입니다.|
|[ATLPath::UnquoteSpaces](#unquotespaces)|이 함수는 [PathUnquoteSpaces에](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)대한 오버로드된 래퍼입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlpath.h

## <a name="atlpathaddbackslash"></a><a name="addbackslash"></a>ATLPath::추가 슬래시

이 함수는 [PathAddBackslash에](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline char* AddBackslash(char* pszPath);
inline wchar_t* AddBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathAddBack슬래시를](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw) 참조하십시오.

## <a name="atlpathaddextension"></a><a name="addextension"></a>ATLPath::추가 확장

이 함수는 [PathAddExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL AddExtension(char* pszPath, const char* pszExtension);
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathAddExtension을](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw) 참조하십시오.

## <a name="atlpathappend"></a><a name="append"></a>ATLPath::부속

이 함수는 [PathAppend에](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL Append(char* pszPath, const char* pszMore);
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);
```

### <a name="remarks"></a>설명

자세한 내용은 [패스 앱펜션을](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw) 참조하십시오.

## <a name="atlpathbuildroot"></a><a name="buildroot"></a>ATLPath::빌드 루트

이 함수는 [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline char* BuildRoot(char* pszPath, int iDrive);
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathBuildRoot를](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw) 참조하십시오.

## <a name="atlpathcanonicalize"></a><a name="canonicalize"></a>ATLPath:::표준화

이 함수는 [PathCanonicalize에](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathCanonicalize를](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew) 참조하십시오.

## <a name="atlpathcombine"></a><a name="combine"></a>ATLPath::결합

이 함수는 PathCombine 에 대한 오버로드된 [래퍼입니다.](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)

### <a name="syntax"></a>구문

```
inline char* Combine(
   char* pszDest,
   const char* pszDir,
   const char* pszFile
);

inline wchar_t* Combine(
   wchar_t* pszDest,
   const wchar_t* pszDir,
   const wchar_t* pszFile);
```

### <a name="remarks"></a>설명

자세한 내용은 패스 결합을 참조하십시오.

## <a name="atlpathcommonprefix"></a><a name="commonprefix"></a>ATLPath::공통 프리픽스

이 함수는 [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline int CommonPrefix(
   const char* pszFile1,
   const char* pszFile2,
   char* pszDest);

inline int CommonPrefix(
   const wchar_t* pszFile1,
   const wchar_t* pszFile2,
   wchar_t* pszDest);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathCommonPrefix를](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw) 참조하십시오.

## <a name="atlpathcompactpath"></a><a name="compactpath"></a>ATLPath:::컴팩트 패스

이 함수는 [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL CompactPath(
   HDC hDC,
   char* pszPath,
   UINT dx);

inline BOOL CompactPath(
   HDC hDC,
   wchar_t* pszPath,
   UINT dx);
```

### <a name="remarks"></a>설명

자세한 내용은 [경로 압축 경로를](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw) 참조하십시오.

## <a name="atlpathcompactpathex"></a><a name="compactpathex"></a>ATLPath::콤팩트패스엑스

이 함수는 [PathCompactPathEx에](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL CompactPathEx(
   char* pszDest,
   const char* pszSrc,
   UINT nMaxChars,
   DWORD dwFlags);

inline BOOL CompactPathEx(
   wchar_t* pszDest,
   const wchar_t* pszSrc,
   UINT nMaxChars,
   DWORD dwFlags);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathCompactPathEx를](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw) 참조하십시오.

## <a name="atlpathfileexists"></a><a name="fileexists"></a>ATLPath::파일 존재

이 함수는 [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL FileExists(const char* pszPath);
inline BOOL FileExists(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathFileExists를](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw) 참조하십시오.

## <a name="atlpathfindextension"></a><a name="findextension"></a>ATLPath::찾기 확장

이 함수는 [PathFindExtension에](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline char* FindExtension(const char* pszPath);
inline wchar_t* FindExtension(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [패스찾기익스텐션을](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw) 참조하십시오.

## <a name="atlpathfindfilename"></a><a name="findfilename"></a>ATLPath::찾기파일 이름

이 함수는 [PathFindFile Name에](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline char* FindFileName(const char* pszPath);
inline wchar_t* FindFileName(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [패스찾기파일이름을](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) 참조하십시오.

## <a name="atlpathgetdrivenumber"></a><a name="getdrivenumber"></a>ATLPath::겟드라이브 넘버

이 함수는 [PathGetDriveNumber에](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline int GetDriveNumber(const char* pszPath);
inline int GetDriveNumber(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathGetDriveNumber를](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw) 참조하십시오.

## <a name="atlpathisdirectory"></a><a name="isdirectory"></a>ATLPath::IsDirectory

이 함수는 [PathIsDirectory에](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)대한 오버로드된 래퍼입니다.

```
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 PathIsDirectory를 참조하십시오.

## <a name="atlpathisfilespec"></a><a name="isfilespec"></a>ATLPath::IsFileSpec

이 함수는 [PathIsFileSpec에](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL IsFileSpec(const char* pszPath);
inline BOOL IsFileSpec(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathIsFileSpec을](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw) 참조하십시오.

## <a name="atlpathisprefix"></a><a name="isprefix"></a>ATLPath::IsPrefix

이 함수는 [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathIsPrefix를](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw) 참조하십시오.

## <a name="atlpathisrelative"></a><a name="isrelative"></a>ATLPath::상대적

이 함수는 [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL IsRelative(const char* pszPath);
inline BOOL IsRelative(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathIsRelative을](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew) 참조하십시오.

## <a name="atlpathisroot"></a><a name="isroot"></a>ATLPath::이뿌리

이 함수는 [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL IsRoot(const char* pszPath);
inline BOOL IsRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathIsRoot를](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw) 참조하십시오.

## <a name="atlpathissameroot"></a><a name="issameroot"></a>ATLPath::IsSameRoot

이 함수는 [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathIsSameRoot를](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw) 참조하십시오.

## <a name="atlpathisunc"></a><a name="isunc"></a>ATLPath::이운크

이 함수는 [PathIsUNC에](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL IsUNC(const char* pszPath);
inline BOOL IsUNC(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathIsUNC를](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw) 참조하십시오.

## <a name="atlpathisuncserver"></a><a name="isuncserver"></a>ATLPath::IsUNCServer

이 함수는 [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL IsUNCServer(const char* pszPath);
inline BOOL IsUNCServer(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathIsUNCServer를](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw) 참조하십시오.

## <a name="atlpathisuncservershare"></a><a name="isuncservershare"></a>ATLPath::IsUNCServerShare

이 함수는 [PathIsUNCServerShare에](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)대한 오버로드래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL IsUNCServerShare(const char* pszPath);
inline BOOL IsUNCServerShare(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathIsUNCServerShare를](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew) 참조하십시오.

## <a name="atlpathmakepretty"></a><a name="makepretty"></a>ATLPath::메이크프리티

이 함수는 [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)에 대한 오버로드 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL MakePretty(char* pszPath);
inline BOOL MakePretty(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathMakePretty를](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw) 참조하십시오.

## <a name="atlpathmatchspec"></a><a name="matchspec"></a>ATLPath::매치스펙

이 함수는 [PathMatchSpec에](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);
```

### <a name="remarks"></a>설명

자세한 내용은 [패스매치스펙을](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw) 참조하십시오.

## <a name="atlpathquotespaces"></a><a name="quotespaces"></a>ATLPath::견적 스페이스

이 함수는 [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline void QuoteSpaces(char* pszPath);
inline void QuoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [패스인용스페이스를](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw) 참조하십시오.

## <a name="atlpathrelativepathto"></a><a name="relativepathto"></a>ATLPath::상대 경로

이 함수는 [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL RelativePathTo(
   char* pszPath,
   const char* pszFrom,
   DWORD dwAttrFrom,
   const char* pszTo,
   DWORD dwAttrTo);

inline BOOL RelativePathTo(
   wchar_t* pszPath,
   const wchar_t* pszFrom,
   DWORD dwAttrFrom,
   const wchar_t* pszTo,
   DWORD dwAttrTo);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathRelativePathTo를](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow) 참조하십시오.

## <a name="atlpathremoveargs"></a><a name="removeargs"></a>ATLPath::리무드아르그

이 함수는 [PathRemoveArgs에](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline void RemoveArgs(char* pszPath);
inline void RemoveArgs(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [패스리RemoveArgs를](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw) 참조하십시오.

## <a name="atlpathremovebackslash"></a><a name="removebackslash"></a>ATLPath::제거백슬래시

이 함수는 [PathRemoveBackslash에](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline char* RemoveBackslash(char* pszPath);
inline wchar_t* RemoveBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [패스제거백슬래시를](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw) 참조하십시오.

## <a name="atlpathremoveblanks"></a><a name="removeblanks"></a>ATLPath::제거 공백

이 함수는 [PathRemoveBlanks에](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline void RemoveBlanks(char* pszPath);
inline void RemoveBlanks(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [패스제거블랭크를](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw) 참조하십시오.

## <a name="atlpathremoveextension"></a><a name="removeextension"></a>ATLPath::제거확장

이 함수는 [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline void RemoveExtension(char* pszPath);
inline void RemoveExtension(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [패스제거익스텐션을](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw) 참조하십시오.

## <a name="atlpathremovefilespec"></a><a name="removefilespec"></a>ATLPath::파일 스펙 제거

이 함수는 [PathRemoveFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL RemoveFileSpec(char* pszPath);
inline BOOL RemoveFileSpec(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [패스제거파일스펙을](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw) 참조하십시오.

## <a name="atlpathrenameextension"></a><a name="renameextension"></a>ATLPath::이름 바꾸기확장

이 함수는 [PathRenameExtension에](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL RenameExtension(char* pszPath, const char* pszExt);
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathRenameExtension을](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw) 참조하십시오.

## <a name="atlpathskiproot"></a><a name="skiproot"></a>ATLPath::스킵루트

이 함수는 [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline char* SkipRoot(const char* pszPath);
inline wchar_t* SkipRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathSkipRoot를](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw) 참조하십시오.

## <a name="atlpathstrippath"></a><a name="strippath"></a>ATL패스::스트립패스

이 함수는 [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)에 대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline void StripPath(char* pszPath);
inline void StripPath(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathStripPath를](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw) 참조하십시오.

## <a name="atlpathstriptoroot"></a><a name="striptoroot"></a>ATLPath::스트립토루트

이 함수는 [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)에 대한 오버로드 래퍼입니다.

### <a name="syntax"></a>구문

```
inline BOOL StripToRoot(char* pszPath);
inline BOOL StripToRoot(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathStripToRoot를](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw) 참조하십시오.

## <a name="atlpathunquotespaces"></a><a name="unquotespaces"></a>ATLPath::인용되지 않은 공간

이 함수는 [PathUnquoteSpaces에](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)대한 오버로드된 래퍼입니다.

### <a name="syntax"></a>구문

```
inline void UnquoteSpaces(char* pszPath);
inline void UnquoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 내용은 [PathUnquote공백을](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw) 참조하십시오.
