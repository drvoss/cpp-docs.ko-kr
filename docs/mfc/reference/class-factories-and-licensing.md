---
title: 클래스 팩터리 및 라이선스
ms.date: 11/04/2016
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
ms.openlocfilehash: e3fed6520cdbe0fd964e4e80e7c9ed9b78296d16
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372304"
---
# <a name="class-factories-and-licensing"></a>클래스 팩터리 및 라이선스

OLE 컨트롤의 인스턴스를 만들려면 컨테이너 응용 프로그램은 컨트롤의 클래스 팩터리의 멤버 함수를 호출합니다. 컨트롤은 실제 OLE 개체이므로 클래스 팩터리는 컨트롤의 인스턴스를 만듭니다. 모든 OLE 컨트롤 클래스에는 클래스 팩터리가 있어야 합니다.

OLE 컨트롤의 또 다른 중요한 기능은 라이센스를 적용하는 기능입니다. ControlWizard를 사용하면 컨트롤 프로젝트를 만드는 동안 라이선스를 통합할 수 있습니다. 제어 라이선스에 대한 자세한 내용은 [ActiveX 컨트롤: ActiveX 컨트롤 라이선스](../../mfc/mfc-activex-controls-licensing-an-activex-control.md)를 참조하세요.

다음 표에는 컨트롤의 클래스 팩터리를 선언하고 구현하고 컨트롤의 라이선스를 부여하는 데 사용되는 몇 가지 매크로 및 함수가 나열되어 있습니다.

### <a name="class-factories-and-licensing"></a>클래스 팩터리 및 라이선스

|||
|-|-|
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|OLE 컨트롤 또는 속성 페이지에 대 한 클래스 팩터리를 선언 합니다.|
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|컨트롤의 `GetClassID` 함수를 구현 하 고 클래스 팩터리의 인스턴스를 선언 합니다.|
|[BEGIN_OLEFACTORY](#begin_olefactory)|모든 라이선싱 함수의 선언을 시작합니다.|
|[END_OLEFACTORY](#end_olefactory)|모든 라이선스 함수의 선언을 종료합니다.|
|[AfxVerifyLicFile](#afxverifylicfile)|특정 컴퓨터에서 사용할 수 있는 컨트롤의 라이센스가 있는지 여부를 확인합니다.|

## <a name="declare_olecreate_ex"></a><a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX

클래스 팩터리 및 `GetClassID` 컨트롤 클래스의 멤버 함수를 선언합니다.

```
DECLARE_OLECREATE_EX(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
컨트롤 클래스의 이름입니다.

### <a name="remarks"></a>설명

이 매크로를 컨트롤 클래스 헤더 파일에서 사용 권한을 지원하지 않는 컨트롤에 사용합니다.

이 매크로는 다음 코드 샘플과 동일한 용도로 사용됩니다.

[!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

## <a name="implement_olecreate_ex"></a><a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX

컨트롤의 클래스 팩터리 및 컨트롤 클래스의 [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) 멤버 함수를 구현합니다.

```
IMPLEMENT_OLECREATE_EX(
   class_name,
    external_name,
    l,
    w1,
    w2,
    b1,
    b2,
    b3,
    b4,
    b5,
    b6,
    b7,
    b8)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
컨트롤 속성 페이지 클래스의 이름입니다.

*external_name*<br/>
응용 프로그램에 노출된 개체 이름입니다.

*l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*<br/>
클래스의 CLSID 구성 요소입니다. 이러한 매개 변수에 대한 자세한 내용은 [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate)에 대한 설명서를 참조하십시오.

### <a name="remarks"></a>설명

이 매크로는 DECLARE_OLECREATE_EX 매크로 또는 BEGIN_OLEFACTORY 및 END_OLEFACTORY 매크로를 사용하는 모든 컨트롤 클래스의 구현 파일에 나타나야 합니다. 외부 이름은 다른 응용 프로그램에 노출되는 OLE 컨트롤의 식별자입니다. 컨테이너는 이 이름을 사용하여 이 컨트롤 클래스의 개체를 요청합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

## <a name="begin_olefactory"></a><a name="begin_olefactory"></a>BEGIN_OLEFACTORY

컨트롤 클래스의 헤더 파일에서 클래스 팩터리 선언을 시작합니다.

```
BEGIN_OLEFACTORY(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스 팩터리인 컨트롤 클래스의 이름을 지정합니다.

### <a name="remarks"></a>설명

클래스 공장 라이센스 함수의 선언은 BEGIN_OLEFACTORY 직후에 시작되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

## <a name="end_olefactory"></a><a name="end_olefactory"></a>END_OLEFACTORY

컨트롤의 클래스 팩터리 선언을 종료합니다.

```
END_OLEFACTORY(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스 팩터리인 컨트롤 클래스의 이름입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

## <a name="afxverifylicfile"></a><a name="afxverifylicfile"></a>AfxVerifyLicFile

이 함수를 호출하여 이름이 지정된 `pszLicFileName` 라이센스 파일이 OLE 컨트롤에 유효한지 확인합니다.

```
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,
    LPCTSTR  pszLicFileName,
    LPOLESTR  pszLicFileContents,
    UINT cch = -1);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
라이센스가 부여된 컨트롤과 연결된 DLL의 인스턴스 핸들입니다.

*pszLicFile네임*<br/>
라이센스 파일 이름을 포함하는 null 종료 된 문자 문자열을 가리킵니다.

*pszLicFile 콘텐츠*<br/>
라이센스 파일의 시작 부분에 있는 시퀀스와 일치해야 하는 바이트 시퀀스를 가리킵니다.

*Cch*<br/>
*pszLicFile콘텐츠의*문자 수 .

### <a name="return-value"></a>Return Value

라이센스 파일이 존재하고 *pszLicFileContents의*문자 시퀀스로 시작하는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

*cch가* -1이면 이 함수는 다음을 사용합니다.

[!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
