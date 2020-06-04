---
title: '연습: 사용자 인터페이스 스레드에서 작업 제거'
ms.date: 08/19/2019
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 52bc98ef339a19c6ec2a53697f532a9a94b6c9a6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377436"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>연습: 사용자 인터페이스 스레드에서 작업 제거

이 문서에서는 동시성 런타임을 사용하여 Microsoft 기초 클래스(MFC) 응용 프로그램의 사용자 인터페이스(UI) 스레드에서 수행되는 작업을 작업자 스레드로 이동하는 방법을 보여 줍니다. 이 문서에서는 긴 도면 작업의 성능을 향상시키는 방법도 보여 줍니다.

차단 작업을 오프로드하여 UI 스레드에서 작업을 제거합니다(예: 그리기) 작업자 스레드로 응용 프로그램의 응답성이 향상될 수 있습니다. 이 연습에서는 Mandelbrot 프랙탈을 생성하는 그리기 루틴을 사용하여 긴 차단 작업을 보여 줍니다. 각 픽셀의 계산은 다른 모든 계산과 독립적이기 때문에 Mandelbrot 프랙탈의 생성은 병렬화에 적합합니다.

## <a name="prerequisites"></a>사전 요구 사항

이 연습을 시작하기 전에 다음 항목을 읽으십시오.

- [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [메시지 전달 기능](../../parallel/concrt/message-passing-functions.md)

- [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)

- [PPL에서의 취소](cancellation-in-the-ppl.md)

또한 이 연습을 시작하기 전에 MFC 응용 프로그램 개발 및 GDI+의 기본 사항에 대해 이해하는 것이 좋습니다. MFC에 대한 자세한 내용은 [MFC 데스크톱 응용 프로그램을](../../mfc/mfc-desktop-applications.md)참조하십시오. GDI+에 대한 자세한 내용은 [GDI+를](/windows/win32/gdiplus/-gdiplus-gdi-start)참조하십시오.

## <a name="sections"></a><a name="top"></a>섹션

이 연습에는 다음과 같은 섹션이 있습니다.

- [MFC 응용 프로그램 만들기](#application)

- [만델브로트 응용 프로그램의 직렬 버전 구현](#serial)

- [사용자 인터페이스 스레드에서 작업 제거](#removing-work)

- [드로잉 성능 향상](#performance)

- [취소 지원 추가](#cancellation)

## <a name="creating-the-mfc-application"></a><a name="application"></a>MFC 응용 프로그램 만들기

이 섹션에서는 기본 MFC 응용 프로그램을 만드는 방법에 대해 설명합니다.

### <a name="to-create-a-visual-c-mfc-application"></a>Visual C++ MFC 응용 프로그램을 만들려면

1. **MFC 응용 프로그램 마법사를** 사용하여 모든 기본 설정이 있는 MFC 응용 프로그램을 만듭니다. [연습: 새 MFC 셸 컨트롤을 사용하여](../../mfc/walkthrough-using-the-new-mfc-shell-controls.md) Visual Studio 버전에 대한 마법사를 여는 방법에 대한 지침을 참조하세요.

1. 예를 들어 `Mandelbrot`프로젝트의 이름을 입력한 다음 **확인을** 클릭하여 **MFC 응용 프로그램 마법사를**표시합니다.

1. 응용 **프로그램 유형** 창에서 **단일 문서를**선택합니다. **문서/아키텍처 지원** 확인란을 선택 취소해야 합니다.

1. **완료를** 클릭하여 프로젝트를 만들고 **MFC 응용 프로그램 마법사를**닫습니다.

   응용 프로그램을 빌드하고 실행하여 응용 프로그램을 성공적으로 만들었는지 확인합니다. 응용 프로그램을 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드를**클릭합니다. 응용 프로그램이 성공적으로 빌드되면 **디버그** 메뉴에서 **디버깅 시작을** 클릭하여 응용 프로그램을 실행합니다.

## <a name="implementing-the-serial-version-of-the-mandelbrot-application"></a><a name="serial"></a>만델브로트 응용 프로그램의 직렬 버전 구현

이 섹션에서는 만델브로트 프랙탈을 그리는 방법에 대해 설명합니다. 이 버전은 만델브로트 프랙탈을 GDI+ [비트맵](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) 개체에 그린 다음 해당 비트맵의 내용을 클라이언트 창에 복사합니다.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>만델브로트 응용 프로그램의 직렬 버전을 구현하려면

1. *pch.h(Visual* Studio 2017 및 이전 의*stdafx.h)에서* 다음 `#include` 지시문을 추가합니다.

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. ChildView.h에서 `pragma` 지시문 뒤에 형식을 `BitmapPtr` 정의합니다. 이 `BitmapPtr` 형식을 사용하면 개체에 대한 포인터를 `Bitmap` 여러 구성 요소에서 공유할 수 있습니다. 개체가 `Bitmap` 더 이상 구성 요소에서 참조되지 않을 때 삭제됩니다.

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. ChildView.h에서 클래스의 섹션에 `protected` 다음 코드를 `CChildView` 추가합니다.

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. ChildView.cpp에서 다음 줄을 주석을 달거나 제거합니다.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   디버그 빌드에서 이 단계는 응용 프로그램이 `DEBUG_NEW` GDI+와 호환되지 않는 할당기를 사용하지 못하게 합니다.

1. ChildView.cpp에서 네임스페이스에 `using` `Gdiplus` 지시문을 추가합니다.

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. 다음 코드를 `CChildView` 클래스의 생성자 및 소멸자에 추가하여 GDI+를 초기화하고 종료합니다.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. `CChildView::DrawMandelbrot` 메서드를 구현합니다. 이 메서드는 Mandelbrot 프랙탈을 `Bitmap` 지정된 개체에 그립니다.

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. `CChildView::OnPaint` 메서드를 구현합니다. 이 메서드는 `CChildView::DrawMandelbrot` `Bitmap` 호출 한 다음 창에 개체의 내용을 복사 합니다.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. 응용 프로그램을 빌드하고 실행하여 응용 프로그램이 성공적으로 업데이트되었는지 확인합니다.

다음 그림에서는 만델브로트 응용 프로그램의 결과를 보여 주시고 있습니다.

![Mandelbrot 응용 프로그램](../../parallel/concrt/media/mandelbrot.png "Mandelbrot 응용 프로그램")

각 픽셀에 대한 계산은 계산 비용이 많이 들기 때문에 UI 스레드는 전체 계산이 완료될 때까지 추가 메시지를 처리할 수 없습니다. 이렇게 하면 응용 프로그램의 응답성이 저하될 수 있습니다. 그러나 UI 스레드에서 작업을 제거하여 이 문제를 해결할 수 있습니다.

【[맨 위](#top)】

## <a name="removing-work-from-the-ui-thread"></a><a name="removing-work"></a>UI 스레드에서 작업 제거

이 섹션에서는 Mandelbrot 응용 프로그램의 UI 스레드에서 그리기 작업을 제거하는 방법을 보여 주며 있습니다. UI 스레드에서 작업자 스레드로 그리기 작업을 이동하면 작업자 스레드가 백그라운드에서 이미지를 생성할 때 메시지를 처리할 수 있습니다.

동시성 런타임은 작업을 실행하는 세 가지 방법( [작업 그룹,](../../parallel/concrt/task-parallelism-concurrency-runtime.md) [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)및 [경량 작업)을](../../parallel/concrt/task-scheduler-concurrency-runtime.md)제공합니다. 이러한 메커니즘 중 하나를 사용하여 UI 스레드에서 작업을 제거할 수 있지만 이 예제에서는 작업 그룹이 취소를 지원하기 [때문에:task_group](reference/task-group-class.md) 개체를 사용합니다. 나중에 이 연습에서는 취소를 사용하여 클라이언트 창의 크기를 조정할 때 수행되는 작업 양을 줄이고 창이 소멸될 때 정리를 수행합니다.

또한 이 예제에서는 [동시성:unbounded_buffer](reference/unbounded-buffer-class.md) 개체를 사용하여 UI 스레드와 작업자 스레드가 서로 통신할 수 있도록 합니다. 작업자 스레드가 이미지를 생성한 후 `Bitmap` 개체에 대한 포인터를 개체에 `unbounded_buffer` 보낸 다음 UI 스레드에 페인트 메시지를 게시합니다. 그런 다음 UI 스레드는 `unbounded_buffer` `Bitmap` 개체에서 개체를 수신하고 클라이언트 창에 그립니다.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>UI 스레드에서 그리기 작업을 제거하려면

1. *pch.h(Visual* Studio 2017 및 이전 의*stdafx.h)에서* 다음 `#include` 지시문을 추가합니다.

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. `task_group` ChildView.h에서 `CChildView` 클래스의 `unbounded_buffer` `protected` 섹션에 변수를 추가하고 멤버합니다. 개체에는 `task_group` 드로잉을 수행하는 작업이 포함됩니다. 개체는 `unbounded_buffer` 완성된 만델브로트 이미지를 보유합니다.

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. ChildView.cpp에서 네임스페이스에 `using` `concurrency` 지시문을 추가합니다.

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. 메서드에서 `CChildView::DrawMandelbrot` `Bitmap::UnlockBits`호출 후 호출 합니다 [.:send](reference/concurrency-namespace-functions.md#send) 함수를 호출 `Bitmap` 하여 개체를 UI 스레드에 전달 합니다. 그런 다음 UI 스레드에 페인트 메시지를 게시하고 클라이언트 영역을 무효화합니다.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. 메서드를 `CChildView::OnPaint` 업데이트하여 업데이트된 `Bitmap` 개체를 수신하고 클라이언트 창에 이미지를 그립니다.

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   메서드는 `CChildView::OnPaint` 메시지 버퍼에 없는 경우 Mandelbrot 이미지를 생성 하는 작업을 만듭니다. 메시지 버퍼에는 초기 `Bitmap` 페인트 메시지와 같은 경우 및 클라이언트 창 앞에 다른 창이 이동되는 경우 개체가 포함되지 않습니다.

1. 응용 프로그램을 빌드하고 실행하여 응용 프로그램이 성공적으로 업데이트되었는지 확인합니다.

이제 그리기 작업이 백그라운드에서 수행되므로 UI의 응답성이 향상됩니다.

【[맨 위](#top)】

## <a name="improving-drawing-performance"></a><a name="performance"></a>드로잉 성능 향상

각 픽셀의 계산은 다른 모든 계산과 독립적이기 때문에 Mandelbrot 프랙탈의 생성은 병렬화에 적합합니다. 그리기 프로시저를 병렬화하려면 `for` `CChildView::DrawMandelbrot` 메서드의 외부 루프를 다음과 같이 [:parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘에 대한 호출로 변환합니다.

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

각 비트맵 요소의 계산은 독립적이므로 비트맵 메모리에 액세스하는 그리기 작업을 동기화할 필요가 없습니다. 이렇게 하면 사용 가능한 프로세서 수가 증가함에 따라 성능이 확장됩니다.

【[맨 위](#top)】

## <a name="adding-support-for-cancellation"></a><a name="cancellation"></a>취소 지원 추가

이 섹션에서는 창 크기 조정을 처리하는 방법과 창이 소멸될 때 활성 그리기 작업을 취소하는 방법에 대해 설명합니다.

[PPL의](cancellation-in-the-ppl.md) 문서 취소는 런타임에서 취소가 어떻게 작동하는지 설명합니다. 취소는 협조적입니다. 따라서 즉시 발생하지 않습니다. 취소된 작업을 중지하려면 런타임은 작업에서 런타임으로 후속 호출 중에 내부 예외를 throw합니다. 이전 섹션에서는 알고리즘을 `parallel_for` 사용하여 도면 작업의 성능을 향상시키는 방법을 보여 주며, 이 섹션에서는 이러한 방법을 보여 주시고 있습니다. 호출을 `parallel_for` 통해 런타임이 작업을 중지할 수 있으므로 취소가 작동하도록 합니다.

### <a name="cancelling-active-tasks"></a>활성 작업 취소

Mandelbrot 응용 `Bitmap` 프로그램은 차원이 클라이언트 창의 크기와 일치하는 개체를 만듭니다. 클라이언트 창의 크기를 조정할 때마다 응용 프로그램은 새 창 크기에 대한 이미지를 생성하는 추가 백그라운드 작업을 만듭니다. 응용 프로그램에는 이러한 중간 이미지가 필요하지 않습니다. 최종 창 크기에 대한 이미지만 필요합니다. 응용 프로그램이 이 추가 작업을 수행하지 못하도록 하려면 `WM_SIZE` 및 `WM_SIZING` 메시지에 대한 메시지 처리기에서 활성 그리기 작업을 취소한 다음 창 크기를 조정한 후 그리기 작업을 다시 예약할 수 있습니다.

창 의 크기를 조정하는 동안 활성 그리기 작업을 취소하려면 응용 프로그램은 및 `WM_SIZING` `WM_SIZE` 메시지에 대한 처리기에서 [동시성 ::task_group::cancel](reference/task-group-class.md#cancel) 메서드를 호출합니다. 메시지의 `WM_SIZE` 처리기는 모든 활성 작업이 완료될 때까지 기다렸다가 업데이트된 창 크기에 대한 그리기 작업을 다시 예약하는 [동시성::task_group:wait](reference/task-group-class.md#wait) 메서드를 호출합니다.

클라이언트 창이 소멸되면 활성 그리기 작업을 취소하는 것이 좋습니다. 활성 그리기 작업을 취소하면 클라이언트 창이 소멸된 후 작업자 스레드가 UI 스레드에 메시지를 게시하지 않도록 합니다. 응용 프로그램은 메시지에 대한 처리기의 활성 `WM_DESTROY` 그리기 작업을 취소합니다.

### <a name="responding-to-cancellation"></a>취소에 대한 응답

그리기 `CChildView::DrawMandelbrot` 작업을 수행하는 메서드는 취소에 응답해야 합니다. 런타임은 예외 처리를 사용하여 작업을 `CChildView::DrawMandelbrot` 취소하기 때문에 메서드는 예외 안전 메커니즘을 사용하여 모든 리소스가 올바르게 정리되도록 해야 합니다. 이 예제에서는 *리소스 수집 초기화(RAII)* 패턴을 사용하여 작업이 취소될 때 비트맵 비트의 잠금이 해제되도록 합니다.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>만델브로트 응용 프로그램에서 취소에 대한 지원을 추가하려면

1. ChildView.h에서 `protected` `CChildView` 클래스의 섹션에서 `OnSize`에 `OnSizing` `OnDestroy` 대한 선언을 추가합니다.

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. ChildView.cpp에서 메시지 맵을 수정하여 `WM_SIZE`에 `WM_SIZING`대한 처리기를 포함합니다. `WM_DESTROY`

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. `CChildView::OnSizing` 메서드를 구현합니다. 이 메서드는 기존 그리기 작업을 취소합니다.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. `CChildView::OnSize` 메서드를 구현합니다. 이 메서드는 기존 그리기 작업을 취소 하 고 업데이트 된 클라이언트 창 크기에 대 한 새 그리기 작업을 만듭니다.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. `CChildView::OnDestroy` 메서드를 구현합니다. 이 메서드는 기존 그리기 작업을 취소합니다.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. ChildView.cpp에서 RAII `scope_guard` 패턴을 구현하는 클래스를 정의합니다.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. 다음 코드를 호출 `CChildView::DrawMandelbrot` 한 후 메서드에 추가합니다. `Bitmap::LockBits`

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   이 코드는 개체를 `scope_guard` 만들어 취소를 처리합니다. 개체가 범위를 벗어나면 비트맵 비트의 잠금이 해제됩니다.

1. 비트맵 비트가 `CChildView::DrawMandelbrot` 잠금 해제된 후 `scope_guard` 개체를 해제하도록 메서드의 끝을 수정하지만 메시지가 UI 스레드로 전송되기 전에. 이렇게 하면 비트맵 비트의 잠금을 해제하기 전에 UI 스레드가 업데이트되지 않습니다.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

1. 응용 프로그램을 빌드하고 실행하여 응용 프로그램이 성공적으로 업데이트되었는지 확인합니다.

창 크기를 조정하면 최종 창 크기에 대해서만 그리기 작업이 수행됩니다. 창이 소멸되면 활성 그리기 작업도 취소됩니다.

【[맨 위](#top)】

## <a name="see-also"></a>참고 항목

[동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 기능](../../parallel/concrt/message-passing-functions.md)<br/>
[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL에서의 취소](cancellation-in-the-ppl.md)<br/>
[MFC 데스크톱 애플리케이션](../../mfc/mfc-desktop-applications.md)
