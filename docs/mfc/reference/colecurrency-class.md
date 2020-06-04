---
title: 코레커런시 클래스
ms.date: 08/29/2019
f1_keywords:
- COleCurrency
- AFXDISP/COleCurrency
- AFXDISP/COleCurrency::COleCurrency
- AFXDISP/COleCurrency::Format
- AFXDISP/COleCurrency::GetStatus
- AFXDISP/COleCurrency::ParseCurrency
- AFXDISP/COleCurrency::SetCurrency
- AFXDISP/COleCurrency::SetStatus
- AFXDISP/COleCurrency::m_cur
- AFXDISP/COleCurrency::m_status
helpviewer_keywords:
- COleCurrency [MFC], COleCurrency
- COleCurrency [MFC], Format
- COleCurrency [MFC], GetStatus
- COleCurrency [MFC], ParseCurrency
- COleCurrency [MFC], SetCurrency
- COleCurrency [MFC], SetStatus
- COleCurrency [MFC], m_cur
- COleCurrency [MFC], m_status
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
ms.openlocfilehash: cc69143101c5d00d4f9a689bd02abdd9596e5b53
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753930"
---
# <a name="colecurrency-class"></a>코레커런시 클래스

OLE 자동화의 `CURRENCY` 데이터 형식을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class COleCurrency
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레 화폐 ::콜레 화폐](#colecurrency)|`COleCurrency` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleCurrency::형식](#format)|개체의 서식이 지정된 문자열 `COleCurrency` 표현을 생성합니다.|
|[COle 통화::GetStatus](#getstatus)|이 `COleCurrency` 개체의 상태(유효성)를 가져옵니다.|
|[COleCurrency::P어스커런시](#parsecurrency)|문자열에서 CURRENCY 값을 읽고 `COleCurrency`의 값을 설정합니다.|
|[COle 통화 ::설정 통화](#setcurrency)|이 `COleCurrency` 개체의 값을 설정합니다.|
|[COle 통화::설정 상태](#setstatus)|이 `COleCurrency` 개체의 상태(유효성)를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[연산자 =](#operator_eq)|값을 복사합니다. `COleCurrency`|
|[연산자 +, -](#operator_plus_minus)|값의 부호를 추가, `COleCurrency` 빼고 변경합니다.|
|[연산자 +=, -=](#operator_plus_minus_eq)|이 `COleCurrency` `COleCurrency` 개체에서 값을 추가하고 뺍니다.|
|[연산자 */](#operator_star)|`COleCurrency` 정수 값으로 값을 배율 조정합니다.|
|[연산자 *=, /=](#operator_star_div_eq)|이 `COleCurrency` 값을 정수 값으로 배율 조정합니다.|
|[연산자 <<](#operator_stream)|`COleCurrency` 값을 또는 `CDumpContext`에 `CArchive` 출력합니다.|
|[연산자 >>](#operator_stream)|에서 개체를 `COleCurrency` `CArchive`입력합니다.|
|[연산자 통화](#operator_currency)|`COleCurrency` 값을 통화로 변환합니다.|
|[연산자 ==, <, <=등](#colecurrency_relational_operators)|두 `COleCurrency` 값을 비교합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[코레화폐::m_cur](#m_cur)|이 `COleCurrency` 개체의 기본 통화를 포함합니다.|
|[코레 화폐::m_status](#m_status)|이 `COleCurrency` 개체의 상태를 포함합니다.|

## <a name="remarks"></a>설명

`COleCurrency`기본 클래스가 없습니다.

통화는 8바이트, 2의 보완 정수 값으로 10,000으로 확장됩니다. 소수점 기호 왼쪽에는 15자리 고정 소수점 번호가 있고 오른쪽에는 4자리 고정 소수점 번호가 있습니다. CURRENCY 데이터 유형은 돈과 관련된 계산이나 정확도가 중요한 고정 점 계산에 매우 유용합니다. OLE 자동화의 데이터 형식에 `VARIANT` 대 한 가능한 형식 중 하나입니다.

`COleCurrency`또한 이 고정점 형식에 대한 몇 가지 기본 산술 연산을 구현합니다. 고정점 계산 중에 발생하는 반올림 오류를 제어하기 위해 지원되는 작업이 선택되었습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`COleCurrency`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="colecurrencycolecurrency"></a><a name="colecurrency"></a>콜레 화폐 ::콜레 화폐

`COleCurrency` 개체를 생성합니다.

```
COleCurrency();
COleCurrency(CURRENCY cySrc);
COleCurrency(const COleCurrency& curSrc);
COleCurrency(const VARIANT& varSrc);

COleCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>매개 변수

*시스터드 (동음이의)*<br/>
새 `COleCurrency` 개체에 복사할 통화 값입니다.

*커서스 (동음이의)*<br/>
새 `COleCurrency` `COleCurrency` 개체에 복사할 기존 개체입니다.

*varSrc*<br/>
통화 `VARIANT` 값(VT_CY)으로 `COleVariant` 변환하여 새 `COleCurrency` 개체로 복사할 기존 데이터 구조(개체일 수 있음)입니다.

*nUnits,* *nFractionalUnits* 새 `COleCurrency` 개체에 복사할 값의 단위 및 소수 부분(1/10,000의 단위)을 나타냅니다.

### <a name="remarks"></a>설명

이러한 모든 생성자는 지정된 `COleCurrency` 값으로 초기화된 새 개체를 만듭니다. 이러한 각 생성자에 대한 간략한 설명은 다음과 같습니다. 달리 명시되지 않는 한 `COleCurrency` 새 항목의 상태가 유효한 것으로 설정됩니다.

- COleCurrency() 초기화된 개체를 `COleCurrency` 0(0)으로 생성합니다.

- COleCurrency`cySrc`() `COleCurrency` [통화](/windows/win32/api/wtypes/ns-wtypes-cy~r1) 값에서 개체를 생성합니다.

- COleCurrency`curSrc`() 기존 `COleCurrency` `COleCurrency` 개체에서 개체를 생성합니다. 새 개체의 상태는 소스 개체와 동일합니다.

- COleCurrency`varSrc`() 개체를 생성합니다. `COleCurrency` [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 구조 또는 `COleVariant` 개체를 통화(VT_CY) 값으로 변환하려고 시도합니다. 이 변환에 성공하면 변환된 값이 새 `COleCurrency` 개체에 복사됩니다. 그렇지 않으면 `COleCurrency` 개체 값이 0(0)으로 설정되고 상태가 유효하지 않습니다.

- COleCurrency`nUnits`() `nFractionalUnits`) `COleCurrency` 는 지정된 숫자 구성 요소에서 개체를 생성합니다. 소수 부분의 절대 값이 10,000보다 크면 단위에 대한 적절한 조정이 이루어집니다. 단위 및 소수 부분은 서명된 긴 값으로 지정됩니다.

자세한 내용은 Windows SDK의 [통화](/windows/win32/api/wtypes/ns-wtypes-cy~r1) 및 [변형](/windows/win32/api/oaidl/ns-oaidl-variant) 항목을 참조하십시오.

### <a name="example"></a>예제

다음 예제는 0 매개 변수 및 두 매개 변수 생성자의 효과를 보여 준다.

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

## <a name="colecurrencyformat"></a><a name="format"></a>COleCurrency::형식

이 멤버 함수를 호출하여 통화 값의 형식이 지정된 표현을 만듭니다.

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
로캘 설정에 대한 플래그를 나타냅니다. 다음 플래그만 통화와 관련이 있습니다.

- LOCALE_NOUSEROVERRIDE 사용자 지정 사용자 설정이 아닌 시스템 기본 로캘 설정을 사용합니다.

*Lcid*<br/>
변환에 사용할 로캘 ID를 나타냅니다.

### <a name="return-value"></a>Return Value

형식이 지정된 통화 값을 포함하는 A입니다. `CString`

### <a name="remarks"></a>설명

로컬 언어 사양(로캘 아이디)을 사용하여 값을 서식을 지정합니다. 통화 기호는 반환된 값에 포함되지 않습니다. 이 `COleCurrency` 개체의 상태가 null이면 반환 값은 빈 문자열입니다. 상태가 잘못되면 반환 문자열은 문자열 리소스 IDS_INVALID_CURRENCY 지정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

## <a name="colecurrencygetstatus"></a><a name="getstatus"></a>COle 통화::GetStatus

지정된 `COleCurrency` 개체의 상태(유효성)를 가져오려면 이 멤버 함수를 호출합니다.

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>Return Value

이 `COleCurrency` 값의 상태를 반환합니다.

### <a name="remarks"></a>설명

반환 값은 클래스 `CurrencyStatus` 내에서 정의된 수련된 형식에 `COleCurrency` 의해 정의됩니다.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

이러한 상태 값에 대한 간략한 설명은 다음 목록을 참조하십시오.

- `COleCurrency::valid`이 `COleCurrency` 개체가 유효하다는 것을 나타냅니다.

- `COleCurrency::invalid`이 `COleCurrency` 개체가 잘못되었음을 나타냅니다. 즉, 해당 값이 올바르지 않을 수 있습니다.

- `COleCurrency::null`이 `COleCurrency` 개체가 null, 즉 이 개체에 대해 제공된 값이 없음을 나타냅니다. (C++ NULL과 반대로 "값이 없음"의 데이터베이스 의미에서 "null"입니다.)

다음과 같은 `COleCurrency` 경우 개체의 상태가 잘못되었습니다.

- 해당 값이 VARIANT 또는 `COleVariant` 통화 값으로 변환할 수 없는 값에서 설정된 경우

- 이 개체가 산술 할당 작업 중에 오버플로 또는 언더플로우를 ** \* **경험한 경우(예: `+=` 또는 .

- 이 개체에 잘못된 값이 할당된 경우

- 이 개체의 상태가 [SetStatus](#setstatus)를 사용하여 유효하지 않게 명시적으로 설정된 경우 .

상태를 유효하지 않게 설정할 수 있는 작업에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [COleCurrency](#colecurrency)

- [연산자 =](#operator_eq)

- [연산자 + -](#operator_plus_minus)

- [연산자 += 및 -=](#operator_plus_minus_eq)

- [연산자 * /](#operator_star)

- [연산자 *= 및 /=](#operator_star_div_eq)

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

## <a name="colecurrencym_cur"></a><a name="m_cur"></a>코레화폐::m_cur

이 `COleCurrency` 개체의 기본 [통화](/windows/win32/api/wtypes/ns-wtypes-cy~r1) 구조입니다.

### <a name="remarks"></a>설명

> [!CAUTION]
> 이 함수에서 `CURRENCY` 반환되는 포인터에 의해 액세스되는 구조의 값을 `COleCurrency` 변경하면 이 개체의 값이 변경됩니다. 이 `COleCurrency` 개체의 상태는 변경되지 않습니다.

자세한 내용은 Windows SDK의 [통화](/windows/win32/api/wtypes/ns-wtypes-cy~r1) 항목을 참조하십시오.

## <a name="colecurrencym_status"></a><a name="m_status"></a>코레 화폐::m_status

이 데이터 멤버의 형식은 `CurrencyStatus` `COleCurrency` 클래스 내에서 정의된 수련 된 형식입니다.

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>설명

이러한 상태 값에 대한 간략한 설명은 다음 목록을 참조하십시오.

- `COleCurrency::valid`이 `COleCurrency` 개체가 유효하다는 것을 나타냅니다.

- `COleCurrency::invalid`이 `COleCurrency` 개체가 잘못되었음을 나타냅니다. 즉, 해당 값이 올바르지 않을 수 있습니다.

- `COleCurrency::null`이 `COleCurrency` 개체가 null, 즉 이 개체에 대해 제공된 값이 없음을 나타냅니다. (C++ NULL과 반대로 "값이 없음"의 데이터베이스 의미에서 "null"입니다.)

다음과 같은 `COleCurrency` 경우 개체의 상태가 잘못되었습니다.

- 해당 값이 VARIANT 또는 `COleVariant` 통화 값으로 변환할 수 없는 값에서 설정된 경우

- 이 개체가 산술 할당 작업 중에 오버플로 또는 언더플로우를 ** \* **경험한 경우(예: `+=` 또는 .

- 이 개체에 잘못된 값이 할당된 경우

- 이 개체의 상태가 [SetStatus](#setstatus)를 사용하여 유효하지 않게 명시적으로 설정된 경우 .

상태를 유효하지 않게 설정할 수 있는 작업에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [COleCurrency](#colecurrency)

- [연산자 =](#operator_eq)

- [연산자 +, -](#operator_plus_minus)

- [연산자 +=, -=](#operator_plus_minus_eq)

- [연산자 */](#operator_star)

- [연산자 *=, /=](#operator_star_div_eq)

> [!CAUTION]
> 이 데이터 멤버는 고급 프로그래밍 상황에 적합합니다. 인라인 멤버 함수 [GetStatus](#getstatus) 및 [SetStatus를](#setstatus)사용 해야 합니다. 이 `SetStatus` 데이터 멤버를 명시적으로 설정하는 것에 대한 자세한 내용은 참조하세요.

## <a name="colecurrencyoperator-"></a><a name="operator_eq"></a>COleCurrency::연산자 =

이러한 오버로드된 할당 연산자는 원본 `COleCurrency` 통화 값을 이 개체에 복사합니다.

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>설명

각 연산자에 대한 간략한 설명은 다음과 같습니다.

- **연산자 =()** `cySrc` **)** `CURRENCY` 값이 `COleCurrency` 개체에 복사되고 해당 상태가 유효한 것으로 설정됩니다.

- **연산자 =()** `curSrc` **)** 피연산자의 값과 상태는 기존 `COleCurrency` 개체가 이 `COleCurrency` 개체에 복사됩니다.

- **연산자** *=(varSrc)* **)** 값(또는 [COleVariant](../../mfc/reference/colevariant-class.md) 개체)을 통화()로 `VT_CY`변환하는 데 성공하면 변환된 값이 `COleCurrency` 이 개체에 복사되고 해당 상태가 유효한 것으로 설정됩니다. `VARIANT` 변환에 성공하지 못하면 `COleCurrency` 개체 값이 0으로 설정되고 상태가 유효하지 않습니다.

자세한 내용은 Windows SDK의 [통화](/windows/win32/api/wtypes/ns-wtypes-cy~r1) 및 [변형](/windows/win32/api/oaidl/ns-oaidl-variant) 항목을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus"></a>COleCurrency::연산자 +, -

이러한 연산자는 두 `COleCurrency` 값을 서로 추가하고 빼고 `COleCurrency` 값의 부호를 변경할 수 있도록 합니다.

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>설명

피연산자 중 하나가 null이면 결과 `COleCurrency` 값의 상태는 null입니다.

산술 연산이 오버플로되면 결과 `COleCurrency` 값이 유효하지 않습니다.

피연산자유효하지 않고 다른 피연산이 null이 아닌 `COleCurrency` 경우 결과 값의 상태가 유효하지 않습니다.

유효, 유효하지 않은 및 null 상태 값에 대한 자세한 내용은 [m_status](#m_status) 멤버 변수를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus_eq"></a>COleCurrency:::연산자 +=, -=

이 개체에 `COleCurrency` 대한 값을 추가하고 뺄 `COleCurrency` 수 있습니다.

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>설명

피연산자 중 하나가 null이면 이 `COleCurrency` 개체의 상태가 null로 설정됩니다.

산술 연산이 오버플로되면 이 `COleCurrency` 개체의 상태가 유효하지 않은 상태로 설정됩니다.

피연산자 중 하나가 유효하지 않고 다른 피연산자 중 `COleCurrency` 하나가 null이 아닌 경우 이 개체의 상태가 유효하지 않은 상태로 설정됩니다.

유효, 유효하지 않은 및 null 상태 값에 대한 자세한 내용은 [m_status](#m_status) 멤버 변수를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

## <a name="colecurrencyoperator--and-"></a><a name="operator_star"></a>COleCurrency ::연산자 \* 및 /

`COleCurrency` 정수 값으로 값을 확장할 수 있습니다.

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>설명

피연산자의 `COleCurrency` null이면 결과 `COleCurrency` 값의 상태는 null입니다.

산술 연산이 오버플로 또는 언더플로우인 경우 `COleCurrency` 결과 값의 상태가 유효하지 않습니다.

피연산자 유효하지 `COleCurrency` 않은 경우 결과 `COleCurrency` 값의 상태가 잘못되었습니다.

유효, 유효하지 않은 및 null 상태 값에 대한 자세한 내용은 [m_status](#m_status) 멤버 변수를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

## <a name="colecurrencyoperator--"></a><a name="operator_star_div_eq"></a>COleCurrency::연산자 \*=, /=

이 `COleCurrency` 값을 정수 값으로 배율 조정하도록 허용합니다.

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>설명

피연산자(null)가 `COleCurrency` null이면 `COleCurrency` 이 개체의 상태가 null로 설정됩니다.

산술 연산이 오버플로되면 이 `COleCurrency` 개체의 상태가 유효하지 않은 상태로 설정됩니다.

피연산자 유효하지 `COleCurrency` 않은 경우 이 `COleCurrency` 개체의 상태가 유효하지 않은 상태로 설정됩니다.

유효, 유효하지 않은 및 null 상태 값에 대한 자세한 내용은 [m_status](#m_status) 멤버 변수를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

## <a name="colecurrencyoperator-ltlt-gtgt"></a><a name="operator_stream"></a>COleCurrency::연산자 &lt; &lt;,&gt;&gt;

진단 덤프 및 아카이브에 저장을 지원합니다.

```
friend CDumpContext& operator<<(
    CDumpContext& dc,
    COleCurrency curSrc);

friend CArchive& operator<<(
    CArchive& ar,
    COleCurrency curSrc);

friend CArchive& operator>>(
    CArchive& ar,
    COleCurrency& curSrc);
```

### <a name="remarks"></a>설명

추출 () **>>** 연산자는 아카이브에서 로드를 지원합니다.

## <a name="colecurrencyoperator-currency"></a><a name="operator_currency"></a>COleCurrency::연산자 통화

이 `COleCurrency` `CURRENCY` 개체에서 값이 복사된 구조를 반환합니다.

```
operator CURRENCY() const;
```

### <a name="remarks"></a>설명

## <a name="colecurrencyparsecurrency"></a><a name="parsecurrency"></a>COleCurrency::P어스커런시

이 멤버 함수를 호출하여 문자열을 구문 분석하여 통화 값을 읽습니다.

```
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT);

throw(CMemoryException*);
throw(COleException*);
```

### <a name="parameters"></a>매개 변수

*lpsz통화*<br/>
구문 분석할 null 종료된 문자열에 대한 포인터입니다.

*dwFlags*<br/>
로캘 설정(다음 플래그)에 대한 플래그를 나타냅니다.

- LOCALE_NOUSEROVERRIDE 사용자 지정 사용자 설정이 아닌 시스템 기본 로캘 설정을 사용합니다.

*Lcid*<br/>
변환에 사용할 로캘 ID를 나타냅니다.

### <a name="return-value"></a>Return Value

문자열이 통화 값으로 성공적으로 변환된 경우 Nonzero(그렇지 않으면 0).

### <a name="remarks"></a>설명

원본 문자열에서 비숫자 문자의 의미에 대해 로컬 언어 사양(로캘 아이디)을 사용합니다.

로캘 ID 값에 대한 설명은 [다국어 지원](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages)을 참조하십시오.

문자열이 통화 값으로 성공적으로 변환된 경우 이 `COleCurrency` 개체의 값은 해당 값으로 설정되고 해당 상태는 유효한 것으로 설정됩니다.

문자열을 통화 값으로 변환할 수 없거나 숫자 오버플로가 있는 경우 이 `COleCurrency` 개체의 상태가 잘못되었습니다.

메모리 할당 오류로 인해 문자열 변환에 실패한 경우 이 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)을 throw합니다. 다른 오류 상태에서이 함수는 [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

## <a name="colecurrency-relational-operators"></a><a name="colecurrency_relational_operators"></a>COleCurrency 관계형 연산자

두 통화 값을 비교하고 조건이 true인 경우 비0을 반환합니다. 그렇지 않으면 0.

```
BOOL operator==(const COleCurrency& cur) const;
BOOL operator!=(const COleCurrency& cur) const;
BOOL operator<(const COleCurrency& cur) const;
BOOL operator>(const COleCurrency& cur) const;
BOOL operator<=(const COleCurrency& cur) const;
BOOL operator>=(const COleCurrency& cur) const;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 순서 작업 **<**(, 의 ** \< ** **>** 반환 **>=** 값) 피연산자의 상태가 null 또는 유효하지 않은 경우 정의되지 않습니다. 같음 연산자 (, `==`) `!=`는 나연의 상태를 고려한다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

## <a name="colecurrencysetcurrency"></a><a name="setcurrency"></a>COle 통화 ::설정 통화

이 멤버 함수를 호출하여 이 `COleCurrency` 개체의 단위 및 소수 부분을 설정합니다.

```cpp
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>매개 변수

*nUnits,* *nFractionalUnits* 이 `COleCurrency` 개체에 복사할 값의 단위 및 소수 부분(1/10,000)을 나타냅니다.

### <a name="remarks"></a>설명

소수 부분의 절대 값이 10,000보다 크면 다음 예제의 세 번째 예와 같이 단위에 대한 적절한 조정이 이루어집니다.

단위 및 소수 부분은 서명된 긴 값으로 지정됩니다. 다음 예제의 네 번째 예는 매개 변수에 다른 징후가 있을 때 발생하는 일을 보여 주며 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

## <a name="colecurrencysetstatus"></a><a name="setstatus"></a>COle 통화::설정 상태

이 멤버 함수를 호출하여 이 `COleCurrency` 개체의 상태(유효성)를 설정합니다.

```cpp
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
이 `COleCurrency` 개체의 새 상태입니다.

### <a name="remarks"></a>설명

*상태* 매개 변수 값은 `CurrencyStatus` 클래스 내에서 정의된 수거된 `COleCurrency` 형식에 의해 정의됩니다.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

이러한 상태 값에 대한 간략한 설명은 다음 목록을 참조하십시오.

- `COleCurrency::valid`이 `COleCurrency` 개체가 유효하다는 것을 나타냅니다.

- `COleCurrency::invalid`이 `COleCurrency` 개체가 잘못되었음을 나타냅니다. 즉, 해당 값이 올바르지 않을 수 있습니다.

- `COleCurrency::null`이 `COleCurrency` 개체가 null, 즉 이 개체에 대해 제공된 값이 없음을 나타냅니다. (C++ NULL과 반대로 "값이 없음"의 데이터베이스 의미에서 "null"입니다.)

> [!CAUTION]
> 이 함수는 고급 프로그래밍 상황에 적합합니다. 이 함수는 이 개체의 데이터를 변경하지 않습니다. 상태를 null 또는 유효하지 않은 상태로 설정하는 데 가장 자주 사용됩니다. 할당 연산자 [(연산자 =](#operator_eq)) 및 [SetCurrency는](#setcurrency) 소스 값에 따라 개체의 상태를 설정합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COle변형 클래스](../../mfc/reference/colevariant-class.md)
