---
title: '&lt;istream&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: fc512558969bc25d2b16afa2b93219e13d0b28ca
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425684"
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; 함수

|||
|-|-|
|[swap](#istream_swap)|[ws](#ws)|

## <a name="istream_swap"></a>  swap

두 stream 개체의 요소를 교환합니다.

```cpp
template <class Elem, class Tr>
void swap(
    basic_istream<Elem, Tr>& left,
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>
void swap(
    basic_iostream<Elem, Tr>& left,
    basic_iostream<Elem, Tr>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
스트림입니다.

*오른쪽*\
스트림입니다.

## <a name="ws"></a>  ws

스트림의 공백을 건너뜁니다.

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>매개 변수

*_Istr*\
스트림입니다.

### <a name="return-value"></a>Return Value

스트림입니다.

### <a name="remarks"></a>설명

조작자는 [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **Elem**> > ( [getloc](../standard-library/ios-base-class.md#getloc))에 `ch` 모든 요소를 추출 하 고 삭제 합니다. **is**( **ctype**\< **Elem**>:: **space**, **ch**)가 true입니다.

함수는 요소를 추출하는 동안 파일 끝에 도달하면 [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**)를 호출합니다. *_Istr*를 반환 합니다.

### <a name="example"></a>예제

[ 사용 예제는 ](../standard-library/istream-operators.md#op_gt_gt)operator>>`ws`를 참조하세요.

## <a name="see-also"></a>참고 항목

[\<istream>](../standard-library/istream.md)
