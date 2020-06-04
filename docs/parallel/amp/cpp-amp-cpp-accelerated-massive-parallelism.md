---
title: C++ AMP(C++ Accelerated Massive Parallelism)
ms.date: 11/04/2016
helpviewer_keywords:
- C++ AMP (see C++ Accelerated Massive Parallelism)
- C++ Accelerated Massive Parallelism, getting started
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
ms.openlocfilehash: c9ef7ab816ec0d17b9dc0b569a6f3a43af83cc68
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167695"
---
# <a name="c-amp-c-accelerated-massive-parallelism"></a>C++ AMP(C++ Accelerated Massive Parallelism)

C++AMP(C++ Accelerated Massive Parallelism)는 개별 그래픽 카드에서 일반적으로 그래픽 처리 장치(GPU)로 제공되는 데이터 병렬 하드웨어를 활용하여 C++ 코드 실행을 가속화합니다. C++ AMP 프로그래밍 모델에서는 다차원 배열, 인덱싱, 메모리 전송 및 바둑판식 배열을 지원합니다. 또한 수학 함수 라이브러리가 포함됩니다. C++ AMP 언어 확장을 사용하여 데이터가 CPU에서 GPU로 이동하는 방법을 제어할 수 있습니다.

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[C++ AMP 개요](../../parallel/amp/cpp-amp-overview.md)|C++ AMP와 수학 라이브러리의 주요 기능을 설명합니다.|
|[람다, 함수 개체 및 제한 함수 사용](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|[Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) 메서드에 대 한 호출에서 람다 식, 함수 개체 및 제한 된 함수를 사용 하는 방법을 설명 합니다.|
|[타일 사용](../../parallel/amp/using-tiles.md)|타일을 사용하여 C++ AMP 코드를 가속화하는 방법에 대하여 설명합니다.|
|[accelerator 및 accelerator_view 개체 사용](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|가속기를 사용하여 GPU에서 코드 실행의 사용자 지정 방법을 설명합니다.|
|[UWP 앱에서 C++ AMP 사용](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Windows 런타임 유형을 사용하는 UWP(유니버설 Windows 플랫폼) 앱에서 C++ AMP를 사용하는 방법을 설명합니다.|
|[그래픽(C++ AMP)](../../parallel/amp/graphics-cpp-amp.md)|C++ AMP 그래픽 라이브러리를 사용하는 방법을 설명합니다.|
|[연습: 매트릭스 곱](../../parallel/amp/walkthrough-matrix-multiplication.md)|매트릭스 곱셈 C++ AMP 코드 및 타일링을 사용하여 행렬 곱셈을 보여줍니다.|
|[연습: C++ AMP 애플리케이션 디버깅](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|병렬 영역 감소를 사용하여 큰 정수 배열을 요약하는 응용 프로그램을 만들고 디버깅하는 방법을 설명합니다.|

## <a name="reference"></a>참조

[참조(C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)<br/>
[tile_static 키워드](../../cpp/tile-static-keyword.md)<br/>
[restrict(C++ AMP)](../../cpp/restrict-cpp-amp.md)

## <a name="other-resources"></a>관련 자료

[네이티브 코드 블로그의 병렬 프로그래밍](https://go.microsoft.com/fwlink/p/?linkid=238472)<br/>
[C++다운로드할 AMP 샘플 프로젝트](https://go.microsoft.com/fwlink/p/?linkid=248508)<br/>
[동시성 C++ 시각화 도우미를 사용 하 여 AMP 코드 분석](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/03/09/analyzing-c-amp-code-with-the-concurrency-visualizer/)


