---
title: _bstr_t::operator +=, +
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
ms.openlocfilehash: b9eddca85d66f4978e1b33299ca655cd880cf45e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181150"
---
# <a name="_bstr_toperator--"></a>_bstr_t::operator +=, +

**Microsoft 전용**

`_bstr_t` 개체의 끝에 문자를 추가하거나 두 문자열을 연결합니다.

## <a name="syntax"></a>구문

```
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

#### <a name="parameters"></a>매개 변수

*s1*<br/>
`_bstr_t` 개체입니다.

*s2*<br/>
멀티바이트 문자열입니다.

*s3*<br/>
유니코드 문자열입니다.

## <a name="remarks"></a>주의

이러한 연산자는 다음과 같이 문자열 연결을 수행합니다.

- **operator + = (**  *s1*  **)** 캡슐화 된 `BSTR` *s1* 의 문자를이 개체의 캡슐화 된 `BSTR`끝에 추가 합니다.

- **operator + (** *s1* **)** 이 개체의 `BSTR`를 *s1*의와 연결 하 여 구성 된 새 `_bstr_t`을 반환 합니다.

- **operator + (** *s2* **&#124;** *s1* **)** 유니코드로 변환 된 멀티 바이트 문자열 *s2*를 *s1*에 캡슐화 된 `BSTR` 연결 하 여 구성 된 새 `_bstr_t`을 반환 합니다.

- **operator + (** *s3* **,** *s1* **)** 유니코드 문자열 s 3을 s *1에서* *캡슐화 된 `BSTR`* 연결 하 여 형성 된 새 `_bstr_t`을 반환 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_bstr_t 클래스](../cpp/bstr-t-class.md)
