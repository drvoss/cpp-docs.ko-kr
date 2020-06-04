---
title: CLongBinary 클래스
ms.date: 11/04/2016
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
helpviewer_keywords:
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
ms.openlocfilehash: 1ce1daba90f3a1dad4b9627082d63f1b3405eab4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370131"
---
# <a name="clongbinary-class"></a>CLongBinary 클래스

데이터베이스에서 매우 큰 이진 데이터 개체(BLOB 또는 "이진 대형 개체"라고도 함) 사용 작업을 간소화합니다.

## <a name="syntax"></a>구문

```
class CLongBinary : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CLong 바이너리 ::CLong Binary](#clongbinary)|`CLongBinary` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CLong 바이너리::m_dwDataLength](#m_dwdatalength)|핸들이 에 저장되는 데이터 개체의 바이트로 `m_hData`실제 크기를 포함합니다.|
|[CLong바이너리::m_hData](#m_hdata)|실제 이미지 개체에 대한 Windows HGLOBAL 핸들을 포함합니다.|

## <a name="remarks"></a>설명

예를 들어 SQL 테이블의 레코드 필드에는 그림을 나타내는 비트맵이 포함될 수 있습니다. 개체는 `CLongBinary` 이러한 개체를 저장하고 크기를 추적합니다.

> [!NOTE]
> 일반적으로 [DFX_Binary](record-field-exchange-functions.md#dfx_binary) 함수와 함께 [CByteArray를](../../mfc/reference/cbytearray-class.md) 사용하는 것이 좋습니다. 여전히 사용할 `CLongBinary`수 있지만 `CByteArray` 일반적으로 Win32에서 더 많은 기능을 `CByteArray`제공합니다. 이 조언은 DAO(데이터 액세스 개체)와 ODBC(개방형 데이터베이스 연결)를 통한 프로그래밍에 적용됩니다.

개체를 `CLongBinary` 사용하려면 레코드 집합 클래스에서 `CLongBinary` 형식의 필드 데이터 멤버를 선언합니다. 이 멤버는 레코드 집합 클래스의 포함된 멤버가 되며 레코드 집합이 생성될 때 생성됩니다. 개체를 `CLongBinary` 생성한 후 RFX(레코드 필드 교환) 메커니즘은 데이터 원본의 현재 레코드에 있는 필드에서 데이터 개체를 로드하고 레코드가 업데이트될 때 레코드에 다시 저장합니다. RFX는 이진 큰 개체의 크기에 대한 데이터 원본을 쿼리하고, `CLongBinary` 개체의 `m_hData` 데이터 멤버를 통해 `HGLOBAL` 저장소를 할당하고, 에 있는 데이터에 핸들을 `m_hData`저장합니다. RFX는 데이터 개체의 실제 크기도 `m_dwDataLength` 데이터 멤버에 저장합니다. 을 `m_hData` `HGLOBAL` 통해 개체의 데이터로 작업하는 데 일반적으로 Windows 핸들에 저장된 데이터를 조작하는 데 사용하는 것과 동일한 기술을 사용합니다.

레코드 집합을 삭제하면 포함된 `CLongBinary` 개체도 소멸되고 소멸자가 데이터 핸들을 `HGLOBAL` 할당 합니다.

큰 개체 및 사용 `CLongBinary`방법에 대한 자세한 내용은 레코드 [집합(ODBC)](../../data/odbc/recordset-odbc.md) 및 레코드 [집합: 대용량 데이터 항목(ODBC) 작업](../../data/odbc/recordset-working-with-large-data-items-odbc.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb_.h

## <a name="clongbinaryclongbinary"></a><a name="clongbinary"></a>CLong 바이너리 ::CLong Binary

`CLongBinary` 개체를 생성합니다.

```
CLongBinary();
```

## <a name="clongbinarym_dwdatalength"></a><a name="m_dwdatalength"></a>CLong 바이너리::m_dwDataLength

HGLOBAL 핸들에 저장된 데이터의 바이트로 실제 크기를 `m_hData`저장합니다.

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>설명

이 크기는 데이터에 할당된 메모리 블록의 크기보다 작을 수 있습니다. Win32 [GLobalSize](/windows/win32/api/winbase/nf-winbase-globalsize) 함수를 호출하여 할당된 크기를 가져옵니다.

## <a name="clongbinarym_hdata"></a><a name="m_hdata"></a>CLong바이너리::m_hData

Windows HGLOBAL 핸들을 실제 이진 큰 개체 데이터에 저장합니다.

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>참고 항목

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)
