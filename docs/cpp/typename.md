---
title: typename
ms.date: 11/04/2016
f1_keywords:
- typename_cpp
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
ms.openlocfilehash: 789bb879922bbd96a04085159205d02fb7f495c8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160686"
---
# <a name="typename"></a>typename

템플릿 정의에서 알 수 없는 식별자가 형식이라는 힌트를 컴파일러에 알려줍니다. 템플릿 매개 변수 목록에서 형식 매개 변수를 지정하는데 사용됩니다.

## <a name="syntax"></a>구문

```
typename identifier;
```

## <a name="remarks"></a>설명

템플릿 정의에서의 이름이 템플릿 인수에 종속되는 정규 이름인 경우 이 키워드를 사용합니다. 정규 이름이 종속적이지 않은 경우 이는 선택사항입니다. 자세한 내용은 [템플릿 및 이름 확인](../cpp/templates-and-name-resolution.md)을 참조 하세요.

**typename** 은 템플릿 선언 또는 정의의 모든 형식에서 사용할 수 있습니다. 템플릿 기본 클래스의 템플릿 인수로 사용되지 않는 한 기본 클래스 목록에서는 허용되지 않습니다.

```cpp
template <class T>
class C1 : typename T::InnerType // Error - typename not allowed.
{};
template <class T>
class C2 : A<typename T::InnerType>  // typename OK.
{};
```

**Typename** 키워드는 템플릿 매개 변수 목록에서 **클래스** 대신 사용할 수도 있습니다. 예를 들어 다음은 의미상 동일합니다.

```cpp
template<class T1, class T2>...
template<typename T1, typename T2>...
```

## <a name="example"></a>예제

```cpp
// typename.cpp
template<class T> class X
{
   typename T::Y m_y;   // treat Y as a type
};

int main()
{
}
```

## <a name="see-also"></a>참고 항목

[템플릿](../cpp/templates-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)
