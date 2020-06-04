---
title: '연습: 매트릭스 곱'
ms.date: 04/23/2019
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
ms.openlocfilehash: f30f8dc235bf0e76c342bea26a35bcbb36cfa237
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366806"
---
# <a name="walkthrough-matrix-multiplication"></a>연습: 매트릭스 곱

이 단계별 연습에서는 C++ AMP를 사용하여 행렬 곱셈 실행을 가속화하는 방법을 보여 줍니다. 두 개의 알고리즘이 제공되며 하나는 바둑판식 배열없이, 하나는 바둑판식 배열이 있습니다.

## <a name="prerequisites"></a>사전 요구 사항

시작하기 전에 다음을 수행합니다.

- [읽기 C ++ AMP 개요](../../parallel/amp/cpp-amp-overview.md).

- [타일을 사용하여](../../parallel/amp/using-tiles.md)읽기 .

- 적어도 Windows 7 또는 Windows Server 2008 R2를 실행하고 있는지 확인합니다.

### <a name="to-create-the-project"></a>프로젝트를 만들려면

새 프로젝트를 만드는 방법은 설치한 Visual Studio 버전에 따라 다릅니다. 선호하는 버전의 Visual Studio에 대한 설명서를 보려면 **버전** 선택기 컨트롤을 사용합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker range="vs-2019"

### <a name="to-create-the-project-in-visual-studio-2019"></a>비주얼 스튜디오 2019에서 프로젝트를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트 만들기** 대화 상자를 엽니다.

1. 대화 상자 맨 위에서 **언어**를 **C++** 로 설정하고 **플랫폼**을 **Windows**로 설정하고 **프로젝트 형식**을 **콘솔**로 설정합니다.

1. 필터링된 프로젝트 유형 목록에서 **빈 프로젝트를** 선택한 다음 **다음을**선택합니다. 다음 페이지에서 이름 **상자에** *MatrixMultiply를* 입력하여 프로젝트 이름을 지정하고 원하는 경우 프로젝트 위치를 지정합니다.

   ![새 콘솔 앱](../../build/media/mathclient-project-name-2019.png "새 콘솔 앱")

1. **만들기** 단추를 선택하여 클라이언트 프로젝트를 만듭니다.

1. **솔루션 탐색기에서** **소스 파일의**바로 가기 메뉴를 연 다음 **새 항목** **추가를** > 선택합니다.

1. 새 **항목 추가** 대화 상자에서 **C++ 파일(.cpp)을**선택하고 **이름** 상자에 *MatrixMultiply.cpp를* 입력한 다음 **추가** 단추를 선택합니다.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-project-in-visual-studio-2017-or-2015"></a>Visual Studio 2017 또는 2015에서 프로젝트를 만들려면

1. Visual Studio의 메뉴 모음에서 **새** > **프로젝트** **파일** > 선택합니다.

1. 템플릿 창에 **설치된** 아래에서 **Visual C++를**선택합니다.

1. **빈 프로젝트를**선택하고 이름 **상자에** *매트릭스를 곱하면* 입력한 다음 **확인** 단추를 선택합니다.

1. **다음** 단추를 선택합니다.

1. **솔루션 탐색기에서** **소스 파일의**바로 가기 메뉴를 연 다음 **새 항목** **추가를** > 선택합니다.

1. 새 **항목 추가** 대화 상자에서 **C++ 파일(.cpp)을**선택하고 **이름** 상자에 *MatrixMultiply.cpp를* 입력한 다음 **추가** 단추를 선택합니다.

::: moniker-end

## <a name="multiplication-without-tiling"></a>타일링없이 곱셈

이 섹션에서는 다음과 같이 정의된 두 행렬 A와 B의 곱셈을 고려합니다.

![3&#45;바이&#45;2 행렬 A](../../parallel/amp/media/campmatrixanontiled.png "3&#45;바이&#45;2 행렬 A")

![2&#45;바이&#45;3 행렬 B](../../parallel/amp/media/campmatrixbnontiled.png "2&#45;바이&#45;3 행렬 B")

A는 3x2 행렬이고 B는 2x3 행렬입니다. A에 B를 곱한 곱은 다음 3x3 행렬입니다. 제품은 A의 행에 B 요소의 열에 요소에 곱하여 계산됩니다.

![3&#45;&#45;3 제품 매트릭스](../../parallel/amp/media/campmatrixproductnontiled.png "3&#45;&#45;3 제품 매트릭스")

### <a name="to-multiply-without-using-c-amp"></a>C++ AMP를 사용하지 않고 곱하기 위해

1. MatrixMultiPly.cpp를 열고 다음 코드를 사용하여 기존 코드를 대체합니다.

   ```cpp
   #include <iostream>

   void MultiplyWithOutAMP() {
       int aMatrix[3][2] = {{1, 4}, {2, 5}, {3, 6}};
       int bMatrix[2][3] = {{7, 8, 9}, {10, 11, 12}};
       int product[3][3] = {{0, 0, 0}, {0, 0, 0}, {0, 0, 0}};

       for (int row = 0; row < 3; row++) {
           for (int col = 0; col < 3; col++) {
               // Multiply the row of A by the column of B to get the row, column of product.
               for (int inner = 0; inner < 2; inner++) {
                   product[row][col] += aMatrix[row][inner] * bMatrix[inner][col];
               }
               std::cout << product[row][col] << "  ";
           }
           std::cout << "\n";
       }
   }

   int main() {
       MultiplyWithOutAMP();
       getchar();
   }
   ```

   알고리즘은 행렬 곱셈의 정의를 간단하게 구현합니다. 계산 시간을 줄이기 위해 병렬 또는 스레드 알고리즘을 사용하지 않습니다.

1. 메뉴 모음에서 모두 저장 **을** > **선택합니다.**

1. **F5** 키보드 단축기를 선택하여 디버깅을 시작하고 출력이 올바른지 확인합니다.

1. 응용 프로그램을 종료하려면 **Enter를** 선택합니다.

### <a name="to-multiply-by-using-c-amp"></a>C++ AMP를 사용하여 곱하기

1. MatrixMultiMultiply.cpp에서 메서드 앞에 다음 `main` 코드를 추가합니다.

   ```cpp
   void MultiplyWithAMP() {
   int aMatrix[] = { 1, 4, 2, 5, 3, 6 };
   int bMatrix[] = { 7, 8, 9, 10, 11, 12 };
   int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0 };

   array_view<int, 2> a(3, 2, aMatrix);

   array_view<int, 2> b(2, 3, bMatrix);

   array_view<int, 2> product(3, 3, productMatrix);

   parallel_for_each(product.extent,
      [=] (index<2> idx) restrict(amp) {
          int row = idx[0];
          int col = idx[1];
          for (int inner = 0; inner <2; inner++) {
              product[idx] += a(row, inner)* b(inner, col);
          }
      });

   product.synchronize();

   for (int row = 0; row <3; row++) {
      for (int col = 0; col <3; col++) {
          //std::cout << productMatrix[row*3 + col] << "  ";
          std::cout << product(row, col) << "  ";
      }
      std::cout << "\n";
     }
   }
   ```

   AMP 코드는 AMP가 아닌 코드와 유사합니다. 에서 각 `parallel_for_each` 요소에 `product.extent`대해 하나의 스레드를 시작하고 `for` 행 및 열에 대한 루프를 대체하는 호출입니다. 행 과 열의 셀 값은 에서 `idx`사용할 수 있습니다. 연산자 및 인덱스 `array_view` 변수 또는 `()` 연산자 및 행 및 열 변수를 사용하여 개체의 요소에 액세스할 수 있습니다. `[]` 이 예제에서는 두 메서드를 모두 보여 줍니다. 메서드는 `array_view::synchronize` `product` 변수의 값을 다시 `productMatrix` 변수로 복사합니다.

1. 행렬의 `include` 상단에 `using` 다음과 같은 문을 추가Multiply.cpp.

   ```cpp
   #include <amp.h>
   using namespace concurrency;
   ```

1. 메서드를 `main` 호출할 `MultiplyWithAMP` 메서드를 수정합니다.

   ```cpp
   int main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       getchar();
   }
   ```

1. **Ctrl**+**F5** 키보드 단축을 눌러 디버깅을 시작하고 출력이 올바른지 확인합니다.

1. **스페이스바를** 눌러 응용 프로그램을 종료합니다.

## <a name="multiplication-with-tiling"></a>타일링이 있는 곱셈

타일링은 데이터를 타일이라고 하는 동일한 크기의 하위 집합으로 분할하는 기술입니다. 바둑판기 바둑판에서 사용할 때 세 가지가 바뀝니다.

- 변수를 `tile_static` 만들 수 있습니다. `tile_static` 공간의 데이터에 대한 액세스는 전역 공간의 데이터에 액세스하는 것보다 몇 배 더 빠를 수 있습니다. 각 타일에 `tile_static` 대해 변수 인스턴스가 만들어지고 타일의 모든 스레드가 변수에 액세스할 수 있습니다. 타일링의 주요 이점은 액세스로 `tile_static` 인한 성능 향상입니다.

- [tile_barrier::wait](reference/tile-barrier-class.md#wait) 메서드를 호출하여 지정된 코드 줄에서 한 타일의 모든 스레드를 중지할 수 있습니다. 스레드가 실행되는 순서를 보장할 수 없으며 한 타일의 모든 스레드가 실행을 계속하기 `tile_barrier::wait` 전에 호출에서 중지됩니다.

- 전체 `array_view` 개체를 기준으로 스레드의 인덱스와 타일을 기준으로 하는 인덱스에 액세스할 수 있습니다. 로컬 인덱스를 사용하면 코드를 더 쉽게 읽고 디버깅할 수 있습니다.

행렬 곱셈의 타일링을 활용하려면 알고리즘이 행렬을 타일로 분할한 다음 타일 `tile_static` 데이터를 변수로 복사하여 더 빠른 액세스를 수행해야 합니다. 이 예제에서는 행렬이 동일한 크기의 하위 행렬로 분할됩니다. 이 제품은 서브 매트릭스를 곱하여 발견됩니다. 이 예제에서 두 행렬과 해당 제품은 다음과 같습니다.

![4&#45;바이&#45;4 행렬 A](../../parallel/amp/media/campmatrixatiled.png "4&#45;바이&#45;4 행렬 A")

![4&#45;바이&#45;4 행렬 B](../../parallel/amp/media/campmatrixbtiled.png "4&#45;바이&#45;4 행렬 B")

![4&#45;4 제품 매트릭스에 의한&#45;](../../parallel/amp/media/campmatrixproducttiled.png "4&#45;4 제품 매트릭스에 의한&#45;")

행렬은 4개의 2x2 행렬로 분할되며 다음과 같이 정의됩니다.

![4&#45;&#45;4 행렬 A는&#45;2 서브&#45;행렬에 의해 2&#45;분할](../../parallel/amp/media/campmatrixapartitioned.png "4&#45;&#45;4 행렬 A는&#45;2 서브&#45;행렬에 의해 2&#45;분할")

![4&#45;&#45;4 행렬 B로 분할 된&#45;2 서브&#45;행렬에 의해 2&#45;분할](../../parallel/amp/media/campmatrixbpartitioned.png "4&#45;&#45;4 행렬 B로 분할 된&#45;2 서브&#45;행렬에 의해 2&#45;분할")

이제 A와 B의 곱을 다음과 같이 작성하고 계산할 수 있습니다.

![4&#45;&#45;4 행렬 A B로 분할하여 2 개의&#45;&#45;2 개의 서브&#45;행렬로 분할했습니다.](../../parallel/amp/media/campmatrixproductpartitioned.png "4&#45;&#45;4 행렬 A B로 분할하여 2 개의&#45;&#45;2 개의 서브&#45;행렬로 분할했습니다.")

행렬은 `a` 2x2 `h` 행렬이기 때문에 모든 제품과 합계는 2x2 행렬입니다. 또한 A와 B의 곱이 예상대로 4x4 행렬이라는 것을 따릅니다. 알고리즘을 빠르게 확인하려면 제품의 첫 번째 열인 첫 번째 행의 요소 값을 계산합니다. 이 예제에서는 `ae + bg`의 첫 번째 행과 첫 번째 열의 요소 값이 됩니다. 각 용어의 첫 번째 열, `ae` 첫 `bg` 번째 행만 계산하면 됩니다. 에 대한 `ae` `(1 * 1) + (2 * 5) = 11`값은 입니다. `bg`의 값이 `(3 * 1) + (4 * 5) = 23`인 경우 최종 값은 `11 + 23 = 34`올바른 값입니다.

이 알고리즘을 구현하려면 다음 코드를

- 호출의 `tiled_extent` 개체 대신 `extent` 개체를 `parallel_for_each` 사용합니다.

- 호출의 `tiled_index` 개체 대신 `index` 개체를 `parallel_for_each` 사용합니다.

- 서브매트릭스를 보유하는 변수를 만듭니다. `tile_static`

- 이 `tile_barrier::wait` 메서드를 사용하여 서브매트릭스 의 제품 계산을 위해 스레드를 중지합니다.

### <a name="to-multiply-by-using-amp-and-tiling"></a>AMP 및 타일링을 사용하여 곱하기

1. MatrixMultiMultiply.cpp에서 메서드 앞에 다음 `main` 코드를 추가합니다.

   ```cpp
   void MultiplyWithTiling() {
       // The tile size is 2.
       static const int TS = 2;

       // The raw data.
       int aMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };
       int bMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };
       int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 };

       // Create the array_view objects.
       array_view<int, 2> a(4, 4, aMatrix);
       array_view<int, 2> b(4, 4, bMatrix);
       array_view<int, 2> product(4, 4, productMatrix);

       // Call parallel_for_each by using 2x2 tiles.
       parallel_for_each(product.extent.tile<TS, TS>(),
           [=] (tiled_index<TS, TS> t_idx) restrict(amp)
           {
               // Get the location of the thread relative to the tile (row, col)
               // and the entire array_view (rowGlobal, colGlobal).
               int row = t_idx.local[0];
               int col = t_idx.local[1];
               int rowGlobal = t_idx.global[0];
               int colGlobal = t_idx.global[1];
               int sum = 0;

               // Given a 4x4 matrix and a 2x2 tile size, this loop executes twice for each thread.
               // For the first tile and the first loop, it copies a into locA and e into locB.
               // For the first tile and the second loop, it copies b into locA and g into locB.
               for (int i = 0; i < 4; i += TS) {
                   tile_static int locA[TS][TS];
                   tile_static int locB[TS][TS];
                   locA[row][col] = a(rowGlobal, col + i);
                   locB[row][col] = b(row + i, colGlobal);
                   // The threads in the tile all wait here until locA and locB are filled.
                   t_idx.barrier.wait();

                   // Return the product for the thread. The sum is retained across
                   // both iterations of the loop, in effect adding the two products
                   // together, for example, a*e.
                   for (int k = 0; k < TS; k++) {
                       sum += locA[row][k] * locB[k][col];
                   }

                   // All threads must wait until the sums are calculated. If any threads
                   // moved ahead, the values in locA and locB would change.
                   t_idx.barrier.wait();
                   // Now go on to the next iteration of the loop.
               }

               // After both iterations of the loop, copy the sum to the product variable by using the global location.
               product[t_idx.global] = sum;
           });

       // Copy the contents of product back to the productMatrix variable.
       product.synchronize();

       for (int row = 0; row <4; row++) {
           for (int col = 0; col <4; col++) {
               // The results are available from both the product and productMatrix variables.
               //std::cout << productMatrix[row*3 + col] << "  ";
               std::cout << product(row, col) << "  ";
           }
           std::cout << "\n";
       }
   }
   ```

   이 예제는 바둑판기 없이 예제와 크게 다릅니다. 코드는 다음과 같은 개념적 단계를 사용합니다.
   1. 타일[0,0]의 `a` 요소를 에 `locA`복사합니다. 타일[0,0]의 `b` 요소를 에 `locB`복사합니다. `product` 바둑판식으로 배열되어 `a` `b`있지 않습니다. 따라서 전역 인덱스를 사용하여 에 `a, b`액세스하고 `product`. `tile_barrier::wait` 호출은 필수적입니다. 둘 다 `locA` 채워지때까지 타일의 모든 `locB` 스레드를 중지합니다.

   1. `locA` 곱하고 `locB` 결과를 넣습니다. `product`

   1. 타일의 [0,1]의 `a` 요소를 `locA`에 복사합니다. 타일 [1,0]의 `b` 요소를 에 `locB`복사합니다.

   1. `locA` 곱하고 `locB` 이미 있는 결과에 추가합니다. `product`

   1. 타일[0,0]의 곱셈이 완료되었습니다.

   1. 다른 네 타일에 대해 반복합니다. 타일에 대한 인덱싱은 없으며 스레드는 임의의 순서로 실행할 수 있습니다. 각 스레드가 실행될 `tile_static` 때 각 타일에 대해 변수가 `tile_barrier::wait` 적절하게 생성되고 프로그램 흐름을 제어하는 호출이 생성됩니다.

   1. 알고리즘을 자세히 살펴보면 각 하위 행렬이 `tile_static` 메모리에 두 번 로드됩니다. 이러한 데이터 전송에는 시간이 소요됩니다. 그러나 데이터가 메모리에 `tile_static` 있으면 데이터에 대한 액세스가 훨씬 빠릅니다. 제품을 계산하려면 하위 매트의 값에 반복적으로 액세스해야 하므로 전반적인 성능 이점이 있습니다. 각 알고리즘에 대해 최적의 알고리즘과 타일 크기를 찾으려면 실험이 필요합니다.

   AMP 및 비타일 예제에서 A와 B의 각 요소는 전역 메모리에서 4번 액세스하여 제품을 계산합니다. 타일 예제에서 각 요소는 전역 메모리에서 두 번, `tile_static` 메모리에서 네 번 액세스됩니다. 이는 성능이 크게 향상되지 않습니다. 그러나 A와 B가 1024x1024 행렬이고 타일 크기가 16이면 상당한 성능 향상이 있을 것입니다. 이 경우 각 요소는 16번만 `tile_static` 메모리에 복사되고 메모리에서 `tile_static` 1024번 액세스됩니다.

1. 그림과 같이 메서드를 `MultiplyWithTiling` 호출하도록 기본 메서드를 수정합니다.

   ```cpp
   int main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       MultiplyWithTiling();
       getchar();
   }
   ```

1. **Ctrl**+**F5** 키보드 단축을 눌러 디버깅을 시작하고 출력이 올바른지 확인합니다.

1. **스페이스** 바를 눌러 응용 프로그램을 종료합니다.

## <a name="see-also"></a>참고 항목

[C++ AMP(C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[연습: C++ AMP 애플리케이션 디버깅](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)
