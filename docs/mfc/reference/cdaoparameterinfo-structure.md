---
title: CDaoParameterInfo 구조체
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 6d594bbeec34e400eb074c136e3467e78b35c4ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368976"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo 구조체

구조에는 `CDaoParameterInfo` DAO(데이터 액세스 개체)에 대해 정의된 매개 변수 개체에 대한 정보가 포함되어 있습니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다.

## <a name="syntax"></a>구문

```
struct CDaoParameterInfo
{
    CString m_strName;       // Primary
    short m_nType;           // Primary
    ColeVariant m_varValue;  // Secondary
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
매개 변수 개체의 이름을 고유하게 지정합니다. 자세한 내용은 DAO 도움말의 "이름 속성" 항목을 참조하십시오.

*m_nType*<br/>
매개 변수 개체의 데이터 형식을 나타내는 값입니다. 가능한 값 목록은 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조의 *m_nType* 멤버를 참조하십시오. 자세한 내용은 DAO 도움말의 "속성 유형" 항목을 참조하십시오.

*m_varValue*<br/>
[COleVariant](../../mfc/reference/colevariant-class.md) 개체에 저장된 매개 변수의 값입니다.

## <a name="remarks"></a>설명

위의 기본 및 보조에 대한 참조는 클래스의 `CDaoQueryDef` [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 멤버 함수에서 정보를 반환하는 방법을 나타냅니다.

MFC는 클래스에서 DAO 매개 변수 개체를 캡슐화하지 않습니다. MFC `CDaoQueryDef` 개체의 기본 DAO querydef 개체는 매개 변수 컬렉션에 매개 변수를 저장합니다. [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 개체의 매개 변수 개체에 액세스하려면 특정 `GetParameterInfo` 매개 변수 이름에 대한 querydef 개체의 멤버 함수를 호출하거나 인덱스를 매개 변수 컬렉션에 호출합니다. [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) 멤버 함수를 `GetParameterInfo` 함께 사용하여 매개 변수 컬렉션을 반복할 수 있습니다.

[CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 멤버 함수에서 검색한 정보는 `CDaoParameterInfo` 구조체에 저장됩니다. 매개 `GetParameterInfo` 변수 수집 매개 변수 개체가 저장 되는 querydef 개체에 대 한 호출합니다.

> [!NOTE]
> 매개 변수의 값만 얻거나 설정하려면 `CDaoRecordset` [클래스의 GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) 및 [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) 멤버 함수를 사용합니다.

`CDaoParameterInfo`또한 디버그 `Dump` 빌드에서 멤버 함수를 정의합니다. 개체의 `Dump` 내용을 덤프하는 데 사용할 수 있습니다. `CDaoParameterInfo`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고 항목

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)
