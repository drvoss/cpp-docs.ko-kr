---
title: CMFCAcceleratorKey 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
ms.openlocfilehash: a814618d3bda27d5b4ace12209dd93343ef2eef9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751785"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey 클래스

가상 키 매핑 및 서식을 구현하는 도우미 클래스입니다.

## <a name="syntax"></a>구문

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCAccelerator키::CMFCAcceleratorKey키](#cmfcacceleratorkey)|`CMFCAcceleratorKey` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCAccelerator키::형식](#format)|ACCEL 구조를 시각적 표현으로 변환합니다.|
|[CMFCAccelerator키::세아셀러레이터](#setaccelerator)|개체의 바로 가기 `CMFCAcceleratorKey` 키를 설정합니다.|

## <a name="remarks"></a>설명

가속기 키는 바로 가기 키라고도 합니다. 사용자가 입력하는 키보드 단축키를 표시하려면 [CMFCAcceleratorKeyAssignCtrl 클래스가](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) Alt+Shift+S와 같은 키보드 단축키를 "Alt + Shift + S"와 같은 사용자 지정 텍스트 형식으로 매핑합니다. 각 `CMFCAcceleratorKey` 개체는 단일 바로 가기 키를 텍스트 형식에 매핑합니다.

바로 가기 키 및 가속기 테이블을 사용하는 방법에 대한 자세한 내용은 [CKeyboardManager 클래스를](../../mfc/reference/ckeyboardmanager-class.md)참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 개체를 `CMFCAcceleratorKey` 생성 하는 방법 및 `Format` 해당 메서드를 사용 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>요구 사항

**헤더:** afxacceleratorkey.h

## <a name="cmfcacceleratorkeycmfcacceleratorkey"></a><a name="cmfcacceleratorkey"></a>CMFCAccelerator키::CMFCAcceleratorKey키

[CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 개체를 생성합니다.

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>매개 변수

*lpAccel*<br/>
【인】 바로 가기 키에 대한 포인터입니다.

### <a name="remarks"></a>설명

를 만들 `CMFCAccleratorKey`때 바로 가기 키를 제공하지 않는 경우 [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) 메서드를 사용하여 `CMFCAcceleratorKey` 바로 가기 키를 개체와 연결합니다.

## <a name="cmfcacceleratorkeyformat"></a><a name="format"></a>CMFCAccelerator키::형식

ACCEL 구조를 연결된 문자열 값으로 변환합니다.

```cpp
void Format(CString& str) const;
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
【아웃】 메서드가 `CString` 번역된 바로 가기 키를 쓰는 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드는 연결된 바로 가기 키의 문자열 형식을 검색합니다. 생성자 또는 메서드 [CMFCAcceleratorKey::SetAccelerator를](#setaccelerator)사용 하 여 [CMFCAccelerator](../../mfc/reference/cmfcacceleratorkey-class.md) Key의 문자열 형식을 설정할 수 있습니다.

## <a name="cmfcacceleratorkeysetaccelerator"></a><a name="setaccelerator"></a>CMFCAccelerator키::세아셀러레이터

[CMFCAcceleratorKey 키](../../mfc/reference/cmfcacceleratorkey-class.md) 개체의 바로 가기 키를 설정합니다.

```cpp
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>매개 변수

*lpAccel*<br/>
【인】 바로 가기 키에 대한 포인터입니다.

### <a name="remarks"></a>설명

을 만들 때 바로 가기 키를 제공하지 않은 `CMFCAcceleratorKey` 경우 에 대한 바로 `CMFCAcceleratorKey`가기 키를 설정하려면 이 메서드를 사용합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[C키보드관리자 클래스](../../mfc/reference/ckeyboardmanager-class.md)
