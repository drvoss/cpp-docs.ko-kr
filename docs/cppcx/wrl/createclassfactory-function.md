---
title: CreateClassFactory 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
ms.openlocfilehash: 0467a9a1341e29a61a3b32d999769b01385f641f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214060"
---
# <a name="createclassfactory-function"></a>CreateClassFactory 함수

지정된 클래스의 인스턴스를 생성하는 팩터리를 만듭니다.

## <a name="syntax"></a>구문

```cpp
template<typename Factory>
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(
   _In_ unsigned int *flags,
   _In_ const CreatorMap* entry,
   REFIID riid,
   _Outptr_ IUnknown **ppFactory
) throw();
```

### <a name="parameters"></a>매개 변수

*flags*<br/>
하나 이상의 [RuntimeClassType](runtimeclasstype-enumeration.md) 열거형 값의 조합입니다.

*entry*<br/>
매개 변수 *riid*에 대 한 초기화 및 등록 정보를 포함 하는 [creatormap](creatormap-structure.md) 에 대 한 포인터입니다.

*riid*<br/>
인터페이스 ID에 대 한 참조입니다.

*ppFactory*<br/>
이 작업이 성공적으로 완료 되 면 클래스 팩터리에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="remarks"></a>주의

템플릿 매개 변수 *팩터리가* 인터페이스 `IClassFactory`에서 파생 되지 않으면 어설션 오류가 발생 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** module .h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Wrappers::Details 네임스페이스](microsoft-wrl-wrappers-details-namespace.md)
