---
title: 'TN002: 영구 개체 데이터 형식'
ms.date: 11/04/2016
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
ms.openlocfilehash: f65a7b7afcf6bd832c9c23560bb29374038fae1b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370449"
---
# <a name="tn002-persistent-object-data-format"></a>TN002: 영구 개체 데이터 형식

이 노트에서는 영구 C++ 개체를 지원하는 MFC 루틴과 파일에 저장될 때 개체 데이터의 형식을 설명합니다. 이는 [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로가 있는 클래스에만 적용됩니다.

## <a name="the-problem"></a>문제

영구 데이터에 대한 MFC 구현은 파일의 단일 인접 부분에 여러 개체에 대한 데이터를 저장합니다. 개체의 `Serialize` 메서드는 개체의 데이터를 압축 이진 형식으로 변환합니다.

구현은 모든 데이터가 [CArchive 클래스를](../mfc/reference/carchive-class.md)사용하여 동일한 형식으로 저장되도록 보장합니다. 개체를 `CArchive` 번역기로 사용합니다. 이 개체는 [CArchive::Close](../mfc/reference/carchive-class.md#close)를 호출할 때까지 생성된 시점부터 유지됩니다. 이 메서드는 프로그래머에 의해 명시적으로 호출되거나 프로그램이 `CArchive`를 포함하는 범위를 종료할 때 소멸자가 암시적으로 호출할 수 있습니다.

이 노트는 `CArchive` 멤버 [CArchive::ReadObject](../mfc/reference/carchive-class.md#readobject) 및 [CArchive::WriteObject](../mfc/reference/carchive-class.md#writeobject)의 구현에 대해 설명합니다. Arcobj.cpp에서 이러한 함수에 대한 `CArchive` 코드와 Arccore.cpp의 주요 구현을 찾을 수 있습니다. 사용자 코드는 `ReadObject` `WriteObject` 직접 호출되지 않습니다. 대신 이러한 개체는 DECLARE_SERIAL 및 IMPLEMENT_SERIAL 매크로에 의해 자동으로 생성되는 클래스별 형식 안전 삽입 및 추출 연산자에서 사용됩니다. 다음 코드는 `WriteObject` 암시적으로 `ReadObject` 호출되는 방법과 방법을 보여 주며 다음과 같습니다.

```
class CMyObject : public CObject
{
    DECLARE_SERIAL(CMyObject)
};

IMPLEMENT_SERIAL(CMyObj, CObject, 1)

// example usage (ar is a CArchive&)
CMyObject* pObj;
CArchive& ar;
ar <<pObj;        // calls ar.WriteObject(pObj)
ar>> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))
```

## <a name="saving-objects-to-the-store-carchivewriteobject"></a>저장소에 개체 저장(CArchive::WriteObject)

메서드는 `CArchive::WriteObject` 개체를 다시 구성하는 데 사용되는 헤더 데이터를 씁니다. 이 데이터는 개체의 유형과 개체의 상태라는 두 부분으로 구성됩니다. 이 메서드는 또한 기록 되는 개체의 ID를 유지 하는 책임, 그래서 단일 복사본만 저장 됩니다., 해당 개체에 대 한 포인터의 수에 관계 없이 (원형 포인터 포함).

저장(삽입) 및 복원(추출) 개체는 여러 "매니페스트 상수"를 사용합니다. 이진에 저장되고 아카이브에 중요한 정보를 제공하는 값입니다("w" 접두사는 16비트 수량을 나타냅니다).

|태그|Description|
|---------|-----------------|
|wNullTag|NULL 개체 포인터(0)에 사용됩니다.|
|w뉴클래스태그|다음에 있는 클래스 설명이 이 아카이브 컨텍스트(-1)에 새로 접하는 것을 나타냅니다.|
|wOldClassTag|이 컨텍스트(0x8000)에서 읽히는 개체의 클래스를 나타냅니다.|

개체를 저장할 때 아카이브는 저장된 개체에서 32비트 *m_pStoreMap*영구 식별자(PID)로 매핑되는 [CMapPtrToPtr(m_pStoreMap)을](../mfc/reference/cmapptrtoptr-class.md) 유지 관리합니다. PID는 아카이브의 컨텍스트에 저장된 모든 고유 개체와 모든 고유 클래스 이름에 할당됩니다. 이 PID는 1부터 순차적으로 나눠주며, 이 PID는 순차적으로 전달됩니다. 이러한 PID는 아카이브 의 범위를 벗어나는 의미가 없으며, 특히 레코드 번호 또는 기타 ID 항목과 혼동해서는 안 됩니다.

클래스에서 `CArchive` PID는 32비트이지만 0x7FFE보다 크지 않으면 16비트로 기록됩니다. 대형 PID는 0x7FFF로 작성되고 그 다음에 32비트 PID가 작성됩니다. 이렇게 하면 이전 버전에서 만든 프로젝트와의 호환성이 유지됩니다.

일반적으로 전역 삽입 연산자사용으로 개체를 아카이브에 저장하도록 요청하면 NULL [CObject](../mfc/reference/cobject-class.md) 포인터에 대한 검사가 이루어집니다. 포인터가 NULL이면 *wNullTag가* 아카이브 스트림에 삽입됩니다.

포인터가 NULL이 아니고 직렬화될 수 `DECLARE_SERIAL` 있는 경우(클래스는 클래스입니다) 코드는 *m_pStoreMap* 확인하여 개체가 이미 저장되었는지 확인합니다. 이 경우 코드는 해당 개체와 연결된 32비트 PID를 아카이브 스트림에 삽입합니다.

이전에 개체를 저장하지 않은 경우 개체의 개체와 정확한 형식(즉, 클래스)이 이 아카이브 컨텍스트에 새로 추가되었거나 개체가 이미 본 정확한 형식이라는 두 가지 가능성을 고려해야 합니다. 형식이 보였는지 여부를 확인하기 위해 코드는 저장되는 개체와 연결된 `CRuntimeClass` 개체와 일치하는 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 개체에 대한 *m_pStoreMap* 쿼리합니다. 일치하는 경우 *wOldClassTag* 및 이 인덱스의 `OR` 비트별 태그를 `WriteObject` 삽입합니다. `CRuntimeClass` 이 아카이브 컨텍스트에 `WriteObject` 대한 새 경우 해당 클래스에 새 PID를 할당하고 *wNewClassTag* 값 앞에 오는 아카이브에 삽입합니다.

그런 다음 이 클래스의 설명자가 `CRuntimeClass::Store` 메서드를 사용하여 아카이브에 삽입됩니다. `CRuntimeClass::Store`클래스의 스키마 번호(아래 참조)와 클래스의 ASCII 텍스트 이름을 삽입합니다. ASCII 텍스트 이름을 사용한다고 해서 응용 프로그램 전체에서 아카이브의 고유성이 보장되는 것은 아닙니다. 따라서 손상을 방지하려면 데이터 파일에 태그를 연결해야 합니다. 클래스 정보를 삽입한 후 아카이브는 개체를 *m_pStoreMap* 넣은 다음 `Serialize` 메서드를 호출하여 클래스별 데이터를 삽입합니다. 호출하기 `Serialize` 전에 *개체를 m_pStoreMap* 배치하면 개체의 여러 복사본이 저장소에 저장되지 않습니다.

초기 호출자(일반적으로 개체 네트워크의 루트)로 돌아갈 [때CArchive::Close](../mfc/reference/carchive-class.md#close)를 호출해야 합니다. 다른 [CFile](../mfc/reference/cfile-class.md)작업을 수행하려는 경우 보관 `CArchive` 프로그램의 손상을 방지하기 위해 [메서드 Flush를](../mfc/reference/carchive-class.md#flush) 호출해야 합니다.

> [!NOTE]
> 이 구현은 아카이브 컨텍스트당 0x3FFFFFFE 인덱스의 하드 제한을 부과합니다. 이 숫자는 단일 아카이브에 저장할 수 있는 최대 고유 개체 및 클래스 수를 나타내지만 단일 디스크 파일에는 아카이브 컨텍스트가 무제한으로 있을 수 있습니다.

## <a name="loading-objects-from-the-store-carchivereadobject"></a>저장소에서 개체 로드(CArchive::ReadObject)

로드(추출) 개체는 `CArchive::ReadObject` 메서드를 사용하며 `WriteObject`의 반대입니다. 와 `WriteObject` `ReadObject` 마찬가지로 사용자 코드에서 직접 호출되지 않습니다. 사용자 코드는 예상 `ReadObject` `CRuntimeClass`된 호출 하는 형식 안전 추출 연산자를 호출 해야 합니다. 이렇게 하면 추출 작업의 형식 무결성이 보장됩니다.

구현에 `WriteObject` 증가 하는 PID를 할당 하기 때문에 1 (0은 `ReadObject` NULL 개체로 미리 정의 됩니다)로 시작 하 고, 구현 아카이브 컨텍스트의 상태를 유지 하기 위해 배열을 사용할 수 있습니다. PID가 저장소에서 읽을 때 PID가 *m_pLoadArray*현재 상한보다 큰 `ReadObject` 경우 새 개체(또는 클래스 설명)가 뒤따른다는 것을 알 수 있습니다.

## <a name="schema-numbers"></a>스키마 번호

클래스의 `IMPLEMENT_SERIAL` 메서드가 발생할 때 클래스에 할당되는 스키마 번호는 클래스 구현의 "버전"입니다. 스키마는 지정된 개체가 영구적으로 만들어진 횟수가 아니라 클래스의 구현을 나타냅니다(일반적으로 개체 버전이라고 함).

시간이 지남에 따라 동일한 클래스의 여러 다른 구현을 유지 하려는 경우 개체의 `Serialize` 메서드 구현을 수정할 때 스키마를 증가 하면 이전 버전의 구현을 사용 하 여 저장 된 개체를 로드할 수 있는 코드를 작성할 수 있습니다.

메서드는 `CArchive::ReadObject` 메모리에 있는 클래스 설명의 스키마 수와 다른 영구 저장소에 스키마 번호가 발생 하면 [CArchiveException을](../mfc/reference/carchiveexception-class.md) throw 합니다. 이 예외에서 복구하는 것은 쉽지 않습니다.

스키마 `VERSIONABLE_SCHEMA` 버전과 결합하여 **OR**이 예외가 throw되지 않도록 할 수 있습니다. 을 `VERSIONABLE_SCHEMA`사용하여 코드는 `Serialize` [CArchive::GetObjectSchema에서](../mfc/reference/carchive-class.md#getobjectschema)반환 값을 확인하여 함수에서 적절한 작업을 수행할 수 있습니다.

## <a name="calling-serialize-directly"></a>직렬화 직접 호출

대부분의 경우 일반 개체 아카이브 `WriteObject` 스키마의 `ReadObject` 오버헤드는 필요하지 않습니다. 데이터를 [CDocument로](../mfc/reference/cdocument-class.md)직렬화하는 일반적인 경우입니다. 이 경우, `Serialize` 의 `CDocument` 방법은 추출 또는 삽입 연산자가 아니라 직접 호출된다. 문서의 내용은 더 일반적인 개체 아카이브 체계를 사용할 수 있습니다.

직접 `Serialize` 호출하면 다음과 같은 장점과 단점이 있습니다.

- 개체를 직렬화하기 전이나 후에 추가 바이트가 아카이브에 추가되지 않습니다. 이렇게 하면 저장된 데이터가 작아지을 뿐만 `Serialize` 아니라 모든 파일 형식을 처리할 수 있는 루틴을 구현할 수 있습니다.

- 다른 용도로 더 `WriteObject` 일반적인 `ReadObject` 개체 아카이브 스키마가 필요하지 않으면 MFC와 구현 및 관련 컬렉션이 응용 프로그램에 연결되지 않도록 조정됩니다.

- 코드는 이전 스키마 번호에서 복구할 필요가 없습니다. 이렇게 하면 문서 직렬화 코드에서 스키마 번호, 파일 형식 버전 번호 또는 데이터 파일 의 시작 부분에 사용하는 모든 식별 번호를 인코딩할 수 있습니다.

- 직접 호출로 `Serialize` 직렬화되는 모든 개체는 `CArchive::GetObjectSchema` 버전을 알 수 없음을 나타내는 반환 값(UINT)-1을 사용하거나 처리해서는 안 됩니다.

문서에서 `Serialize` 직접 호출되므로 일반적으로 문서의 하위 개체가 상위 문서에 대한 참조를 보관할 수 없습니다. 이러한 개체는 컨테이너 문서에 대한 포인터를 명시적으로 제공해야 하거나 [CArchive::MapObject](../mfc/reference/carchive-class.md#mapobject) 함수를 사용하여 포인터를 PID에 매핑한 `CDocument` 다음 이러한 백 포인터를 보관해야 합니다.

앞서 설명했듯이 직접 호출할 `Serialize` 때 버전 및 클래스 정보를 직접 인코딩하여 이전 파일과의 이전 버전 호환성을 유지하면서 나중에 형식을 변경할 수 있도록 해야 합니다. 함수는 `CArchive::SerializeClass` 개체를 직접 직렬화하기 전에 또는 기본 클래스를 호출하기 전에 명시적으로 호출할 수 있습니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
