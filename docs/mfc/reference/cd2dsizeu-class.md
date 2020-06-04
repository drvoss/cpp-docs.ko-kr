---
title: CD2DSizeU 클래스
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
ms.openlocfilehash: a5b87fe2ddd8fb32ddbbb2884c630952afdb079c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359286"
---
# <a name="cd2dsizeu-class"></a>CD2DSizeU 클래스

D2D1_SIZE_U 위한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|오버로드되었습니다. 개체에서 `D2D1_SIZE_U` `CD2DSizeU` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2DSizeU::IsNull](#isnull)|식에 유효한 데이터(NULL)가 포함되어 있지 않은지 여부를 나타내는 **부울** 값을 반환합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2DSizeU::연산자 CSize](#operator_csize)|개체로 `CD2DSizeU` `CSize` 변환합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_SIZE_U`

[CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dsizeucd2dsizeu"></a><a name="cd2dsizeu"></a>CD2DSizeU::CD2DSizeU

CSize 개체에서 CD2DSizeU 개체를 생성합니다.

```
CD2DSizeU(const CSize& size);
CD2DSizeU(const D2D1_SIZE_U& size);
CD2DSizeU(const D2D1_SIZE_U* size);

CD2DSizeU(
    UINT32 cx = 0,
    UINT32 cy = 0);
```

### <a name="parameters"></a>매개 변수

*크기*<br/>
소스 크기

*Cx*<br/>
소스 너비

*Cy*<br/>
소스 높이

## <a name="cd2dsizeuisnull"></a><a name="isnull"></a>CD2DSizeU::IsNull

식에 유효한 데이터(Null)가 포함되어 있지 않은지 여부를 나타내는 부울 값을 반환합니다.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Return Value

너비와 높이가 비어 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cd2dsizeuoperator-csize"></a><a name="operator_csize"></a>CD2DSizeU::연산자 CSize

CD2DSizeU를 CSize 개체로 변환합니다.

```
operator CSize();
```

### <a name="return-value"></a>Return Value

D2D 크기의 현재 값입니다.

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
