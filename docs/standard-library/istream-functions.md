---
title: '&lt;istream&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: 3d647c7b05a3868ec0359410cc0e703306b874ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363074"
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; 함수

|||
|-|-|
|[스왑](#istream_swap)|[Ws](#ws)|

## <a name="swap"></a><a name="istream_swap"></a>스왑

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

## <a name="ws"></a><a name="ws"></a>Ws

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

`ch` 조작자는**ctype** \< **Elem**> >(getloc)use_facet [use_facet](../standard-library/basic-filebuf-class.md#open)< 있는 모든 요소를 추출하고 [삭제합니다.](../standard-library/ios-base-class.md#getloc) **is**( **ctype**\< **Elem**>:: **space**, **ch**)가 true임)를 추출하고 삭제합니다.

함수는 요소를 추출하는 동안 파일 끝에 도달하면 [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**)를 호출합니다. *_Istr*반환합니다.

### <a name="example"></a>예제

`ws` 사용 예제는 [operator>>](../standard-library/istream-operators.md#op_gt_gt)를 참조하세요.

## <a name="see-also"></a>참고 항목

[\<아이스트림>](../standard-library/istream.md)
