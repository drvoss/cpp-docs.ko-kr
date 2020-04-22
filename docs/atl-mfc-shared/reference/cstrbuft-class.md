---
title: CStrBufT 클래스
ms.date: 10/18/2018
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
ms.openlocfilehash: 71d7b6f7d53e9613b1ac26013d73c1dbd1ef0aab
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746932"
---
# <a name="cstrbuft-class"></a>CStrBufT 클래스

이 클래스는 기존 `GetBuffer` `ReleaseBuffer` `CStringT` 개체에 대한 자동 리소스 정리 및 호출을 제공합니다.

## <a name="syntax"></a>구문

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>매개 변수

*TCharType*<br/>
클래스의 문자 `CStrBufT` 유형입니다. 다음 중 하나일 수 있습니다.

- **char** char(ANSI 문자 문자열의 경우)

- **wchar_t(유니코드** 문자 문자열의 경우)

- TCHAR(ANSI 및 유니코드 문자 문자열 모두)

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|PCXSTR|상수 문자열에 대한 포인터입니다.|
|PXSTR|문자열에 대한 포인터입니다.|
|`StringType`|이 클래스 템플릿의 특수화로 버퍼를 조작할 문자열 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CStrBufT:::CStrBufT](#cstrbuft)|문자열 버퍼 개체의 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CStrBufT::설정 길이](#setlength)|연결된 문자열 개체의 문자 버퍼 길이를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CStrBufT::연산자 PCXSTR](#operator_pcxstr)|연결된 문자열 개체의 문자 버퍼에 대한 **const** 포인터를 검색합니다.|
|[CStrBufT::연산자 PXSTR](#operator_pxstr)|연결된 문자열 개체의 character 버퍼에 대한 포인터를 검색합니다.|

### <a name="public-constants"></a>공용 상수

|속성|Description|
|----------|-----------------|
|[CStrBufT::AUTO_LENGTH](#auto_length)|릴리스 시 문자열의 새 길이를 자동으로 결정합니다.|
|[CStrBufT::SET_LENGTH](#set_length)|GetBuffer 시간에 문자열 개체의 길이 설정|

## <a name="remarks"></a>설명

이 클래스는 [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 및 [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)또는 [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) 및 `ReleaseBuffer`에 대한 호출을 대체하기 위한 래퍼 클래스로 사용됩니다.

주로 도우미 클래스로 디자인되어 `CStrBufT` 개발자가 호출 하는 방법 이나 시기에 대 한 걱정 없이 문자열 개체의 character 버퍼로 작업하는 편리한 방법을 제공 `ReleaseBuffer`합니다. 이는 예외 또는 여러 개의 종료 코드 경로의 경우 래퍼 개체가 자연스럽게 범위를 벗어나기 때문에 가능합니다. 소멸자가 문자열 리소스를 해제하도록 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 아실프스트스트.h

## <a name="cstrbuftauto_length"></a><a name="auto_length"></a>CStrBufT::AUTO_LENGTH

릴리스 시 문자열의 새 길이를 자동으로 결정합니다.

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>설명

릴리스 시 문자열의 새 길이를 자동으로 결정합니다. 문자열은 null-종료되어야 합니다.

## <a name="cstrbuftcstrbuft"></a><a name="cstrbuft"></a>CStrBufT:::CStrBufT

버퍼 개체를 생성합니다.

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
버퍼와 연결된 문자열 개체입니다. 일반적으로 개발자는 미리 `CStrBuf` 정의된 타입defs(TCHAR 변형), `CStrBufA` **(char** 변형) 및 `CStrBufW` **(wchar_t** 변형)을 사용합니다.

*nMinLength*<br/>
문자 버퍼의 최소 길이입니다.

*dwFlags*<br/>
문자열 길이가 자동으로 결정되는지 여부를 결정합니다. 다음 중 하나일 수 있습니다.

- AUTO_LENGTH 문자열 길이는 [CSimpleStringT::Release가](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) 호출될 때 자동으로 결정됩니다. 문자열은 null-종료되어야 합니다. 기본값.

- SET_LENGTH 문자열 길이는 [CSimpleStringT::GetBuffer가](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 호출될 때 설정됩니다.

### <a name="remarks"></a>설명

연결된 문자열 개체에 대한 문자열 버퍼를 만듭니다. 생성 하는 동안 [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 또는 [CSimpleStringT::GetBufferSetLength호출](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) 됩니다.

복사 생성자는 **비공개입니다.**

## <a name="cstrbuftoperator-pcxstr"></a><a name="operator_pcxstr"></a>CStrBufT::연산자 PCXSTR

연결된 문자열 개체에 저장된 문자에 C 스타일 문자열로 직접 액세스합니다.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Return Value

문자열의 데이터에 대한 문자 포인터입니다.

### <a name="remarks"></a>설명

문자열 개체의 character 버퍼에 대한 포인터를 반환하려면 이 함수를 호출합니다. 이 포인터로는 문자열 개체의 내용을 변경할 수 없습니다.

## <a name="cstrbuftoperator-pxstr"></a><a name="operator_pxstr"></a>CStrBufT::연산자 PXSTR

연결된 문자열 개체에 저장된 문자에 C 스타일 문자열로 직접 액세스합니다.

```
operator PXSTR() throw();
```

### <a name="return-value"></a>Return Value

문자열의 데이터에 대한 문자 포인터입니다.

### <a name="remarks"></a>설명

문자열 개체의 character 버퍼에 대한 포인터를 반환하려면 이 함수를 호출합니다. 개발자는 이 포인터를 통해 문자열 개체의 내용을 변경할 수 있습니다.

## <a name="cstrbuftpcxstr"></a><a name="pcxstr"></a>CStrBufT::PCXSTR

상수 문자열에 대한 포인터입니다.

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

## <a name="cstrbuftpxstr"></a><a name="pxstr"></a>CStrBufT::PXSTR

문자열에 대한 포인터입니다.

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

## <a name="cstrbuftset_length"></a><a name="set_length"></a>CStrBufT::SET_LENGTH

시간에 `GetBuffer` 문자열 개체의 길이를 설정합니다.

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>설명

GetBuffer 시간에 문자열 개체의 길이를 설정합니다.

[CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 및 [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) 문자열 버퍼 개체가 생성 될 때 호출 됩니다 경우 확인 합니다.

## <a name="cstrbuftsetlength"></a><a name="setlength"></a>CStrBufT::설정 길이

문자 버퍼의 길이를 설정합니다.

```cpp
void SetLength(int nLength);
```

### <a name="parameters"></a>매개 변수

*nLength*<br/>
문자열 개체의 문자 버퍼의 새 길이입니다.

> [!NOTE]
> `CStrBufT`의 생성자 생성자에 지정된 최소 버퍼 길이보다 낮거나 같아야 합니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 버퍼 개체로 표시되는 문자열의 길이를 설정합니다.

## <a name="cstrbuftstringtype"></a><a name="stringtype"></a>CStrBufT::문자열 유형

이 클래스 템플릿의 특수화로 버퍼를 조작할 문자열 형식입니다.

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>설명

`TCharType`은 클래스 템플릿을 전문으로 하는 데 사용되는 문자 유형입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
