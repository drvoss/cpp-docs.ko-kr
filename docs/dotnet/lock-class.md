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
ms.openlocfilehash: b2ae1be31233e55aa34d6f3046d90fb2127348c0
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80080039"
---
# <a name="lock-class"></a>lock 클래스

이 클래스는 여러 스레드에서 개체에 대 한 액세스를 동기화 하기 위한 잠금을 자동화 합니다.  생성 된 경우 잠금을 획득 하 고 제거 되 면 잠금을 해제 합니다.

## <a name="syntax"></a>구문

```cpp
ref class lock;
```

## <a name="remarks"></a>주의

`lock`는 CLR 개체에만 사용할 수 있으며 CLR 코드 에서만 사용할 수 있습니다.

내부적으로 lock 클래스는 <xref:System.Threading.Monitor>을 사용 하 여 액세스를 동기화 합니다. 자세한 내용은 참조 된 문서를 참조 하세요.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|---------|-----------|
|[lock::lock](#lock)|지정 된 시간 동안 또는 지정 된 시간 동안 잠금 상태를 영구적으로 얻기 위해 대기 하는 `lock` 개체를 생성 합니다.|
|[lock::~lock](#tilde-lock)|`lock` 개체를 Destructs 합니다.|

### <a name="public-methods"></a>public 메서드

|이름|설명|
|---------|-----------|
|[lock::acquire](#acquire)|개체에 대 한 잠금을 획득 하 고, 선택적으로 잠금을 획득 하기 위해 대기 하는 경우 지정 된 시간 동안 또는 전혀 발생 하지 않도록 대기 합니다.|
|[lock::is_locked](#is-locked)|잠금을 보유 하 고 있는지 여부를 나타냅니다.|
|[lock::release](#release)|잠금을 해제 합니다.|
|[lock::try_acquire](#try-acquire)|지정 된 시간 동안 기다린 후 예외를 throw 하는 대신 획득의 성공을 보고 하는 `bool`을 반환 하는 개체에 대 한 잠금을 가져옵니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|---------|-----------|
|[lock:: operator&nbsp;bool](#operator-bool)|조건식에 `lock`을 사용 하기 위한 연산자입니다.|
|[lock::operator==](#operator-equality)|같음 연산자입니다.|
|[lock::operator!=](#operator-inequality)|같지 않음 연산자입니다.|

## <a name="requirements"></a>요구 사항

**헤더 파일** \<msclr\lock.h >

Msclr **네임 스페이스**

## <a name="locklock"></a><a name="lock"></a>lock:: lock

지정 된 시간 동안 또는 지정 된 시간 동안 잠금 상태를 영구적으로 얻기 위해 대기 하는 `lock` 개체를 생성 합니다.

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
시간 제한 값 (밀리초) 또는 <xref:System.TimeSpan>입니다.

### <a name="exceptions"></a>예외

제한 시간이 초과 되기 전에 잠금 획득이 발생 하지 않는 경우 <xref:System.ApplicationException>을 throw 합니다.

### <a name="remarks"></a>주의

생성자의 처음 세 형태는 지정 된 시간 제한 기간 (또는 지정 되지 않은 경우 <xref:System.Threading.Timeout.Infinite>) 내에서 `_object`에 대 한 잠금을 가져오려고 시도 합니다.

생성자의 네 번째 형태는 `_object`에 대 한 잠금을 획득 하지 않습니다. `lock_later`은 [lock_when 열거형](../dotnet/lock-when-enum.md)의 멤버입니다. Lock [:: 얻으려고](../dotnet/lock-acquire.md) 또는 [lock:: try_acquire](../dotnet/lock-try-acquire.md) 을 사용 하 여이 경우 잠금을 가져옵니다.

소멸자가 호출 되 면 잠금이 자동으로 해제 됩니다.

`_object`를 <xref:System.Threading.ReaderWriterLock>수 없습니다.  인 경우 컴파일러 오류가 발생 합니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다. 클래스는 자체에 대 한 잠금을 사용 하 여 내부 데이터에 대 한 액세스가 각 스레드에 대해 일치 하는지 확인 합니다. 주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대 한 잠금을 사용 하 여 작업자 스레드가 아직 있는지 여부를 주기적으로 확인 합니다. 그러면 주 응용 프로그램은 모든 작업자 스레드가 작업을 완료할 때까지 종료 될 때까지 기다립니다.

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

## <a name="locklock"></a><a name="tilde-lock"></a>lock:: ~ lock

`lock` 개체를 Destructs 합니다.

```cpp
~lock();
```

### <a name="remarks"></a>주의

소멸자는 [lock:: release](../dotnet/lock-release.md)를 호출 합니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다.  클래스는 자체에 대 한 잠금을 사용 하 여 내부 데이터에 대 한 액세스가 각 스레드에 대해 일치 하는지 확인 합니다.  주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대 한 잠금을 사용 하 여 작업자 스레드가 아직 있는지 여부를 주기적으로 확인 합니다. 그러면 주 응용 프로그램은 모든 작업자 스레드가 작업을 완료할 때까지 종료 될 때까지 기다립니다.

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

## <a name="lockacquire"></a><a name="acquire"></a>lock:: 획득

개체에 대 한 잠금을 획득 하 고, 선택적으로 잠금을 획득 하기 위해 대기 하는 경우 지정 된 시간 동안 또는 전혀 발생 하지 않도록 대기 합니다.

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
제한 시간 값 (밀리초) 또는 <xref:System.TimeSpan>입니다.

### <a name="exceptions"></a>예외

제한 시간이 초과 되기 전에 잠금 획득이 발생 하지 않는 경우 <xref:System.ApplicationException>을 throw 합니다.

### <a name="remarks"></a>주의

시간 제한 값을 제공 하지 않으면 기본 시간 제한이 <xref:System.Threading.Timeout.Infinite>됩니다.

잠금을 이미 가져온 경우이 함수는 아무 작업도 수행 하지 않습니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다.  클래스는 자체에 대 한 잠금을 사용 하 여 내부 데이터에 대 한 액세스가 각 스레드에 대해 일치 하는지 확인 합니다. 주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대 한 잠금을 사용 하 여 작업자 스레드가 아직 있는지 여부를 주기적으로 확인 합니다. 그러면 주 응용 프로그램은 모든 작업자 스레드가 작업을 완료할 때까지 종료 될 때까지 기다립니다.

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

## <a name="lockis_locked"></a><a name="is-locked"></a>lock:: is_locked

잠금을 보유 하 고 있는지 여부를 나타냅니다.

```cpp
bool is_locked();
```

### <a name="return-value"></a>반환 값

잠금이 유지 되는 경우 `true` `false` 그렇지 않으면입니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다.  클래스는 자체에 대 한 잠금을 사용 하 여 내부 데이터에 대 한 액세스가 각 스레드에 대해 일치 하는지 확인 합니다.  주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대 한 잠금을 사용 하 여 모든 작업자 스레드가 존재 하는지 정기적으로 확인 하 고 모든 작업자 스레드가 작업을 완료할 때까지 종료 될 때까지 기다립니다.

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

## <a name="lockoperator-bool"></a><a name="operator-bool"></a>lock:: operator bool

조건식에 `lock`을 사용 하기 위한 연산자입니다.

```cpp
operator bool();
```

### <a name="return-value"></a>반환 값

잠금이 유지 되는 경우 `true` `false` 그렇지 않으면입니다.

### <a name="remarks"></a>주의

이 연산자는 정수 계열 형식으로 변환할 수 없기 때문에 `bool` 보다 안전한 `_detail_class::_safe_bool`로 변환 됩니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다.  클래스는 자체에 대 한 잠금을 사용 하 여 내부 데이터에 대 한 액세스가 각 스레드에 대해 일치 하는지 확인 합니다. 주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대 한 잠금을 사용 하 여 작업자 스레드가 아직 있는지 여부를 주기적으로 확인 합니다. 주 응용 프로그램은 모든 작업자 스레드가 작업을 완료할 때까지 종료 될 때까지 기다립니다.

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

## <a name="lockrelease"></a><a name="release"></a>lock:: release

잠금을 해제 합니다.

```cpp
void release();
```

### <a name="remarks"></a>주의

잠금을 보유 하 고 있지 않으면 `release` 아무 작업도 수행 하지 않습니다.

이 함수는 명시적으로 호출할 필요가 없습니다. `lock` 개체가 범위를 벗어나면 소멸자는 `release`를 호출 합니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다. 클래스는 자체에 대 한 잠금을 사용 하 여 내부 데이터에 대 한 액세스가 각 스레드에 대해 일치 하는지 확인 합니다. 주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대 한 잠금을 사용 하 여 작업자 스레드가 아직 있는지 여부를 주기적으로 확인 합니다. 그러면 주 응용 프로그램은 모든 작업자 스레드가 작업을 완료할 때까지 종료 될 때까지 기다립니다.

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

## <a name="locktry_acquire"></a><a name="try-acquire"></a>lock:: try_acquire

지정 된 시간 동안 기다린 후 예외를 throw 하는 대신 획득의 성공을 보고 하는 `bool`을 반환 하는 개체에 대 한 잠금을 가져옵니다.

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
제한 시간 값 (밀리초) 또는 <xref:System.TimeSpan>입니다.

### <a name="return-value"></a>반환 값

잠금을 획득 한 경우 `true` `false` 그렇지 않으면입니다.

### <a name="remarks"></a>주의

잠금을 이미 가져온 경우이 함수는 아무 작업도 수행 하지 않습니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다. 클래스는 자체에 대 한 잠금을 사용 하 여 내부 데이터에 대 한 액세스가 각 스레드에 대해 일치 하는지 확인 합니다. 주 응용 프로그램 스레드는 클래스의 동일한 인스턴스에 대 한 잠금을 사용 하 여 작업자 스레드가 아직 있는지 여부를 주기적으로 확인 합니다. 그러면 주 응용 프로그램은 모든 작업자 스레드가 작업을 완료할 때까지 종료 될 때까지 기다립니다.

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

## <a name="lockoperator"></a><a name="operator-equality"></a>lock:: operator = =

같음 연산자입니다.

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>매개 변수

*t*<br/>
같은지 비교할 개체입니다.

### <a name="return-value"></a>반환 값

`t` 잠금의 개체와 같으면 `true`을 반환 하 고, 그렇지 않으면 `false`를 반환 합니다.

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

## <a name="lockoperator"></a><a name="operator-inequality"></a>lock:: operator! =

같지 않음 연산자입니다.

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>매개 변수

*t*<br/>
같지 않은지 비교할 개체입니다.

### <a name="return-value"></a>반환 값

`t` 잠금의 개체와 다른 경우 `false` `true`를 반환 합니다.

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