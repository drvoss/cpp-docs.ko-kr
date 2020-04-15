---
title: FtmBase 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
- ftm/Microsoft::WRL::FtmBaseCreateGlobalInterfaceTable
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
- ftm/Microsoft::WRL::FtmBase::FtmBase
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
- ftm/Microsoft::WRL::FtmBase::marshaller_
- ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
helpviewer_keywords:
- Microsoft::WRL::FtmBase class
- Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable method
- Microsoft::WRL::FtmBase::DisconnectObject method
- Microsoft::WRL::FtmBase::FtmBase, constructor
- Microsoft::WRL::FtmBase::GetMarshalSizeMax method
- Microsoft::WRL::FtmBase::GetUnmarshalClass method
- Microsoft::WRL::FtmBase::MarshalInterface method
- Microsoft::WRL::FtmBase::marshaller_ data member
- Microsoft::WRL::FtmBase::ReleaseMarshalData method
- Microsoft::WRL::FtmBase::UnmarshalInterface method
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
ms.openlocfilehash: d37cdddda8cf8894016ed80b9055fe106b1600f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371508"
---
# <a name="ftmbase-class"></a>FtmBase 클래스

자유 스레드된 마샬러 개체를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class FtmBase :
    public Microsoft::WRL::Implements<
        Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,
        Microsoft::WRL::CloakedIid<IMarshal>
    >;
```

## <a name="remarks"></a>설명

자세한 내용은 [런타임클래스 클래스](runtimeclass-class.md)를 참조하십시오.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

| 속성                         | Description                                        |
| ---------------------------- | -------------------------------------------------- |
| [FtmBase::FtmBase](#ftmbase) | `FtmBase` 클래스의 새 인스턴스를 초기화합니다. |

### <a name="public-methods"></a>Public 메서드

| 속성                                                               | Description                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [FtmBase::만들기 글로벌 인터페이스테이블](#createglobalinterfacetable) | GIT(전역 인터페이스 테이블)를 만듭니다.                                                                                                                              |
| [FtmBase::DisconnectObject](#disconnectobject)                     | 개체에 대한 모든 외부 연결을 강제로 해제합니다. 개체의 서버는 종료하기 전에 이 메서드의 개체 구현을 호출합니다.                |
| [FtmBase::겟마샬사이즈맥스](#getmarshalsizemax)                   | 지정된 개체에서 지정된 인터페이스 포인터를 마샬링하는 데 필요한 바이트 수에 대한 상한을 가져옵니다.                                                |
| [FtmBase::GetUnmarshalClass](#getunmarshalclass)                   | COM이 해당 프록시에 대한 코드를 포함하는 DLL을 찾는 데 사용하는 CLSID를 가져옵니다. COM은 이 DLL을 로드하여 프록시의 초기화되지 않은 인스턴스를 만듭니다. |
| [FtmBase::마샬인터페이스](#marshalinterface)                     | 일부 클라이언트 프로세스에서 프록시 개체를 초기화하는 데 필요한 데이터를 스트림에 씁니다.                                                                          |
| [FtmBase::릴리스마샬데이터](#releasemarshaldata)                 | 마샬링된 데이터 패킷을 삭제합니다.                                                                                                                                    |
| [FtmBase::마샬링 인터페이스](#unmarshalinterface)                 | 새로 만든 프록시를 초기화하고 해당 프록시에 인터페이스 포인터를 반환합니다.                                                                                    |

### <a name="public-data-members"></a>공용 데이터 멤버

| 속성                                | Description                                       |
| ----------------------------------- | ------------------------------------------------- |
| [FtmBase::marshaller_](#marshaller) | 스레드가 없는 마샬러에 대한 참조를 보유합니다. |

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`FtmBase`

## <a name="requirements"></a>요구 사항

**헤더:** ftm.h

**네임스페이스:** Microsoft::WRL

## <a name="ftmbasecreateglobalinterfacetable"></a><a name="createglobalinterfacetable"></a>FtmBase::만들기 글로벌 인터페이스테이블

GIT(전역 인터페이스 테이블)를 만듭니다.

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>매개 변수

*Git*<br/>
이 작업이 완료되면 전역 인터페이스 테이블에 대한 포인터가 됩니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

자세한 내용은 MSDN 라이브러리의 `IGlobalInterfaceTable` `COM Interfaces` `COM Reference` 주제 하위 주제에 대한 항목을 참조하십시오.

## <a name="ftmbasedisconnectobject"></a><a name="disconnectobject"></a>FtmBase::DisconnectObject

개체에 대한 모든 외부 연결을 강제로 해제합니다. 개체의 서버는 종료하기 전에 이 메서드의 개체 구현을 호출합니다.

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>매개 변수

*dwReserved*<br/>
나중에 사용하도록 예약되어 있습니다. 0이어야 합니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="ftmbaseftmbase"></a><a name="ftmbase"></a>FtmBase::FtmBase

`FtmBase` 클래스의 새 인스턴스를 초기화합니다.

```cpp
FtmBase();
```

## <a name="ftmbasegetmarshalsizemax"></a><a name="getmarshalsizemax"></a>FtmBase::겟마샬사이즈맥스

지정된 개체에서 지정된 인터페이스 포인터를 마샬링하는 데 필요한 바이트 수에 대한 상한을 가져옵니다.

```cpp
STDMETHODIMP GetMarshalSizeMax(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out DWORD *pSize
) override;
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
마샬링할 인터페이스의 식별자를 참조합니다.

*태양광 발전*<br/>
마샬링할 인터페이스 포인터; NULL이 될 수 있습니다.

*dwDest컨텍스트*<br/>
지정된 인터페이스를 마샬링하지 않을 대상 컨텍스트입니다.

하나 이상의 MSHCTX 열거 값을 지정합니다.

현재 마샬링 해제는 현재 프로세스의 다른 아파트(MSHCTX_INPROC) 또는 현재 프로세스(MSHCTX_LOCAL)와 동일한 컴퓨터의 다른 프로세스에서 발생할 수 있습니다.

*pvDest컨텍스트*<br/>
향후 사용을 위해 예약; NULL이어야 합니다.

*mshlflags*<br/>
마샬링할 데이터가 클라이언트 프로세스(일반적인 경우)로 다시 전송될지 또는 여러 클라이언트에서 검색할 수 있는 전역 테이블에 기록되는지 여부를 나타내는 플래그입니다. 하나 이상의 MSHLFLAGS 열거 값을 지정합니다.

*pSize*<br/>
이 작업이 완료되면 마샬링 스트림에 기록할 데이터 양에 대한 상한에 대한 포인터가 됩니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 E_FAIL 또는 E_NOINTERFACE.

## <a name="ftmbasegetunmarshalclass"></a><a name="getunmarshalclass"></a>FtmBase::GetUnmarshalClass

COM이 해당 프록시에 대한 코드를 포함하는 DLL을 찾는 데 사용하는 CLSID를 가져옵니다. COM은 이 DLL을 로드하여 프록시의 초기화되지 않은 인스턴스를 만듭니다.

```cpp
STDMETHODIMP GetUnmarshalClass(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out CLSID *pCid
) override;
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
마샬링할 인터페이스의 식별자를 참조합니다.

*태양광 발전*<br/>
마샬링할 인터페이스에 대한 포인터; 호출자에게 원하는 인터페이스에 대한 포인터가 없는 경우 NULL이 될 수 있습니다.

*dwDest컨텍스트*<br/>
지정된 인터페이스를 마샬링하지 않을 대상 컨텍스트입니다.

하나 이상의 MSHCTX 열거 값을 지정합니다.

마샬링 해제는 현재 프로세스의 다른 아파트(MSHCTX_INPROC) 또는 현재 프로세스와 동일한 컴퓨터의 다른 프로세스(MSHCTX_LOCAL)에서 발생할 수 있습니다.

*pvDest컨텍스트*<br/>
향후 사용을 위해 예약; NULL이어야 합니다.

*mshlflags*<br/>
이 작업이 완료되면 클라이언트 프로세스에서 프록시를 만드는 데 사용할 CLSID에 대한 포인터입니다.

*pCid*

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면, S_FALSE.

## <a name="ftmbasemarshalinterface"></a><a name="marshalinterface"></a>FtmBase::마샬인터페이스

일부 클라이언트 프로세스에서 프록시 개체를 초기화하는 데 필요한 데이터를 스트림에 씁니다.

```cpp
STDMETHODIMP MarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags
) override;
```

### <a name="parameters"></a>매개 변수

*pStm*<br/>
마샬링 중에 사용할 스트림에 대한 포인터입니다.

*riid*<br/>
마샬링할 인터페이스의 식별자를 참조합니다. 이 인터페이스는 `IUnknown` 인터페이스에서 파생되어야 합니다.

*태양광 발전*<br/>
마샬링할 인터페이스 포인터에 대한 포인터; 호출자에게 원하는 인터페이스에 대한 포인터가 없는 경우 NULL이 될 수 있습니다.

*dwDest컨텍스트*<br/>
지정된 인터페이스를 마샬링하지 않을 대상 컨텍스트입니다.

하나 이상의 MSHCTX 열거 값을 지정합니다.

마샬링 해제는 현재 프로세스의 다른 아파트(MSHCTX_INPROC) 또는 현재 프로세스(MSHCTX_LOCAL)와 동일한 컴퓨터의 다른 프로세스에서 발생할 수 있습니다.

*pvDest컨텍스트*<br/>
나중에 사용하도록 예약되어 있습니다. 0이어야 합니다.

*mshlflags*<br/>
마샬링할 데이터를 클라이언트 프로세스(일반적인 경우)로 다시 전송할지 아니면 여러 클라이언트에서 검색할 수 있는 전역 테이블에 기록할지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

S_OK 인터페이스 포인터가 성공적으로 마샬링되었습니다.

E_NOINTERFACE 지정된 인터페이스가 지원되지 않습니다.

STG_E_MEDIUMFULL 스트림이 가득 찼습니다.

E_FAIL 작업이 실패했습니다.

## <a name="ftmbasemarshaller_"></a><a name="marshaller"></a>FtmBase::marshaller_

스레드가 없는 마샬러에 대한 참조를 보유합니다.

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="ftmbasereleasemarshaldata"></a><a name="releasemarshaldata"></a>FtmBase::릴리스마샬데이터

마샬링된 데이터 패킷을 삭제합니다.

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>매개 변수

*pStm*<br/>
소멸할 데이터 패킷을 포함하는 스트림에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="ftmbaseunmarshalinterface"></a><a name="unmarshalinterface"></a>FtmBase::마샬링 인터페이스

새로 만든 프록시를 초기화하고 해당 프록시에 인터페이스 포인터를 반환합니다.

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>매개 변수

*pStm*<br/>
인터페이스 포인터가 마샬링되지 않도록 하는 스트림에 대한 포인터입니다.

*riid*<br/>
마샬링되지 않을 인터페이스의 식별자를 참조합니다.

*ppv*<br/>
이 작업이 완료되면 *riid에서*요청된 인터페이스 포인터를 받는 포인터 변수의 주소입니다. 이 작업이 성공하면 **ppv에는* 마샬링되지 않은 인터페이스의 요청된 인터페이스 포인터가 포함되어 있습니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 E_NOINTERFACE 또는 E_FAIL.
