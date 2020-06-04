---
title: lock 클래스
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::lock::lock
- msclr::lock::is_locked
- msclr::lock.is_locked
- msclr::lock::acquire
- msclr::lock::try_acquire
- msclr::lock::release
- msclr::lock::operator==
- msclr::lock::operator!=
helpviewer_keywords:
- msclr::lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: ea09dd3d4a2eaf4cf7708d09509cfecfa4a6c6d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373070"
---
# <a name="lock-class"></a>lock 클래스

이 클래스는 여러 스레드에서 개체에 대한 액세스를 동기화하기 위해 잠금을 자동으로 가져옵니다.  생성하면 잠금을 획득하고 파괴하면 잠금이 해제됩니다.

## <a name="syntax"></a>구문

```cpp
ref class lock;
```

## <a name="remarks"></a>설명

`lock`CLR 개체에만 사용할 수 있으며 CLR 코드에서만 사용할 수 있습니다.

내부적으로 lock 클래스는 <xref:System.Threading.Monitor> 액세스를 동기화하는 데 사용합니다. 자세한 내용은 참조된 문서를 참조하십시오.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|---------|-----------|
|[lock::lock](#lock)|선택적으로 `lock` 지정된 시간 동안 영원히 잠금을 획득하기 위해 기다리거나 전혀 없는 객체를 생성합니다.|
|[잠금::~잠금](#tilde-lock)|개체를 소멸시입니다. `lock`|

### <a name="public-methods"></a>public 메서드

|속성|Description|
|---------|-----------|
|[lock::acquire](#acquire)|선택적으로 지정된 시간 동안 영원히 잠금을 획득하기 위해 기다리거나 전혀 없는 개체에 대한 잠금을 획득합니다.|
|[lock::is_locked](#is-locked)|잠금이 유지되고 있는지 여부를 나타냅니다.|
|[lock::release](#release)|잠금을 해제합니다.|
|[lock::try_acquire](#try-acquire)|개체에 대한 잠금을 획득하여 지정된 시간 동안 대기하고 `bool` 예외를 throw하는 대신 획득 성공 사례를 보고하는 반환을 반환합니다.|

### <a name="public-operators"></a>공공 사업자

|속성|Description|
|---------|-----------|
|[잠금::연산자&nbsp;불](#operator-bool)|조건식에서 `lock` 사용하기 위한 연산자입니다.|
|[잠금::연산자==](#operator-equality)|같음 연산자.|
|[lock::operator!=](#operator-inequality)|부등분 연산자.|

## <a name="requirements"></a>요구 사항

**헤더 파일** \<msclr\lock.h>

**네임스페이스** msclr

## <a name="locklock"></a><a name="lock"></a>잠금::잠금

선택적으로 `lock` 지정된 시간 동안 영원히 잠금을 획득하기 위해 기다리거나 전혀 없는 객체를 생성합니다.

```cpp
template<class T> lock(
   T ^ _object
);
template<class T> lock(
   T ^ _object,
   int _timeout
);
template<class T> lock(
   T ^ _object,
   System::TimeSpan _timeout
);
template<class T> lock(
   T ^ _object,
   lock_later
);
```

### <a name="parameters"></a>매개 변수

*_object*<br/>
잠글 개체입니다.

*_timeout*<br/>
시간 초과하는 값은 밀리초 <xref:System.TimeSpan>단위로 또는 .

### <a name="exceptions"></a>예외

<xref:System.ApplicationException> 시간 시간 전에 잠금 수집이 발생하지 않으면 throw합니다.

### <a name="remarks"></a>설명

생성자의 처음 세 가지 형태는 지정된 `_object` 시간 시간 기간 내에 <xref:System.Threading.Timeout.Infinite> 잠금을 획득하려고 시도합니다(또는 지정되지 않은 경우).

생성자의 네 번째 형식은 `_object`에 대한 잠금을 획득하지 않습니다. `lock_later`은 [lock_when 열거형의](../dotnet/lock-when-enum.md)구성원입니다. 이 경우 잠금을 획득하려면 [잠금::획득](../dotnet/lock-acquire.md) 또는 [잠금:try_acquire](../dotnet/lock-try-acquire.md) 사용합니다.

소멸자가 호출될 때 잠금이 자동으로 해제됩니다.

`_object`할 <xref:System.Threading.ReaderWriterLock>수 없습니다.  이 경우 컴파일러 오류가 발생합니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드에서 클래스의 단일 인스턴스를 사용합니다. 클래스는 자체 잠금을 사용하여 내부 데이터에 대한 액세스가 각 스레드에 대해 일관되게 있는지 확인합니다. 주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대한 잠금을 사용하여 작업자 스레드가 여전히 존재하는지 주기적으로 확인합니다. 그런 다음 모든 작업자 스레드가 작업을 완료할 때까지 주 응용 프로그램이 종료될 때까지 기다립니다.

```cpp
// msl_lock_lock.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="locklock"></a><a name="tilde-lock"></a>잠금::~잠금

개체를 소멸시입니다. `lock`

```cpp
~lock();
```

### <a name="remarks"></a>설명

소멸자는 [lock::release를](../dotnet/lock-release.md)호출합니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드에서 클래스의 단일 인스턴스를 사용합니다.  클래스는 자체 잠금을 사용하여 내부 데이터에 대한 액세스가 각 스레드에 대해 일관되게 있는지 확인합니다.  주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대한 잠금을 사용하여 작업자 스레드가 여전히 존재하는지 주기적으로 확인합니다. 그런 다음 모든 작업자 스레드가 작업을 완료할 때까지 주 응용 프로그램이 종료될 때까지 기다립니다.

```cpp
// msl_lock_dtor.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockacquire"></a><a name="acquire"></a>잠금::획득

선택적으로 지정된 시간 동안 영원히 잠금을 획득하기 위해 기다리거나 전혀 없는 개체에 대한 잠금을 획득합니다.

```cpp
void acquire();
void acquire(
   int _timeout
);
void acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>매개 변수

*_timeout*<br/>
시간 시간(시간)(밀리초)로 또는 <xref:System.TimeSpan>.

### <a name="exceptions"></a>예외

<xref:System.ApplicationException> 시간 시간 전에 잠금 수집이 발생하지 않으면 throw합니다.

### <a name="remarks"></a>설명

시간 지정 값이 제공되지 않으면 기본 시간 지정은 <xref:System.Threading.Timeout.Infinite>입니다.

잠금이 이미 수집된 경우 이 함수는 아무 것도 수행하지 않습니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드에서 클래스의 단일 인스턴스를 사용합니다.  클래스는 자체 잠금을 사용하여 내부 데이터에 대한 액세스가 각 스레드에 대해 일관되게 있는지 확인합니다. 주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대한 잠금을 사용하여 작업자 스레드가 여전히 존재하는지 주기적으로 확인합니다. 그런 다음 모든 작업자 스레드가 작업을 완료할 때까지 주 응용 프로그램이 종료될 때까지 기다립니다.

```cpp
// msl_lock_acquire.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockis_locked"></a><a name="is-locked"></a>잠금:is_locked

잠금이 유지되고 있는지 여부를 나타냅니다.

```cpp
bool is_locked();
```

### <a name="return-value"></a>반환 값

`true`잠금이 유지되는 `false` 경우, 그렇지 않으면.

### <a name="example"></a>예제

이 예제에서는 여러 스레드에서 클래스의 단일 인스턴스를 사용합니다.  클래스는 자체 잠금을 사용하여 내부 데이터에 대한 액세스가 각 스레드에 대해 일관되게 있는지 확인합니다.  주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대한 잠금을 사용하여 주기적으로 작업자 스레드가 여전히 존재하는지 확인하고 모든 작업자 스레드가 작업을 완료할 때까지 종료될 때까지 기다립니다.

```cpp
// msl_lock_is_locked.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l.is_locked()) { // check if we got the lock
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockoperator-bool"></a><a name="operator-bool"></a>잠금::연산자 불

조건식에서 `lock` 사용하기 위한 연산자입니다.

```cpp
operator bool();
```

### <a name="return-value"></a>반환 값

`true`잠금이 유지되는 `false` 경우, 그렇지 않으면.

### <a name="remarks"></a>설명

이 연산자는 `_detail_class::_safe_bool` 실제로 정수 `bool` 유형으로 변환할 수 없기 때문에 보다 안전한 것으로 변환합니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드에서 클래스의 단일 인스턴스를 사용합니다.  클래스는 자체 잠금을 사용하여 내부 데이터에 대한 액세스가 각 스레드에 대해 일관되게 있는지 확인합니다. 주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대한 잠금을 사용하여 작업자 스레드가 여전히 존재하는지 주기적으로 확인합니다. 모든 작업자 스레드가 작업을 완료할 때까지 주 응용 프로그램이 종료될 때까지 기다립니다.

```cpp
// msl_lock_op_bool.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l) { // use bool operator to check for lock
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockrelease"></a><a name="release"></a>잠금::릴리스

잠금을 해제합니다.

```cpp
void release();
```

### <a name="remarks"></a>설명

잠금이 유지되지 않으면 `release` 아무 것도 수행하지 않습니다.

이 함수를 명시적으로 호출할 필요가 없습니다. 개체가 `lock` 범위를 벗어나면 소멸자가 호출합니다. `release`

### <a name="example"></a>예제

이 예제에서는 여러 스레드에서 클래스의 단일 인스턴스를 사용합니다. 클래스는 자체 잠금을 사용하여 내부 데이터에 대한 액세스가 각 스레드에 대해 일관되게 있는지 확인합니다. 주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대한 잠금을 사용하여 작업자 스레드가 여전히 존재하는지 주기적으로 확인합니다. 그런 다음 모든 작업자 스레드가 작업을 완료할 때까지 주 응용 프로그램이 종료될 때까지 기다립니다.

```cpp
// msl_lock_release.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="locktry_acquire"></a><a name="try-acquire"></a>잠금::try_acquire

개체에 대한 잠금을 획득하여 지정된 시간 동안 대기하고 `bool` 예외를 throw하는 대신 획득 성공 사례를 보고하는 반환을 반환합니다.

```cpp
bool try_acquire(
   int _timeout_ms
);
bool try_acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>매개 변수

*_timeout*<br/>
시간 시간(시간)(밀리초)로 또는 <xref:System.TimeSpan>.

### <a name="return-value"></a>반환 값

`true`잠금이 획득된 `false` 경우, 그렇지 않은 경우.

### <a name="remarks"></a>설명

잠금이 이미 수집된 경우 이 함수는 아무 것도 수행하지 않습니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드에서 클래스의 단일 인스턴스를 사용합니다. 클래스는 자체 잠금을 사용하여 내부 데이터에 대한 액세스가 각 스레드에 대해 일관되게 있는지 확인합니다. 주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대한 잠금을 사용하여 작업자 스레드가 여전히 존재하는지 주기적으로 확인합니다. 그런 다음 모든 작업자 스레드가 작업을 완료할 때까지 주 응용 프로그램이 종료될 때까지 기다립니다.

```cpp
// msl_lock_try_acquire.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockoperator"></a><a name="operator-equality"></a>잠금::연산자==

같음 연산자.

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
같은지 비교할 개체입니다.

### <a name="return-value"></a>반환 값

그렇지 `t` 않으면 잠금의 개체와 동일한 경우 반환합니다. `true` `false`

### <a name="example"></a>예제

```cpp
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="lockoperator"></a><a name="operator-inequality"></a>잠금::연산자!=

부등분 연산자.

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
부등/용적성 비교할 개체입니다.

### <a name="return-value"></a>반환 값

그렇지 `t` 않으면 잠금의 개체와 다른 경우 반환합니다. `true` `false`

### <a name="example"></a>예제

```cpp
// msl_lock_op_ineq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   Object^ o2 = gcnew Object;
   lock l1(o1);
   if (l1 != o2) {
      Console::WriteLine("Inequal!");
   }
}
```

```Output
Inequal!
```
