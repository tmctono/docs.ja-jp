---
title: 非同期プログラミングのパターン
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50d76aef201fead37923a65cfeead16638b09842
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031175"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="cce4c-102">非同期プログラミングのパターン</span><span class="sxs-lookup"><span data-stu-id="cce4c-102">Asynchronous programming patterns</span></span>

<span data-ttu-id="cce4c-103">.NET には、非同期操作を実行するための 3 つのパターンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="cce4c-103">.NET provides three patterns for performing asynchronous operations:</span></span>  

- <span data-ttu-id="cce4c-104">**タスク ベースの非同期パターン (TAP)**。1 つのメソッドを使用して非同期操作の開始と完了を表します。</span><span class="sxs-lookup"><span data-stu-id="cce4c-104">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="cce4c-105">TAP は、.NET Framework 4 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cce4c-105">TAP was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="cce4c-106">**.NET で非同期プログラミングを行う場合、これが推奨される方法となります。**</span><span class="sxs-lookup"><span data-stu-id="cce4c-106">**It's the recommended approach to asynchronous programming in .NET.**</span></span> <span data-ttu-id="cce4c-107">C# の [async](~/docs/csharp/language-reference/keywords/async.md) キーワードと [await](~/docs/csharp/language-reference/keywords/await.md) キーワード、および Visual Basic の [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 演算子と [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) 演算子により、TAP の言語サポートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="cce4c-107">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic add language support for TAP.</span></span> <span data-ttu-id="cce4c-108">詳細については、「[タスク ベースの非同期パターン (TAP)](task-based-asynchronous-pattern-tap.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cce4c-108">For more information, see [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>  

- <span data-ttu-id="cce4c-109">**イベント ベースの非同期パターン (EAP)** は、非同期動作を提供するための、イベント ベースの従来のモデルです。</span><span class="sxs-lookup"><span data-stu-id="cce4c-109">**Event-based Asynchronous Pattern (EAP)**, which is the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="cce4c-110">これは、`Async` サフィックスを持つメソッドと、1 つ以上のイベント、イベント ハンドラー デリゲート型、および `EventArg` 派生型を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cce4c-110">It requires a method that has the `Async` suffix and one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="cce4c-111">EAP は、.NET Framework 2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cce4c-111">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="cce4c-112">新規の開発では推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cce4c-112">It's no longer recommended for new development.</span></span> <span data-ttu-id="cce4c-113">詳細については、「[イベント ベースの非同期パターン (EAP)](event-based-asynchronous-pattern-eap.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cce4c-113">For more information, see [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  

- <span data-ttu-id="cce4c-114">**非同期プログラミング モデル (APM)** パターン (<xref:System.IAsyncResult> パターンとも呼ばれます) は、<xref:System.IAsyncResult> インターフェイスを使用して非同期動作を提供する従来のモデルです。</span><span class="sxs-lookup"><span data-stu-id="cce4c-114">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), which is the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="cce4c-115">このパターンでは、同期操作に `Begin` と `End` メソッドが必要になります (たとえば、非同期書き込み操作を実装するための `BeginWrite` と `EndWrite`)。</span><span class="sxs-lookup"><span data-stu-id="cce4c-115">In this pattern, synchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` to implement an asynchronous write operation).</span></span> <span data-ttu-id="cce4c-116">このパターンは、新規の開発では推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cce4c-116">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="cce4c-117">詳細については、「[非同期プログラミング モデル (APM)](asynchronous-programming-model-apm.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cce4c-117">For more information, see [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md).</span></span>  
  
## <a name="comparison-of-patterns"></a><span data-ttu-id="cce4c-118">パターンの比較</span><span class="sxs-lookup"><span data-stu-id="cce4c-118">Comparison of patterns</span></span>

<span data-ttu-id="cce4c-119">3 つのパターンで非同期操作がどのようにモデリングされるかを簡単に比較するために、指定された量のデータを、指定のバッファーの指定されたオフセットに読み込む `Read` メソッドを考えます。</span><span class="sxs-lookup"><span data-stu-id="cce4c-119">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

<span data-ttu-id="cce4c-120">TAP のこのメソッドに対応する部分では、次の単一の `ReadAsync` メソッドが公開されます。</span><span class="sxs-lookup"><span data-stu-id="cce4c-120">The TAP counterpart of this method would expose the following single `ReadAsync` method:</span></span>  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

<span data-ttu-id="cce4c-121">EAP の場合は次の型とメンバーのセットが公開されます。</span><span class="sxs-lookup"><span data-stu-id="cce4c-121">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="cce4c-122">APM の対応する部分では `BeginRead` メソッドと `EndRead` メソッドが公開されます。</span><span class="sxs-lookup"><span data-stu-id="cce4c-122">The APM counterpart would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a><span data-ttu-id="cce4c-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="cce4c-123">See also</span></span>

- [<span data-ttu-id="cce4c-124">非同期の詳細</span><span class="sxs-lookup"><span data-stu-id="cce4c-124">Async in depth</span></span>](../async-in-depth.md)
- [<span data-ttu-id="cce4c-125">C# の非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="cce4c-125">Asynchronous programming in C#</span></span>](~/docs/csharp/async.md)
- [<span data-ttu-id="cce4c-126">F# の非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="cce4c-126">Async Programming in F#</span></span>](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [<span data-ttu-id="cce4c-127">Async および Await を使用した非同期プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cce4c-127">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)
