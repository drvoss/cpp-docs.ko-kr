---
title: Serialization(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
ms.openlocfilehash: b2dfdcaf1a1f33e89d106d4529ffc9af2d08376b
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545164"
---
# <a name="serialization-ccli"></a>Serialization(C++/CLI)

개별 필드 또는 속성을 포함 하 여 관리 되는 클래스의 Serialization (개체 또는 멤버의 상태를 영구 미디어에 저장 하는 프로세스)은 <xref:System.SerializableAttribute> 및 <xref:System.NonSerializedAttribute> 클래스에서 지원 됩니다.

## <a name="remarks"></a>주의

**SerializableAttribute** 사용자 지정 특성을 관리 되는 클래스에 적용 하 여 전체 클래스를 직렬화 하거나 특정 필드 또는 속성에만 적용 하 여 관리 되는 클래스의 일부를 serialize 합니다. **NonSerializedAttribute** 사용자 지정 특성을 사용 하 여 관리 되는 클래스의 필드 또는 속성을 serialize 하지 않도록 제외 합니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 예제에서는 클래스 `MyClass` 및 `m_nCount`속성이 serializable로 표시 됩니다. 그러나 `m_nData` 속성은 **NonSerialized** 사용자 지정 특성에 의해 표시 된 대로 serialize 되지 않습니다.

### <a name="code"></a>코드

```cpp
// serialization_and_mcpp.cpp
// compile with: /LD /clr
using namespace System;

[ Serializable ]
public ref class MyClass {
public:
   int m_nCount;
private:
   [ NonSerialized ]
   int m_nData;
};
```

### <a name="comments"></a>설명

두 특성 모두 "short name" (**Serializable** 및 **NonSerialized**)을 사용 하 여 참조할 수 있습니다. [특성 적용](/dotnet/standard/attributes/applying-attributes)에서이에 대해 자세히 설명 합니다.

## <a name="see-also"></a>참고 항목

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
