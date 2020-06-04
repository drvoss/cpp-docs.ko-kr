---
title: GetActivationFactory 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
ms.openlocfilehash: 430b4ed3f6a02fd3db2bcab05fbb7f21f5367b5c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213982"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory 함수

템플릿 매개 변수로 지정 된 형식에 대 한 활성화 팩터리를 검색 합니다.

## <a name="syntax"></a>구문

```cpp
template<typename T>
inline HRESULT GetActivationFactory(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
활성화 팩터리의 유형을 지정 하는 템플릿 매개 변수입니다.

*activatableClassId*<br/>
활성화 팩터리에서 생성할 수 있는 클래스의 이름입니다.

*팩토리에서*<br/>
이 작업이 완료 되 면 *T*형식의 활성화 팩터리에 대 한 참조입니다.

## <a name="return-value"></a>반환 값

성공 하면 S_OK 합니다. 그렇지 않으면이 작업이 실패 한 이유를 나타내는 HRESULT 오류가 발생 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임 스페이스:** Windows:: Foundation

## <a name="see-also"></a>참고 항목

[Windows::Foundation 네임스페이스](windows-foundation-namespace.md)
