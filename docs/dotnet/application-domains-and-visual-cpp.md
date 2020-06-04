---
title: 애플리케이션 도메인 및 Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
ms.openlocfilehash: 16c02bb58681ecb241d3552f57e0b05f2d6711b4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208806"
---
# <a name="application-domains-and-visual-c"></a>애플리케이션 도메인 및 Visual C++

`__clrcall` 가상 함수가 있는 경우 vtable은 응용 프로그램 도메인 (appdomain) 당입니다. 하나의 appdomain에서 개체를 만드는 경우 해당 appdomain 내 에서만 가상 함수를 호출할 수 있습니다. 혼합 모드 ( **/clr**)에서는 형식에 `__clrcall` 가상 함수가 없는 경우 프로세스별 vtables이 있습니다. **/Clr: pure** 및 **/clr: safe** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

자세한 내용은 다음을 참조하세요.

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>참고 항목

- [혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)
