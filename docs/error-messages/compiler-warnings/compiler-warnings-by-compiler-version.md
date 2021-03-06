---
title: "컴파일러 버전으로 컴파일러 경고 | Microsoft Docs"
ms.custom: 
ms.date: 01/31/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- warnings, by compiler version
- cl.exe compiler, setting warning options
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f6ee65b1001f0cf651fcbbd68170484cd134aa4
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2018
---
# <a name="compiler-warnings-by-compiler-version"></a>컴파일러 버전으로 컴파일러 경고

컴파일러를 사용 하 여 지정한 버전 이후 도입 된 경고 표시 하지 않을 수는 [/Wv](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션입니다. 이 새 도구 집합 버전을 소개 하 고 일시적으로 새 경고를 표시 하지 않을 때 빌드 프로세스를 관리 하는 데 유용 합니다. 이 옵션 새 오류 메시지를 표시 하지 않습니다. 모든 새 경고를 표시 하지 않는 것이 좋습니다 영구적으로! 항상 가장 높은 일반 경고 수준에서 컴파일하는 것이 좋습니다 __/W4__, 제거 하 고는 __/Wv__ 최대한 빨리 옵션 빌드에 있습니다. 

이러한 버전의 컴파일러에 새로운 경고가 소개 되었습니다.

| 제품 | 컴파일러 버전 번호 |
|-|-|
| Visual C++ 2002 | 13.00.9466 |
| Visual C++ 2003 | 13.10.3077 |
| Visual C++ 2005 | 14.00.50727.762 |
| Visual C++ 2008 | 15.00.21022.08 |
| Visual C++ 2010 | 16.00.40219.01 |
| Visual C++ 2012 | 17.00.51106.1 |
| Visual C++ 2013 | 18.00.21005.1 |
| Visual C++ 2015 RTM | 19.00.23026.0 |
| Visual c + + 2015 업데이트 1 | 19.00.23506.0 |
| Visual c + + 2015 업데이트 2 | 19.00.23918.0 |
| Visual c + + 2015 업데이트 3 | 19.00.24215.1 |
| Visual C++ 2017 RTM | 19.10.24903.0 |
| Visual c + + 2017 15.1 버전 | 19.10.25017.0 |
| Visual c + + 2017 15.3 버전 | 19.11.25506.0 |
| Visual c + + 2017 15.5 버전 | 19.12.25827.0 |

주요 번호만, 주 및 부 번호 또는 주, 부를 지정 하 고 빌드 번호를 수는 __/Wv__ 옵션입니다. 컴파일러 버전 지정된 된 수로 시작 하는 일치 하는 모든 경고를 보고 하 고 지정된 된 숫자 보다 큰 버전에 대 한 모든 경고를 표시 하지 않습니다. 예를 들어 __/Wv:17__ 또는 그 이전 버전의 Visual Studio 2012에 도입 된 모든 경고를 보고 하 고 Visual Studio 2013 (버전 18)에서 이상 컴파일러에 의해 정의 된 모든 경고를 표시 하지 않습니다. Visual Studio 2015에서 도입 된 경고를 표시 하지 않는 업데이트 2 이상 버전에서는 사용할 수 있습니다 및 __/Wv:19.00.23506__합니다. 사용 하 여 __/Wv:19.11__ Visual Studio 2017 15.5, 버전 이전에 Visual Studio의 모든 버전에서 도입 되었지만 Visual Studio 2017 15.5 이상 버전에에서 도입 된 경고를 표시 하지 않습니다.이 모든 경고를 보고 합니다.

다음 섹션에서는 목록을 사용 하 여 표시 하지 않을 수 있는 Visual c + +의 각 버전에서 도입 된 경고는 __/Wv__ 컴파일러 옵션입니다. __/Wv__ 옵션 이전의 지정 된 버전의 컴파일러는 나열 되지 않은 경고 표시 하지 않을 수 있습니다.

## <a name="warnings-introduced-in-visual-c-2017-version-155-compiler-version-1912258270"></a>Visual c + + 2017 15.5 (컴파일러 버전 19.12.25827.0) 버전에에서 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:19.11__합니다.

|||
|-|-|
C5044|명령줄 옵션에 인수가 *옵션* 경로 가리키는 '*경로*' 존재 하지 않는

## <a name="warnings-introduced-in-visual-c-2017-version-153-compiler-version-1911255060"></a>Visual c + + 2017 15.3 (컴파일러 버전 19.11.25506.0) 버전에에서 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:19.10__합니다.

|||
|-|-|
C4843|'*type1*': 배열 또는 함수 형식에 대 한 참조의 예외 처리기에 연결할 수 없습니다, 사용 하 여 '*type2*' 대신
C4844|' 모듈 내보내기 *모듈*;'는 이제 모듈 인터페이스를 선언 하기 위한 기본 구문
C5039|'*함수*': 포인터 또는 함수를 잠재적으로 throw 하는 참조-EHc 아래 extern C 함수에 전달 합니다. 이 함수는 예외를 throw 하는 경우 정의 되지 않은 동작이 발생할 수 있습니다.
C5040|동적 예외 사양은 C + + 14에만 및 이전 버전; 올바른지 noexcept(false)로 처리 하는 방법
C5041|'*정의*': constexpr 정적 데이터 멤버에 대 한 아웃오브 라인 정의 필요 하지 않으며 C + + 17에 사용 되지 않음
C5042|'*선언*': 함수 선언은 블록 범위에서 표준 c + +에서 '인라인'이 지정 된 일 수 없습니다. '인라인' 지정자를 제거 합니다.
C5043|'*사양*': 예외 사양이 이전 선언과 일치 하지 않습니다

## <a name="warnings-introduced-in-visual-c-2017-version-151-compiler-version-1910250170"></a>Visual c + + 2017 15.1 (컴파일러 버전 19.10.25017.0) 버전에에서 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:19.10.24903__합니다.

|||
|-|-|
C4597|정의 되지 않은 동작이: *설명*
C4604|'*형식*': 유효한 복사 생성자가 필요 네이티브 및 관리 되는 경계 값으로 인수를 전달 합니다. 그렇지 않으면 런타임 동작이 정의 되지 않습니다.
C4749|조건에 따라 지원: *설명*
C4768|링크 사양이 이전 __declspec 특성이 무시 됩니다.
C4834|'nodiscard' 특성을 가진 함수의 반환 값 삭제
C4841|비표준 확장이 사용 됨: *확장*
C4842|다중 상속을 사용 하 여 형식에 적용 하는 'offsetof'의 결과 컴파일러 버전 간에 일관 되도록 보장 되지
C4869|'nodiscard'는 클래스, 열거형 및 void가 아닌 반환 형식이 있는 함수에만 적용 될 수 있습니다.
C5033|'*저장소 클래스*'는 더 이상 지원 되는 저장소 클래스
C5034|내장 함수의 사용 하 여 '*내장*' 하면 함수 *함수* 게스트 코드로 컴파일할 수를
C5035|기능을 사용 하 여 '*기능*' 하면 함수 *함수* 게스트 코드로 컴파일할 수를
C5036|/hybrid:x86arm64로 컴파일할 때 varargs 함수 포인터 변환이 있습니다. '*type1*'to'*type2*'
C5037|'*멤버-함수*': 클래스 템플릿의 멤버는 아웃오브 라인 정의 기본 인수를 가질 수 없습니다
C5038|데이터 멤버 '*member1*'초기화 될 데이터 멤버 뒤'*member2*'

## <a name="warnings-introduced-in-visual-c-2017-rtm-compiler-version-191024903"></a>Visual c + + 2017 RTM (컴파일러 버전 19.10.24903)에서 시작 하는 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:19.00__합니다.

|||
|-|-|
C4468|'fallthrough': 특성 뒤에 야 case 레이블 또는 기본 레이블
C4698|'*기능*' 제거 나중에 업데이트 되었거나 평가 목적 으로만 사용 및 변경 될 수 있습니다.
C4839|클래스의 비표준 사용*클래스*' variadic 함수에 대 한 인수로
C4840|클래스의 이식성 사용*클래스*' variadic 함수에 대 한 인수로

## <a name="warnings-introduced-in-visual-c-2015-update-3-compiler-version-1900242151"></a>Visual c + + 2015 업데이트 3 (컴파일러 버전 19.00.24215.1)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:19.00.23918__합니다.

|||
|-|-|
C4467|ATL 특성의 사용은 사용 되지 않습니다.
C4596|'*이름*': 멤버 선언의 정규화 된 이름이 잘못 되었습니다.
C4598|' #include \< *헤더*\>': 헤더 번호 *번호* 에 *소스* 일치 하지 않습니다 *소스* 해당 위치
C4599|'*인수*': *소스* 인수 번호 *번호* 일치 하지 않습니다 *소스*

## <a name="warnings-introduced-in-visual-c-2015-update-2-compiler-version-1900239180"></a>Visual c + + 2015 업데이트 2 (컴파일러 버전 19.00.23918.0)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:19.00.23506__합니다.

|||
|-|-|
C4466|코 루틴 힙 생략을 수행할 수 없습니다.
C4595|'*클래스*': 멤버가 아닌 연산자 new 또는 delete 함수 선언할 수 없습니다. 인라인
C4828|파일 오프셋 0에서 시작 문자가 x*값* 현재 소스 문자 집합에서 사용할 수 없는 (코드 페이지 *번호*).
C4868|컴파일러는 중괄호로 묶인된 이니셜라이저 목록에서 왼쪽에서 오른쪽 평가 순서를 적용할 수 없습니다.

## <a name="warnings-introduced-in-visual-c-2015-update-1-compiler-version-1900235060"></a>Visual c + + 2015 업데이트 1 (컴파일러 버전 19.00.23506.0)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:19.00.23026__합니다.

|||
|-|-|
C4426|헤더를 포함 한 후 변경 된 최적화 플래그 #pragma optimize() 되었기 때문일 수 있습니다.
C4654|미리 컴파일된 헤더의 앞에 배치 하는 코드는 무시 됩니다. 미리 컴파일된 헤더에 코드를 추가 합니다.
C5031|#pragma warning(pop): 일치 하지 않을 수, 다른 파일에서 푸시된 경고 상태를 팝 합니다.
C5032|없는 해당 #pragma warning(pop) #pragma warning (push)를 발견 했습니다.

## <a name="warnings-introduced-in-visual-c-2015-rtm-compiler-version-1900230260"></a>Visual c + + 2015 RTM (컴파일러 버전 19.00.23026.0)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/wv: 18__합니다.

|||
|-|-|
C4427|'*오류*': 상수 분할을 정의 되지 않은 동작이의 오버플로
C4438|'*형식*': 호출할 수 없습니다 안전 하 게 /await: clrcompat 모드입니다. 경우 '*형식*' CLR로 호출을 CLR 헤드가 손상에서 될 수 있습니다
C4455|' 연산자 *이름*': 밑줄로 시작 하지 않는 리터럴 접미사 식별자는 예약 되어 있습니다.
C4456|선언 '*이름*' 이전 로컬 선언을 숨깁니다.
C4457|선언 '*이름*' 숨깁니다 함수 매개 변수
C4458|선언 '*이름*' 클래스 멤버를 숨깁니다
C4459|선언 '*이름*' 전역 선언을 숨깁니다.
C4462|'*형식*': 형식의 GUID를 확인할 수 없습니다. 프로그램은 런타임에 실패할 수 있습니다.
C4463|오버플로. 할당 *값* 값만 포함할 수 있는 비트 필드에 *값* 를 *값*
C4473|'*함수*': 서식 문자열에 대 한 전달 된 인수가 부족 합니다.
C4474|'*함수*': 서식 문자열에 전달 된 인수가 너무 많습니다.
C4475|'*함수*': 길이 한정자 '*한정자*'형식 필드 문자를 사용할 수 없습니다'*문자*' 서식 지정자
C4476|'*함수*': 알 수 없는 형식 필드 문자 '*문자*' 서식 지정자
C4477|'*함수*': 서식 문자열 '*문자열*'형식의 인수를 사용 해야'*형식*', 하지만 variadic 인수 *번호* 형식이 '*형식*'
C4478|'*함수*': 위치 및 비 위치 자리 표시자는 동일한 형식 문자열에 혼합할 수 없고
C4494|'*형식*': __declspec(allocator) 함수 반환 형식이 때문에 아니면 무시 한 포인터 또는 참조
C4495|비표준 확장이 사용 '_': 명시적 기본 클래스 이름으로 대체
C4496|비표준 확장 'for each' 사용: 했습니다. ranged-for 문으로 대체
C4497|비표준 확장이 사용 'sealed': 'final'으로 대체
C4498|비표준 확장이 사용 됨: '*확장*'
C4499|'*특수화*': 명시적 특수화 (무시 됨)는 저장소 클래스를 가질 수 없습니다
C4576|괄호로 묶인 이니셜라이저 목록이 옵니다 형식은 비표준 명시적 형식 변환 구문
C4577|' noexcept' 처리 모드를 지정 합니다; 예외가 함께 사용 예외 시 종료가 보장 되지 않습니다. /EHsc를 지정 합니다.
C4578|'abs':에서 변환 '*형식*'to'*형식*', 데이터 손실을 (= 호출을 '*이름*' 또는 #include <cmath>?)
C4582|'*형식*': 생성자가 암시적으로 호출 되지 않습니다
C4583|'*형식*': 소멸자가 암시적으로 호출
C4587|'*형식*': 동작 변경: 생성자가 더 이상 암시적으로 호출
C4588|'*형식*': 동작 변경: 소멸자가 더 이상 암시적으로 호출 되 고 없습니다.
C4589|추상 클래스의 생성자*형식*'가상 기본 클래스에 대 한 이니셜라이저를 무시'*형식*'
C4591|'constexpr' 호출 깊이 제한 *번호* 초과 (/ constexpr:depth<NUMBER>)
C4592|'*형식*': 기호가 동적으로 됩니다 (구현 제한)를 초기화 합니다.
C4593|'*형식*': 'constexpr' 호출 실행 단계 제한의 *값* 을 초과 했습니다; /constexpr:steps를 사용 하 여<NUMBER> 도를 늘리려면
C4647|동작 변경: __is_pod (*형식*) 이전 버전에 서로 다른 값
C4648|표준 특성 'carries_dependency'는 무시 됩니다.
C4649|특성이이 컨텍스트에서 무시 됩니다.
C4753|포인터;의 범위를 찾을 수 없습니다. 무시 MPX 내장 함수
C4771|범위는 단순한 포인터를 사용 하 여 만들어야 무시 MPX 내장 함수
C4774|'*설명*': 서식 문자열 인수에 필요한 *번호* 이 문자열 리터럴
C4775|형식 문자열에 사용 되는 비표준 확장 '*문자열*'함수의'*함수*'
C4776|' %*문자*'함수의 서식 문자열에서 허용 되지 않는'*함수*'
C4777|'*설명*': 서식 문자열 '*문자열*'형식의 인수를 사용 해야'*형식*', 하지만 variadic 인수 *번호* 형식이 '*형식*'
C4778|'*설명*': 서식 문자열을 종결 되지 않은 '*문자열*'
C4838|변환에서 '*형식*'to'*형식*' 범위가 좁은
C5022|'*형식*': 지정 된 여러 명의 이동 생성자
C5023|'*형식*': 지정 된 여러 명의 이동 할당 연산자
C5024|'*선언*': 이동 생성자가 암시적으로 삭제 된 것으로 정의 됩니다
C5025|'*선언*': 이동 할당 연산자가 암시적으로 삭제 된 것으로 정의 됩니다
C5026|'*형식*': 이동 생성자가 암시적으로 삭제 된 것으로 정의 됩니다
C5027|'*형식*': 이동 할당 연산자가 암시적으로 삭제 된 것으로 정의 됩니다
C5028|'*이름*': 이전 선언에 지정 된 맞춤 (*번호*) 정의에 지정 되지 않은
C5029|비표준 확장이 사용 됨: 변수, 데이터 멤버 및 태그 형식에만에 c + +의 맞춤 특성 적용
C5030|특성 '*특성*' 인식 되지 않습니다

## <a name="warnings-introduced-in-visual-c-2013-compiler-version-1800210051"></a>Visual c + + 2013 (컴파일러 버전 18.00.21005.1)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:17__합니다.

|||
|-|-|
C4301|'*형식*': 재정의 가상 함수에서 다른만 '*선언*' const/volatile 한정자
C4316|'*형식*': 힙에 할당 된 개체를 정렬할 수 있습니다 *번호*
C4380|'*형식*': 기본 생성자는 사용 되지 않을 수 없습니다
C4388|'*토큰*': signed 또는 unsigned 일치 하지 않습니다.
C4423|'std:: bad_alloc': 클래스에 의해 발생 합니다 ('*형식*') 선에 *번호*
C4424|에 대 한 catch '*형식*'앞 에'*형식*' 줄에 *번호*; 예측할 수 없는 'std:: bad_alloc' throw 되 면 동작이 발생할 수 있습니다
C4425|SAL 주석은 '...'에 적용할 수 없습니다.
C4464|include에 상대 경로 포함 '..'
C4575|와 호환 되지 않는 ' __vectorcall'는 ' / clr' 옵션: '__stdcall'으로 변환
C4609|'*형식*'기본 인터페이스에서 파생'*형식*'유형에'*형식*'. 에 대 한 다른 기본 인터페이스를 사용 하 여 '*형식*', 또는 기본/파생 관계를 중단 합니다.
C4754|비교에 사용 된 산술 연산의 변환 규칙 *설명*(*번호*) 분기 하나를 실행할 수 없음을 의미 합니다. 캐스트 '*형식*'to'*형식*' (또는 비슷한 형식의 *번호* 바이트)입니다.
C4755|비교에 사용 된 산술 연산의 변환 규칙 *설명*(*번호*) 인라인 된 함수에서 분기 하나를 실행할 수 없음을 의미 합니다. 캐스트 '*형식*'to'*형식*' (또는 비슷한 형식의 *번호* 바이트)입니다.
C4767|섹션 이름 '*이름*' 8 자 보다 긺 및 링커에서 잘립니다
C4770|enum 유효성을 부분적으로 검사 '*이름*' 인덱스로 사용
C4827|공용 'ToString' 메서드 매개 변수가 0 virtual로 표시 해야 하 고 재정의
C4882|concurrency:: parallel_for_each를 비 const 호출 연산자와 함수에 전달 되지 않음
C4973|'*형식*': 사용 되지 않는 것으로 표시
C4974|'*형식*': 사용 되지 않는 것으로 표시
C4981|Warbird: 작동 '*선언*' 아니라 __forceinline로 표시 인라인 예외 의미 체계를 포함 하기 때문에
C4990|Warbird: *메시지*
C4991|Warbird: 작동 '*선언*' __forceinline로 있으므로 인라인이 아니라 표시의 인라인 보호 수준이 부모 보다 큽니다.
C4992|Warbird: 작동 '*선언*' 아니라 __forceinline로 표시 인라인 보호할 수 없는 인라인 어셈블리를 포함 하기 때문에

## <a name="warnings-introduced-in-visual-c-2012-compiler-version-1700511061"></a>Visual c + + 2012 (컴파일러 버전 17.00.51106.1)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:16__합니다.

|||
|-|-|
C4330|특성 '*특성*'section'에 대 한*섹션*' 무시
C4415|duplicate __declspec(code_seg('*name*'))
C4416|빈 문자열을 포함 하는 code_seg: 무시
C4417|명시적 템플릿 인스턴스화가 code_seg 가질 수 없습니다: 무시
C4418|code_seg enum에서 무시
C4419|'*이름*'에 private ref 클래스에 적용 될 때 영향을 주지 않습니다'*형식*'.
C4435|'*형식*': 가상 기본으로 인해/v d 2의 개체 레이아웃이 변경 됩니다 '*형식*'
C4436|가상 기본 사이의 dynamic_cast '*형식*'to'*형식*' 생성자 또는 소멸자가 부분적으로 생성 된 개체와 함께 실패할 수 있습니다
C4437|가상 기본 사이의 dynamic_cast '*형식*'to'*형식*' 일부 컨텍스트에서 실패할 수 있습니다
C4443|pragma 매개 변수는 '0', '1' 또는 '2'
C4446|'*형식*': 멤버를 매핑할 수 없습니다 '*이름*'이 형식에 형식 이름으로 충돌 하기 때문입니다. 메서드가 변경 되어 '*이름*'
C4447|스레딩 모델이 없는 'main' 시그니처입니다. 사용 하는 것이 좋습니다. ' int main (platform:: array\<platform:: string ^ > ^ args)'입니다.
C4448|'*형식*' 메타 데이터에 지정 된 기본 인터페이스를 제공 하지 않습니다. 선택 하는 데: '*형식*'는 런타임에 실패할 수 있습니다.
C4449|'*형식*' unsealed 형식은 '[WebHostHidden]'로 표시 되어야 합니다
C4450|'*형식*'로 표시 해야 '[WebHostHidden]'에서 파생 되기 때문 에'*형식*'
C4451|'*형식*': ref 클래스의 사용*형식*' 내부 여러 컨텍스트에서 개체가 잘못 마샬링될이 컨텍스트에서 발생할 수 있습니다
C4452|'*형식*': public 형식은 전역 범위에서 일 수 없습니다. 출력.winmd 파일 이름의 자식인 네임 스페이스에는 것이 있어야 합니다.
C4453|'*형식*': '[WebHostHidden]' 형식을 해야 하지 않은 public 형식의 게시 된 표면에 사용할 수 없습니다 '[WebHostHidden]'
C4454|'*형식*' 없이 [defaultoverload] 지정 된 입력된 매개 변수 수가 이상으로 오버 로드 됩니다. 선택 '*선언*' 기본 오버 로드로
C4471|'*이름*': 범위가 지정 되지 않은 열거형의 정방향 선언에 (int로 가정)는 내부 형식이 있어야 합니다.
C4472|'*이름*'가 네이티브 열거형: 관리 되 는/WinRT 열거형을 선언 하려면 액세스 지정자 (전용/공용)를 추가 합니다.
C4492|'*형식*': 일치 기본 ref 클래스 메서드 '*형식*', 하지만 'override'로 표시 되지 않습니다
C4493|삭제 식은 효과가 없습니다 소멸자 '*형식*' 'public' 액세스가 없습니다
C4585|'*형식*': A WinRT 'public ref 클래스' sealed 여야 하거나 또는 기존의에서 파생 unsealed 클래스
C4586|'*형식*': public 형식은 'Windows' 라는 최상위 네임 스페이스에서 선언할 수 없습니다
C4695|#pragma execution_character_set: '*인수*' 지원 되는 인수가 아닙니다: ' u t F-8'을 현재만 지원 됩니다
C4703|잠재적으로 초기화 되지 않은 로컬 포인터 변수 '*이름*' 사용
C4728|/Yl-옵션이 PCH 참조가 필요 하기 때문에 무시 됩니다.
C4745|volatile 액세스 '*이름*' 크기로 인해 인식 될 수 없습니다
C4746|volatile 액세스 '*이름*' /volatile:\<iso\|ms > __iso_volatile_load/store 내장 함수를 사용 하 여 고려 설정;
C4872|concurrency:: parallel_for_each에 대해 호출 그래프를 컴파일하는 경우를 검색 하는 0으로 부동 소수점 나누기: '*설명*'
C4880|캐스팅 '*형식*'to'*형식*': 포인터 또는 참조에서 상수 성을 캐스팅 하면 amp 제한 함수에 정의 되지 않은 동작이 발생할 수 있습니다
C4881|생성자 및/또는 소멸자가 호출 되지 것입니다 tile_static 변수에 대 한 '*형식*'
C4966|'*설명*'가 지원 되지 않는 세그먼트 이름이 무시 된 __code_seg 주석이 있습니다.
C4988|'*형식*': 변수가 클래스/함수 범위 외부 선언
C4989|'*설명*': 형식에 충돌 하는 정의 합니다.

## <a name="warnings-introduced-in-visual-c-2010-compiler-version-16004021901"></a>Visual c + + 2010 (컴파일러 버전 16.00.40219.01)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:15__합니다.

|||
|-|-|
C4352|'*이름*': 이미 정의 된 내장 함수
C4573|사용 '*형식*' 하려면 컴파일러가 'this' 요소가이 있 캡처할 현재 기본 캡처 모드에서 허용 되지
C4574|'*이름*'같이 정의 됩니다. ' 0': =을 사용 하 여 ' #if *이름*'?
C4689|'*문자*': #pragma detect_mismatch에 지원 되지 않는 문자; #pragma 무시
C4751|/arch AVX 플래그 intel (r) 스트리밍 SIMD 확장 인라인 ASM 내에 있는에 적용 되지 않습니다.
C4752|intel (r) Advanced Vector Extensions;를 찾을 수합니다 적절 한 /arch AVX 플래그를 사용 하는 것이 좋습니다.
C4837|발견 된 삼중 자: '?? *문자*'교체'*문자*'
C4986|'*선언*': 예외 사양이 이전 선언과 일치 하지 않습니다
C4987|비표준 확장명 사용: 'throw (...)'

## <a name="warnings-introduced-in-visual-c-2008-compiler-version-15002102208"></a>Visual c + + 2008 (컴파일러 버전 15.00.21022.08)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:14__합니다.

|||
|-|-|
C4396|'*형식*': friend 선언이 함수 템플릿의 특수화를 참조 하는 경우 인라인 지정자를 사용할 수 없습니다
C4413|'*선언*': 생성자가 종료 후에 유지 하지 않는 임시 참조 멤버가 초기화는
C4491|'*설명*': IDL 버전 형식이 잘못에
C4603|'*이름*': 매크로가 정의 되지 않았거나 미리 컴파일된 헤더 사용 후 정의가 다릅니다
C4627|'*설명*': 미리 컴파일된 헤더 사용을 찾을 때 건너뛰었습니다
C4750|'*설명*': 루프에 인라이닝 된 _alloca () 함수
C4910|'*형식*': '__declspec (dllexport)' 및 'extern' 명시적 인스턴스화에서 호환 되지 않습니다.
C4985|'*선언*': 이전 선언에 특성이 없습니다.

## <a name="warnings-introduced-in-visual-c-2005-compiler-version-140050727762"></a>Visual c + + 2005 (컴파일러 버전 14.00.50727.762)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:13__합니다.

|||
|-|-|
C4000|알 수 없는 경고 하십시오 Visual c + + 도움말 메뉴에서 [기술 지원] 명령을 선택 하거나 기술 지원 도움말 파일에 대 한 자세한 내용은
C4272|'*형식*': __declspec (dllimport) 표시; 함수를 가져올 때 네이티브 호출 규칙을 지정 해야 합니다.
C4333|'*식*': 오른쪽 시프트 횟수가 너무 커 데이터가 손실
C4334|'*식*': 32 비트 시프트의 결과가 암시적으로 64 비트로 변환 (64 비트 시프트를 사용 했습니다.)
C4335|Mac 파일 형식이 발견 되었습니다: 하십시오 소스 파일을 DOS 나 UNIX 형식 변환
C4342|동작 변경: '*형식*' 호출 되었지만 이전 버전에서는 멤버 연산자가 호출
C4350|동작 변경: '*선언*'대신 호출'*선언*'
C4357|대리자에 대 한 형식 인수 목록에 있는 매개 변수 배열 인수 '*선언*'생성할 때 무시'*형식*'
C4358|'*식*': 결합된 대리자의 반환 형식은 'void' 이며 반환 되는 값 정의 되지 않습니다.
C4359|'*형식*': 맞춤 지정 자가 실제 맞춤 보다 작으면 (*번호*), 무시 됩니다.
C4362|'*형식*': 8 바이트 보다 큰 맞춤 CLR에서 지원 되지 않습니다
C4364|#using 어셈블리에 대 한 '*이름*'에서 이전에 표시 *설명*(*번호*); as_friend 특성 없이 as_friend 적용 되지 않습니다
C4365|'*식*': 변환할 '*형식*'to'*형식*', signed 또는 unsigned 일치 하지 않습니다.
C4366|단항의 결과가 '*연산자*' 연산자는 정렬 되지 않을 수 있습니다
C4367|변환에서 '*형식*'to'*형식*' 데이터 형식 잘못 맞춤 예외가 발생할 수 있습니다
C4368|정의할 수 없습니다 '*이름*의 멤버인 관리 되 는' 있는 그대로'*형식*': 혼합된 형식은 지원 되지 않습니다
C4369|'*형식*': 열거자 값 '*번호*'로 나타낼 수 없습니다'*형식*', 값은 '*번호*'
C4374|'*선언*': 인터페이스 메서드가 가상 메서드에서 구현 하지 것입니다. '*선언*'
C4375|public이 아닌 메서드 '*선언*'를 재정의 하지 않습니다'*선언*'
C4376|액세스 지정자 '*지정자*:'은 더 이상 지원:를 사용 하십시오 '*지정자*:' 대신
C4377|네이티브 형식은 기본적으로 private입니다. -d1PrivateNativeTypes는 사용 되지 않습니다.
C4378|이니셜라이저; 실행에 대 한 함수 포인터 얻어야 합니다. resolvemethodhandle
C4379|버전 *버전* 공용 언어 런타임에서이 컴파일러에서 지원 되지 않습니다. 이 버전을 사용 하 여 예기치 않은 결과가 발생할 수 있습니다.
C4381|'*선언*': 인터페이스 메서드가 public이 아닌 방법으로 구현 하지 것입니다. '*선언*'
C4382|throw '*형식*': __clrcall 소멸자 또는 복사 생성자 인 형식이 /clr에서 낼 수 있습니다: 순수 모듈
C4383|'*형식*': 핸들 역참조의 의미가 변경할 수는 사용자 정의 하는 경우 '*연산자*' 연산자가; 연산자는 피연산자에 대 한 명시적 정적 함수로 작성
C4384|#pragma '*지시문*' 전역 범위에만 사용 해야
C4393|'*형식*': const 영향을 주지 않습니다 *설명* 데이터 멤버; 무시
C4394|'*형식*': appdomain 별 기호는 __declspec로 표시할 수 없습니다 (*값*)
C4395|'*형식*': 멤버 함수가 initonly 데이터 멤버의 복사본에서 호출 됩니다. '*형식*'
C4397|DefaultCharSetAttribute는 무시 됩니다.
C4398|'*형식*': appdomain이 여러 개 프로세스별 전역 개체가 제대로 작동 하지 않으면 __declspec (appdomain)을 사용 하는 것이 좋습니다.
C4399|'*형식*': __declspec로 프로세스별 기호를 표시 하지 말아야 (*값*) /clr으로 컴파일하는 경우: 순수
C4400|'*형식*':이 형식에 대해 const/volatile 한정자는 지원 되지 않습니다
C4412|'*선언*': 함수 시그니처에 형식 '*형식*'; C + + 개체는 순수 코드 간에 전달 하는 안전 하지 않은 혼합형 / 네이티브는입니다.
C4429|가능한 불완전 하거나 형식이 잘못 된 유니버설 문자 이름
C4430|형식 지정자가 없습니다. int로 가정합니다. 참고: c + + 기본 int를 지원 하지 않습니다.
C4431|형식 지정자가 없습니다. int로 가정합니다. 참고: C에서는 더 이상 기본 int를 지원하지 않습니다.
C4434|정적 생성자는 private 액세스 가능성이; 있어야 합니다. private 액세스로 변경
C4439|'*형식*': 서명에 관리 되는 형식과 함수 정의는 __clrcall 호출 규칙이 있어야 합니다.
C4441|호출 규칙의 '*규칙*' 무시 됩니다. '*규칙*'를 대신 사용
C4445|'*선언*': 관리 되 는/WinRT 형식에 가상 메서드는 전용일 수 없습니다.
C4460|CLR/WinRT 연산자 '*형식*', 참조로 매개 변수를 전달 합니다. CLR/WinRT 연산자 '*연산자*'c + + 연산자에서 다른 의미 체계의 '*연산자*', 값으로 전달 하 시겠습니까?
C4461|'*형식*':이 클래스에 종료 자가 '! *형식*' 소멸자가 되지 않은 있지만 ' ~*형식*'
C4470|부동 소수점 제어 pragma /clr에서 무시 됩니다.
C4480|비표준 확장이 사용 됨: 열거형에 대 한 기본 형식 지정 '*형식*'
C4481|비표준 확장이 사용 됨: 재정의 지정자 '*지정자*'
C4482|비표준 확장이 사용 됨: 열거형 '*형식*' 정규화 된 이름에 사용 되는
C4483|구문 오류: c + + 키워드 필요 합니다.
C4484|'*형식*': 일치 기본 ref 클래스 메서드 '*형식*', 하지만 'virtual', 'new' 또는 'override';로 표시 되지 않습니다 'new' (및 'virtual' 아님) 가정
C4485|'*형식*': 일치 기본 ref 클래스 메서드 '*형식*', 하지 않으면이 '표시 된 new' 또는 'override'; 'new' (및 'virtual') 가정
C4486|'*형식*': ref 클래스 또는 값 클래스의 전용 가상 메서드를 'sealed'으로 표시
C4487|'*형식*': 일치 된 상속 된 비가상 메서드 '*형식*' 명시적으로 표시 되어야 'new'
C4488|'*형식*': 필요 '*키워드*'인터페이스 메서드를 구현 하는 키워드'*형식*'
C4489|'*키워드*': 인터페이스 메서드를 사용할 수 없습니다 '*이름*'; 재정의 지정자는 ref 클래스와 값 클래스 메서드에만 사용할 수
C4490|'*키워드*': 재정의 지정자;의 잘못 된 사용 '*형식*' 기본 ref 클래스 메서드는 일치 하지 않습니다
C4538|'*형식*':이 형식에 대해 const/volatile 한정자는 지원 되지 않습니다
C4559|'*형식*': 재정의; 함수 향상 __declspec (*값*)
C4565|'*형식*': 재정의; 기호 __declspec로 이전에 선언 되었습니다 (*값*)
C4566|유니버설 문자 이름으로 표현 되는 문자 '*문자*' 현재 코드 페이지에서 표현할 수 없는 (*번호*)
C4568|'*형식*': 멤버가 명시적 재정의의 시그니처와 일치
C4569|'*형식*': 멤버가 명시적 재정의의 시그니처와 일치
C4570|'*형식*': 명시적으로 선언 되지 추상 않았지만 추상 함수를가지고
C4571|변경; Visual c + + 7.1부터 catch (...) 의미 체계를 알림: 구조적된 예외 (SEH) 변경 되었습니다.
C4572|'...'를 사용, /clr [ParamArray] 특성은 사용 되지 않습니다. 대신
C4580|[attribute]는 사용 되지 않습니다. 대신 지정 *지정*Attribute를 기본 클래스로
C4581|사용 되지 않는 동작: ' "*이름*"' 아래 템플릿으로 바뀝니다 '*이름*' 프로세스 특성
C4606|#pragma 경고: '*번호*' 무시 됩니다. 코드 분석 경고가 경고 수준과 연결 되어 있지 않습니다.
C4631|MSXML 또는 XPath를 사용할 수 없습니다. XML 문서 주석이 처리되지 않습니다. *description*
C4632|XML 문서 주석: *설명* -액세스 거부: *설명*
C4633|XML 문서 주석을*설명*: 오류: *설명*
C4634|XML 문서 주석을*설명*: 적용할 수 없습니다: *설명*
C4635|XML 문서 주석을*설명*: 잘못 된 형식의 XML: *설명*
C4636|XML 문서 주석을*설명*: 태그에 비어 있지 않은 필요 '*설명*' 특성입니다.
C4637|XML 문서 주석을*설명*: <include> 태그가 삭제 되었습니다. *description*
C4638|XML 문서 주석을*설명*: 알 수 없는 기호에 참조 '*설명*'.
C4639|MSXML 오류, XML 문서 주석이 처리 되지 것입니다. *description*
C4641|XML 문서 주석에 모호한 상호 참조가 있습니다. 
C4678|기본 클래스*선언*'인덱서보다 접근성 은'*이름*'
C4679|'*설명*': 멤버를 가져올 수 없습니다
C4687|'*형식*': 봉인된 추상 클래스는 인터페이스를 구현할 수 없습니다 '*형식*'
C4688|'*이름*': 제약 조건 목록에 어셈블리 전용 형식 '*선언*'
C4690|[ emitidl ( pop ) ]: 푸시 횟수 보다 팝
C4691|'*형식*': 참조 되지 않는 참조 형식에서 예상 된 *모듈* '*설명*'를 대신 사용 하는 현재 변환 단위에 정의 된 형식
C4692|'*이름*': 전용이 아닌 멤버의 시그니처에 어셈블리 전용 네이티브 형식 '*선언*'
C4693|'*형식*': 봉인된 추상 클래스는 인스턴스 멤버를 가질 수 없습니다*이름*'
C4694|'*형식*': 봉인된 추상 클래스는 기본 클래스 '를 사용할 수 없습니다*형식*'
C4720|인라인 어셈블러 보고서: '*설명*'
C4721|'*설명*': 내장 함수로 사용할 수 없음
C4722|'*설명*': 소멸자 반환 하지 않습니다. 잠재적인 메모리 누수
C4726|ARM arch4/4T에서는 ' < _ f > 또는 < spsr_f >' 치 값과 함께
C4727|명명 된 PCH *이름* 에 타임 스탬프가 동일한 *이름* 및 *이름*합니다.  첫 번째 PCH를 사용합니다.
C4729|선형 그래프 기반 경고에 사용하기에는 함수가 너무 큽니다.
C4730|'*설명*': _m64 혼합 및 부동 소수점에 잘못 된 코드 식으로 인해 수
C4731|'*설명*': 프레임 포인터 레지스터가 '*등록*' 인라인 어셈블리 코드에 의해 수정
C4732|내장 '*내장*'이 아키텍처에서 지원 되지 않습니다
C4733|인라인 asm 'fs: 0'에 할당: 처리기 안전한 처리기로 등록 되지 않았습니다
C4734|개 이상의 64k 디버그 정보 섹션; COFF에 줄 번호 모듈에 대 한 COFF 디버그 줄 번호 표시 하 고 중지 '*모듈*'
C4738|32비트 float 결과를 메모리에 저장하면 성능이 저하될 수 있습니다.
C4739|변수에 대 한 참조가 '*변수*' 저장소 공간을 초과 합니다
C4740|내부 / 외부로 인라인 asm 코드 흐름을 선택 하면 전역 최적화
C4742|'*변수*'다른 맞춤의 '*위치*'및'*위치*': *번호* 및 *번호*
C4743|'*이름*'다른 크기의 '*위치*'및'*위치*': *번호* 및 *번호* 바이트
C4744|'*이름*'다른 종류의 '*위치*'및'*위치*': '*형식*'및'*형식*'
C4747|관리 되는 호출 '*형식*': DLL 진입점 및 DLL 진입점에서 접근 하는 호출을 포함 하 여 로더 잠금 상태에서 관리 되는 코드는 실행 되지 않을 수 있습니다
C4761|인수;의 정수 크기가 일치 하지 않습니다. 변환 됩니다.
C4764|16바이트를 초과하도록 catch 개체를 맞출 수 없습니다.
C4788|'*식별자*': 식별자로 잘렸습니다. '*번호*' 문자
C4789|버퍼 '*이름*' 크기의 *번호* 바이트 오버런 됩니다. *번호* 오프셋에서 시작 바이트가 작성 됩니다 *번호*
C4801|참조로 반환은 확인할 수 없습니다: *설명*
C4819|현재 코드 페이지에서 표현할 수 없는 문자가 파일 (*번호*). 데이터 손실을 방지 하려면 유니코드 형식으로 파일을 저장 합니다.
C4826|변환에서 '*형식*'to'*형식*' 부호가 확장 됩니다. 이렇게 하면 예기치 않은 런타임 동작이 발생할 수 있습니다.
C4829|main 함수에 대한 매개 변수가 잘못된 것 같습니다. 고려 ' int main (platform:: array\<platform:: string ^ > ^ argv)'
C4835|'*형식*': 내보낸된 데이터에 대 한 이니셜라이저는 관리 되는 코드가 호스트 어셈블리에서 먼저 실행 될 때까지 실행 되지 것입니다
C4867|'*형식*': 비표준 구문 사용. '&' 멤버에 대 한 포인터를 만들려면
C4936|/clr 또는 /clr:pure를 지정하여 컴파일한 경우에만 이 __declspec를 사용할 수 있습니다.
C4937|'*이름*'및'*이름*'의 인수로 서 서로 구분 되지 않으므로'*옵션*'
C4938|'*형식*': 부동 소수점 감소 변수로 /fp 구분 하면: strict 또는 #pragma fenv_access
C4939|#pragma vtordisp는 사용되지 않으므로 이후 Visual C++ 릴리스에서 제거될 예정입니다.
C4947|'*형식*': 사용 되지 않는 것으로 표시
C4949|pragma 'managed' 및 'u'로 컴파일하는 경우에 의미 있는 ' / clr [: 옵션]'
C4950|'*형식*': 사용 되지 않는 것으로 표시
C4955|'*설명*': 가져오기가 무시 되었습니다; 이미에서 가져온 '*소스*'
C4956|'*형식*':이 형식은 확인할 수입니다.
C4957|'*식*': 명시적 캐스트에서 '*형식*'to'*형식*'를 확인할 수 없습니다
C4958|'*식*': 포인터 산술 연산은 확인할 수 없습니다
C4959|관리 되지 않는 정의할 수 없습니다. *클래스* '*형식*' /clr: safe에서 해당 멤버에 액세스 하면 비안정형 코드가 생성 되므로
C4960|'*설명*' 너무 커서 프로 파일링
C4961|프로필 데이터가 병합 '*위치*'를 사용 하지 않도록 설정 하는 프로필 기반 최적화
C4962|'*설명*': 프로필 데이터가 일관성이 이므로 사용 하지 않도록 설정 하는 프로필 기반 최적화
C4963|'*설명*': 프로필 데이터가 없습니다; 계측 된 빌드에서 다른 컴파일러 옵션을 사용 했습니다
C4964|최적화 옵션을 지정 합니다. 프로필 정보가 수집 되지 않습니다.
C4965|암시적 상자 정수 0; nullptr 또는 명시적 캐스트를 사용 하 여
C4970|대리 생성자: 이후 대상 개체가 무시 '*선언*'는 정적
C4971|인수 순서: \<대상 개체 >를 \<함수 대상 > 대리자 생성자는 사용 되지 않습니다를 사용 하 여 \<함수 대상 >, \<대상 개체 >
C4972|왼쪽 항의 값(l-value)을 확인할 수 없어 unboxing 작업의 결과를 직접 수정하거나 처리하고 있습니다.

## <a name="warnings-introduced-in-visual-c-2003-compiler-version-13103077"></a>Visual c + + 2003 (컴파일러 버전 13.10.3077)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:13.00.9466__합니다.

|||
|-|-|
C4343|#pragma 최적화 (*설명*, 해제) /Og 옵션을 재정의
C4344|동작 변경: 명시적 템플릿 인수 결과 호출에서 사용 하 여 '*선언*'
C4346|'*형식*': 종속 이름이 형식이 아닙니다
C4348|'*선언*': 기본 매개 변수 재정의: 매개 변수 *번호*
C4356|'*형식*': 파생된 클래스를 통해 정적 데이터 멤버를 초기화할 수 없습니다
C4408|익명 *구조체* 모든 데이터 멤버를 선언 하지 않았습니다.
C4544|'*선언*': 기본 템플릿 인수가이 템플릿 선언에서 무시 됩니다.
C4545|쉼표 앞의 식이 인수 목록이 없는 함수로 계산됩니다.
C4546|쉼표 앞의 함수에 인수 목록이 없습니다.
C4547|'*식*': 쉼표 효과가 없습니다; 앞의 연산자 파생 작업이 있는 연산자 여야 합니다.
C4548|쉼표 앞의 식은 의미 없는 식입니다. 파생 작업이 있는 식이어야 합니다.
C4549|'*식*': 쉼표 앞의 연산자에 영향을 주지 않습니다; 시겠습니까 '*식*'?
C4628|-Ze에는 digraph가 지원되지 않습니다. 문자 시퀀스 '*시퀀스*'에 대 한 대체 토큰으로 해석 되지'*토큰*'
C4629|digraph가 사용 문자 시퀀스 '*시퀀스*'토큰으로 해석'*토큰*' (이 원하지 경우 두 문자 사이 공백을 삽입)
C4671|'*설명*': 복사 생성자가 액세스할 수 없습니다
C4676|'*설명*': 소멸자에 액세스할 수 없으면
C4677|'*이름*': 전용이 아닌 멤버의 시그니처에 어셈블리 전용 형식 '*선언*'
C4686|'*형식*': 동작 변경 되었을 수, udt 반환 호출 규칙이
C4812|사용 되지 않는 선언 스타일:를 사용 하십시오 '*형식*::*이름*' 대신
C4813|'*형식*': 지역 클래스의 friend 함수가 이전에 선언 해야
C4821|시그니처 (BOM)으로 파일을 저장 하십시오를 유니코드 인코딩 형식을 확인할 수 없습니다.
C4822|'*형식*': 지역 클래스 멤버 함수 본문에는
C4823|'*형식*': 사용 고정 포인터 하지만 해제 의미 체계를 사용할 수 없습니다. /EHa를 사용 하는 것이 좋습니다.
C4913|사용자 정의 이항 연산자 ','가 존재하지만 오버로드가 모든 피연산자를 변환하지 못했습니다. 기본 내장 이항 연산자 ','를 사용합니다.
C4948|반환 형식 '*선언*' 해당 setter의 마지막 매개 변수 형식과 일치 하지 않습니다
C4951|'*설명*' 프로필 데이터가 수집 된 함수 프로필 데이터가 사용 되지 않습니다 이후 편집 되었습니다.
C4952|'*설명*': 프로그램 데이터베이스에 프로필 데이터가 없습니다 '*설명*'
C4953|인라인 '*설명*' 프로필 데이터가 수집 된 이후 편집 되었습니다.
C4954|'*설명*': 프로 파일링 되지 않았습니다 (__int64 switch 식 포함)

## <a name="warnings-introduced-in-visual-c-2002-compiler-version-13009466"></a>Visual c + + 2002 (컴파일러 버전 13.00.9466)에 도입 된 경고

이러한 경고 및 이후 버전에서 모든 경고는 컴파일러 옵션을 사용 하 여 억제 __/Wv:12__합니다.

|||
|-|-|
C4096|'*형식*': 인터페이스는 COM 인터페이스가 아니므로 IDL로 내보내지 것입니다
C4097|pragma 매개 변수는 'restore' 또는 'off'이어야 합니다.
C4165|'Bool'; 'HRESULT'는 변환 되 고 원하는 작업 인지 입니까?
C4183|'*이름*': 'int'를 반환 하는 멤버 함수를 것으로 간주 반환 유형이; 없습니다.
C4199|*description*
C4255|'*이름*': 함수 프로토타입을 입력 하지 않았습니다: '()'에서 '(void)'로 변환
C4256|'*선언*': 가상 기본 클래스에 대 한 생성자에는 '...'; 호출이 Visual c + +의 이전 버전과 호환 되지 않을 수 있습니다
C4258|'*이름*': 정의에서 바깥쪽 범위의 정의가 사용 루프 무시 됩니다.
C4263|'*선언*': 멤버 함수가 기본 클래스 가상 멤버 함수를 재정의 하지 않습니다
C4264|'*선언*': 재정의 자료에서 가상 멤버 함수에 대해 사용할 수 없습니다 '*클래스*'; 함수가 숨겨집니다.
C4265|'*형식*': 클래스에 가상 함수가 있지만 소멸자는 가상이이 클래스의 인스턴스를 제대로 소멸 되지 않을 수 있습니다
C4266|'*선언*': 재정의 자료에서 가상 멤버 함수에 대해 사용할 수 없습니다 '*클래스*'; 함수가 숨겨집니다.
C4267|'*식*': 변환에 사용 되는 'size_t'에서 '*형식*', 데이터가 손실 될 수
C4274|#ident 무시 됩니다. #pragma 주석 (exestr, 'string')에 대 한 설명서를 참조 하십시오.
C4277|가져온된 항목 '*형식*::*이름*' 데이터 멤버와 함수 멤버;로 존재 하므로 데이터 멤버가 무시 됩니다.
C4278|'*이름*': 형식 라이브러리의 식별자 '*설명*'가 이미 매크로 'rename' 한정자를 사용 하십시오.
C4279|'*이름*': 형식 라이브러리의 식별자 '*설명*'는 키워드 'rename' 한정자를 사용 하십시오.
C4287|'*식*': 서명 되지 않은 또는 음의 상수 일치 하지 않습니다.
C4288|비표준 확장이 사용 됨: '*이름*': for 루프에서 선언 된 루프 제어 변수가 for 루프 범위 외부에서 사용 되었습니다; 외부 범위에 있는 선언과 충돌
C4289|비표준 확장이 사용 됨: '*이름*': for 루프에서 선언 된 루프 제어 변수가 for 루프 범위 외부에서 사용 됩니다
C4293|'*식*': 시프트 횟수가 음수 이거나 너무 큽니다., 정의 되지 않은 동작
C4295|'*형식*': 배열이 너무 작아서 null 종결 문자를 포함 하려면
C4296|'*식*': 식이 항상 *값*
C4297|'*형식*': 함수가 간주 하지 않도록 지정 되었으나 예외를 throw 하려면
C4298|'*이름*': 형식 라이브러리의 식별자 '*설명*'가 이미 매크로; 이름을 ' __*이름*'
C4299|'*이름*': 형식 라이브러리의 식별자 '*설명*'가 키워드입니다; 이름을 ' __*이름*'
C4302|'*식*':에서 잘림 '*형식*'to'*형식*'
C4303|*변환* 에서 '*형식*'to'*형식*'은 static_cast, __try_cast 또는 dynamic_cast를 사용, 사용 되지 않음
C4314|pragma 매개 변수는 '32' 또는 '64' 이어야 합니다
C4315|'*형식*': 멤버에 대 한 'this'이 포인터 '*형식*' 정렬 되지 *번호* 생성자가 예상 대로
C4318|memset에 길이로 상수 0을 전달합니다.
C4319|'*식*': 0 확장 '*형식*'to'*형식*' 더 큰
C4321|자동으로 생성 되는 인터페이스에 대 한 IID '*형식*'
C4322|자동으로 생성 되는 클래스에 대 한 CLSID*형식*'
C4323|다시 사용 하 여 등록 된 CLSID를 클래스의*형식*'
C4324|'*형식*': 맞춤 지정자 때문에 구조체가 채워졌습니다
C4325|표준 섹션에 대 한 특성 '*설명*' 무시
C4326|반환 형식 '*이름*'이어야 합니다.'*형식*' 대신의 '*형식*'
C4327|'*식*': LHS의 간접 참조 맞춤이 (*번호*) RHS 보다 큰 (*번호*)
C4328|'*설명*': 정식 매개 변수의 간접 참조 맞춤이 *번호* (*번호*) 실제 인수 맞춤 보다 큰 (*번호*)
C4329|맞춤 지정 자가 enum에서 무시 됩니다.
C4336|상호 참조 형식 라이브러리 가져오기 '*라이브러리*'가져오기' before*설명*'
C4337|상호 참조 형식 라이브러리 '*라이브러리*'에서'*설명*'가 자동으로 가져옵니다.
C4338|#pragma *설명*: 표준 섹션 '*섹션*' 사용
C4339|'*형식*':이 형식 사용 하면 런타임 예외가 발생할 수 있습니다 CLR/WinRT 메타 데이터에 정의 되지 않은 형식이 사용 되었습니다
C4353|비표준 확장이 사용 됨: 함수 식으로 상수 0입니다.  내장 '__noop' 함수를 사용
C4370|'*선언*': 압축 기능이 향상 되어 컴파일러의 이전 버전에서 클래스 레이아웃이 변경 되었습니다
C4371|'*선언*': 멤버의 압축 기능이 향상 되어 컴파일러의 이전 버전에서 클래스 레이아웃이 변경 될 수 있습니다 '*멤버*'
C4373|'*형식*': 가상 함수 재정의*선언*', 매개 변수의 const/volatile 한정자만 다른 경우 이전 버전의 컴파일러를 재정의 하지 않았습니다
C4387|'*설명*': 고려 되었지만
C4389|'*식*': signed 또는 unsigned 일치 하지 않습니다.
C4391|'*선언*': 내장 함수가 필요 합니다. 반환 형식이 잘못 되었습니다 '*형식*'
C4392|'*선언*': 내장 함수, 예상에 대 한 인수 개수가 잘못 되었습니다 '*번호*' 인수
C4407|멤버 표현에 다른 포인터 캐스팅, 컴파일러 코드를 생성할 수 잘못 된
C4420|'*이름*': 사용 하 여 연산자를 사용할 수 없는 '*이름*' 대신 런타임 검사가 손상 될 수 있습니다
C4440|재정의 된 호출 규칙이에서 '*설명*'to'*설명*' 무시
C4442|__annotation 인수에 null 종결자를 포함 합니다.  값은 잘립니다.
C4444|'*이름*':이 컨텍스트에서 최상위 '__unaligned' 구현 되지 않음
C4526|'*형식*': 정적 멤버 함수는 가상 함수를 재정의할 수 없습니다 '*선언*' 무시 재정의 가상 함수는 숨겨집니다.
C4531|C + + 예외 처리를 Windows CE에서 사용할 수 없습니다. 구조적된 예외 처리 사용
C4532|'*설명*': 점프 *마지막* 블록의 동작을 정의 되지 않은 종료 처리 중
C4533|초기화 '*선언*' 의해 생략 되었습니다. ' goto *선언*'
C4534|'*선언*'에 대 한 기본 생성자 됩니다 *클래스* '*형식*' 기본 인수 때문에
C4535|호출 _set_se_translator() /EHa 필요
C4536|'*설명*': 형식-이름이 메타 데이터 한계인 초과 '*번호*' 문자
C4537|'*선언*': '.' 비 UDT 형식에 적용
C4542|쓸 수 없습니다 병합된 삽입 된 텍스트 파일 생성을 건너뛰므로 *형식* 파일: '*filename*': *오류*
C4543|특성으로 표시 되지 않도록 텍스트 삽입 ' 없음\_injected_text'
C4555|식이 효과가 없습니다. 파생 작업이 있는 식이어야 합니다.
C4557|효과 포함 '__assume' '*효과*'
C4558|피연산자의 값 '*번호*'범위를 벗어났습니다'*번호* - *번호*'
C4561|'와 호환 되지 않는 ' __fastcall는 ' / clr' 옵션: '__stdcall'으로 변환
C4562|완전히 프로토타입화 된 함수가 필요는 ' / clr' 옵션: '()'에서 '(void)'로 변환
C4564|메서드 '*이름*'의 *클래스* '*형식*'지원 되지 않는 기본 매개 변수 정의'*매개 변수*'
C4584|'*형식*': 기본 클래스 '*선언*'은 이미의 기본 클래스'*선언*'
C4608|공용 구조체의 여러 멤버를 초기화 하는 중: '*형식*'및'*형식*'
C4619|#pragma 경고: 수는 없습니다 경고 '*번호*'
C4623|'*형식*': 기본 생성자가 암시적으로 삭제 된 것으로 정의 됩니다
C4624|'*형식*': 소멸자가 암시적으로 삭제 된 것으로 정의 됩니다
C4625|'*형식*': 복사 생성자가 암시적으로 삭제 된 것으로 정의 됩니다
C4626|'*형식*': 할당 연산자가 암시적으로 삭제 된 것으로 정의 됩니다
C4645|'noreturn'으로 선언 된 함수에 return 문이 있을
C4646|'noreturn'으로 선언 된 함수에 void가 아닌 반환 형식이
C4659|#pragma '*설명*': 예약 된 세그먼트에 사용 하 여 '*이름*' 않은 동작을 사용 하 여 #pragma 주석 (linker,...)
C4667|'*선언*': 강제 인스턴스화와 일치 하는 정의 된 함수 템플릿이 없습니다
C4668|'*이름*'에 '0'으로 바뀝니다. 전처리기 매크로로 정의 되지 않은'*값*'
C4669|'*식*': 안전 하지 않은 변환: '*형식*' 관리 되 는/WinRT 형식의 개체인 경우
C4674|'*이름*' 'static' 선언 해야 하며 매개 변수를 하나만 있어야 합니다.
C4680|'*형식*': coclass는 기본 인터페이스를 지정 하지 않습니다
C4681|'*형식*': coclass가 이벤트 소스인 기본 인터페이스를 지정 하지 않습니다
C4682|'*형식*': 방향 매개 변수 특성을 지정 하지 [in]를 기본값으로 설정
C4683|'*선언*': 이벤트 소스에 'out'-여러 이벤트 처리기를 후크 하는 경우 주의 해야 합니다; 매개 변수
C4684|'*설명*': 경고!! 특성에 잘못 된 코드가 생성 발생할 수 있습니다: 주의 하 여 사용
C4685|템플릿 매개 변수를 분석하는 경우 '> >'가 있어야 하는데 '>>'가 왔습니다.
C4700|초기화 되지 않은 지역 변수 '*이름*' 사용
C4701|잠재적으로 초기화 되지 않은 지역 변수 '*이름*' 사용
C4702|코드에 접근할 수
C4711|함수 '*이름*' 자동 인라인 확장을 위해 선택
C4714|함수 '*선언*' 인라인이 아니라 __forceinline로 표시
C4715|'*함수*': 모든 제어 경로 값을 반환
C4716|'*함수*': 값을 반환 해야
C4717|'*함수*': 모든 제어 경로에서 재귀적으로 함수 런타임 스택 오버플로가 발생 하면
C4718|'*함수*': 재귀 호출에 파생 작업이 없습니다. 삭제
C4719|이중 상수를 Qfast로 지정 된 경우-사용 하 여 'f'를 단 정밀도 찾았습니다.
C4723|0 나누기 연산이 발생할 수
C4724|0의 나머지 연산이 발생할 수 있습니다.
C4725|명령이 일부 Pentium에서 정확하지 않을 수 있습니다.
C4757|첨자는 부호 없는 큰 값, 음의 상수가 사용 하려고 했습니까?
C4772|#import; 누락 된 형식 라이브러리에서 형식을 참조 했습니다. '*설명*' 자리 표시자로 사용
C4792|함수 '*함수*' 링크에 필요한 가져오기 라이브러리; 네이티브 코드에서 sysimport를 사용 하 여 선언 및 참조
C4794|스레드 로컬 저장소 변수의 세그먼트 '*이름*'에서 변경'*세그먼트*'to'*세그먼트*'
C4798|p 코드 함수에 대해 생성 된 네이티브 코드 '*이름*' 예외 처리기 또는 해제 의미 체계
C4799|함수 '*이름*'에 EMMS 명령이 없습니다
C4803|'*선언*': raise 메서드에 이벤트의 다른 저장소 클래스 '*선언*'
C4810|value of pragma pack(show) == *number*
C4811|pragma conform 값 (forScope, show) = = *값*
C4820|'*형식*': '*번호*' 바이트 채움 문자가 뒤에 추가 *형식* '*형식*'
C4905|와이드 문자열 리터럴 캐스팅 '*형식*'
C4906|문자열 리터럴을로 캐스팅 '*형식*'
C4912|'*특성*': 특성에는 중첩된 UDT에 동작이 정의 되지 않았습니다
C4916|dispid를 하기 위해 '*형식*': 인터페이스에 의해 정의 되어야 합니다
C4917|'*형식*': GUID만 클래스, 인터페이스 또는 네임 스페이스와 연결할 수
C4918|'*문자*': pragma 최적화 목록에 잘못 된 문자
C4920|enum *이름* 멤버 *이름*=*번호* 열거형에서 이미 확인 *이름* 으로 *이름* = *번호*
C4921|'*이름*': 특성 값 '*값*' 기호는 여러 번 지정 하지 마십시오.
C4925|'*선언*': 스크립트에서 dispinterface 메서드를 호출할 수 없습니다
C4926|'*선언*': 기호를 이미 정의: 무시 된 특성
C4927|변환이 잘못 되었습니다. 둘 이상의 사용자 정의 변환이 암시적으로 적용 된
C4928|복사 초기화가 잘못되었습니다. 사용자 정의 변환이 암시적으로 두 번 이상 적용되었습니다.
C4929|'*설명*': 형식 라이브러리로 있습니다. 'embedded_idl' 한정자를 무시 합니다.
C4930|'*선언*': 프로토타입 함수가 호출 되지 (의도 되는 변수 정의 ि ल ्?)
C4931|에 대 한 형식 라이브러리를 빌드 했다고 간주 합니다. *번호*-비트 포인터
C4932|__identifier (*설명*)와 __identifier (*설명*)를 구분할 수 없습니다
C4934|'__delegate(multicast)'는 사용 되지 않습니다., '__delegate' 대신 사용 합니다.
C4935|수정 됨 어셈블리 액세스 지정자 '*설명*'
C4944|'*이름*': 기호를 가져올 수 없습니다 '*소스*': '*선언*' 현재 범위에 이미 있습니다
C4945|'*이름*': 기호를 가져올 수 없습니다 '*소스*': '*선언*'이미 가져온 다른 어셈블리에서 '*소스*'
C4946|관련된 클래스 간에 사용 되는 reinterpret_cast: '*선언*'및'*선언*'
C4995|'*이름*': 이름 #pragma 사용 되지 않는 것으로 표시 되었습니다
C4996|'*issue*': *description*
C4997|'*형식*': coclass가 COM 인터페이스 또는 의사 (pseudo) 인터페이스를 구현 하지 않습니다
C4998|예상 실패: *설명*(*번호*)

## <a name="see-also"></a>참고 항목
[/Wv 컴파일러 옵션](../../build/reference/compiler-option-warning-level.md)
[기본적으로 해제 되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)
[경고](../../preprocessor/warning.md)
