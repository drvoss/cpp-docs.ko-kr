---
title: DAO 데이터베이스 엔진 초기화 및 종료
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 62460e8e55f70b8cb0743f1d044636d25121050d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365902"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO 데이터베이스 엔진 초기화 및 종료

DAO는 Access 데이터베이스와 함께 사용되며 Office 2013을 통해 지원됩니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다. MFC DAO 개체를 사용하는 경우 DAO 데이터베이스 엔진을 먼저 초기화한 다음 응용 프로그램 또는 DLL이 종료되기 전에 종료해야 합니다. 두 가지 `AfxDaoInit` 기능 `AfxDaoTerm`및 는 이러한 작업을 수행합니다.

### <a name="dao-database-engine-initialization-and-termination"></a>DAO 데이터베이스 엔진 초기화 및 종료

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|DAO 데이터베이스 엔진을 초기화합니다.|
|[AfxDaoTerm](#afxdaoterm)|DAO 데이터베이스 엔진을 종료합니다.|

## <a name="afxdaoinit"></a><a name="afxdaoinit"></a>아프다오이니트

이 함수는 DAO 데이터베이스 엔진을 초기화합니다.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>설명

대부분의 경우 응용 프로그램이 필요할 때 `AfxDaoInit` 자동으로 호출하기 때문에 호출할 필요가 없습니다.

관련 정보 및 호출 `AfxDaoInit`예제는 기술 참고 [54를](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="afxdaoterm"></a><a name="afxdaoterm"></a>아프다오터

이 함수는 DAO 데이터베이스 엔진을 종료합니다.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>설명

일반적으로 일반 MFC DLL에서 이 함수만 호출하면 됩니다. 응용 프로그램이 필요할 `AfxDaoTerm` 때 자동으로 호출됩니다.

일반 MFC DLL에서는 `AfxDaoTerm` `ExitInstance` 함수 앞에 호출하지만 모든 MFC DAO 개체가 소멸된 후에는 호출합니다.

관련 정보는 [기술 참고 54를](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
