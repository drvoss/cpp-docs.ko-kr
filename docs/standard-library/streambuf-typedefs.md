---
title: "&lt;streambuf&gt; 형식 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 4abaa093b4fa739602e308ec420299907f4ded3f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; 형식 정의
|||  
|-|-|  
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|  
  
##  <a name="streambuf"></a>  streambuf  
 `char`를 템플릿 매개 변수로 사용하는 `basic_streambuf`의 특수화입니다.  
  
```
typedef basic_streambuf<char, char_traits<char>> streambuf;
```  
  
### <a name="remarks"></a>설명  
 이 형식은 기본 문자 특성을 포함하는 `char` 형식의 요소용으로 특수화된 [basic_streambuf](../standard-library/basic-streambuf-class.md) 템플릿 클래스와 동일한 의미입니다.  
  
##  <a name="wstreambuf"></a>  wstreambuf  
 `wchar_t`를 템플릿 매개 변수로 사용하는 `basic_streambuf`의 특수화입니다.  
  
```
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```  
  
### <a name="remarks"></a>설명  
 이 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_streambuf](../standard-library/basic-streambuf-class.md) 템플릿 클래스와 동일한 의미입니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<streambuf>](../standard-library/streambuf.md)



