---
title: Dispose メソッドの実装
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 964c788c5fc1ac791ed3ddd20c9c5c972d07b2c1
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106888"
---
# <a name="implementing-a-dispose-method"></a><span data-ttu-id="61687-102">Dispose メソッドの実装</span><span class="sxs-lookup"><span data-stu-id="61687-102">Implementing a Dispose method</span></span>

<span data-ttu-id="61687-103">アプリケーションによって使用されるアンマネージ リソースを解放するための <xref:System.IDisposable.Dispose%2A> メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="61687-103">You implement a <xref:System.IDisposable.Dispose%2A> method to release unmanaged resources used by your application.</span></span> <span data-ttu-id="61687-104">.NET のガベージ コレクターは、アンマネージ メモリの割り当てや解放を行いません。</span><span class="sxs-lookup"><span data-stu-id="61687-104">The .NET garbage collector does not allocate or release unmanaged memory.</span></span>  
  
<span data-ttu-id="61687-105">[Dispose パターン](../../../docs/standard/design-guidelines/dispose-pattern.md)と呼ばれる、オブジェクトを破棄するパターンによって、オブジェクトの有効期間に順番が付けられます。</span><span class="sxs-lookup"><span data-stu-id="61687-105">The pattern for disposing an object, referred to as a [dispose pattern](../../../docs/standard/design-guidelines/dispose-pattern.md), imposes order on the lifetime of an object.</span></span> <span data-ttu-id="61687-106">Dispose パターンは、ファイルおよびパイプ ハンドル、レジストリ ハンドル、待機ハンドル、アンマネージ メモリ ブロックのポインターなど、アンマネージ リソースにアクセスするオブジェクトでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="61687-106">The dispose pattern is used only for objects that access unmanaged resources, such as file and pipe handles, registry handles, wait handles, or pointers to blocks of unmanaged memory.</span></span> <span data-ttu-id="61687-107">これは、使用されていないマネージド オブジェクトの解放にはガベージ コレクターが非常に有効ですが、アンマネージド オブジェクトは解放できないためです。</span><span class="sxs-lookup"><span data-stu-id="61687-107">This is because the garbage collector is very efficient at reclaiming unused managed objects, but it is unable to reclaim unmanaged objects.</span></span>  
  
<span data-ttu-id="61687-108">Dispose パターンには 2 種類あります。</span><span class="sxs-lookup"><span data-stu-id="61687-108">The dispose pattern has two variations:</span></span>  
  
- <span data-ttu-id="61687-109">型で使用する各アンマネージ リソースをセーフ ハンドル (つまり、<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> から派生したクラス) でラップします。</span><span class="sxs-lookup"><span data-stu-id="61687-109">You wrap each unmanaged resource that a type uses in a safe handle (that is, in a class derived from <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>).</span></span> <span data-ttu-id="61687-110">この場合、<xref:System.IDisposable> インターフェイスと追加の `Dispose(Boolean)` メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="61687-110">In this case, you implement the <xref:System.IDisposable> interface and an additional `Dispose(Boolean)` method.</span></span> <span data-ttu-id="61687-111">これは推奨される方法で、<xref:System.Object.Finalize%2A?displayProperty=nameWithType> メソッドをオーバーライドする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="61687-111">This is the recommended variation and doesn't require overriding the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span>  
  
  > [!NOTE]
  > <span data-ttu-id="61687-112"><xref:Microsoft.Win32.SafeHandles?displayProperty=nameWithType> 名前空間には <xref:System.Runtime.InteropServices.SafeHandle> から派生した一連のクラスが用意されています。これらのクラスの一覧については、「[セーフ ハンドルの使用](#SafeHandles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61687-112">The <xref:Microsoft.Win32.SafeHandles?displayProperty=nameWithType> namespace provides a set of classes derived from <xref:System.Runtime.InteropServices.SafeHandle>, which are listed in the [Using safe handles](#SafeHandles) section.</span></span> <span data-ttu-id="61687-113">アンマネージ リソースを解放できるクラスが見つからない場合は、<xref:System.Runtime.InteropServices.SafeHandle> の独自のサブクラスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="61687-113">If you can't find a class that is suitable for releasing your unmanaged resource, you can implement your own subclass of <xref:System.Runtime.InteropServices.SafeHandle>.</span></span>  
  
- <span data-ttu-id="61687-114"><xref:System.IDisposable> インターフェイスと追加の `Dispose(Boolean)` メソッドを実装し、<xref:System.Object.Finalize%2A?displayProperty=nameWithType> メソッドもオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="61687-114">You implement the <xref:System.IDisposable> interface and an additional `Dispose(Boolean)` method, and you also override the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="61687-115"><xref:System.Object.Finalize%2A> の実装が型のコンシューマーによって呼び出されなかった場合にアンマネージ リソースが破棄されるように、<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> をオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61687-115">You must override <xref:System.Object.Finalize%2A> to ensure that unmanaged resources are disposed of if your <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation is not called by a consumer of your type.</span></span> <span data-ttu-id="61687-116">前の項目で説明された推奨される方法を使用すると、<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> クラスが代わりにこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="61687-116">If you use the recommended technique discussed in the previous bullet, the <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> class does this on your behalf.</span></span>  
  
<span data-ttu-id="61687-117"><xref:System.IDisposable.Dispose%2A> メソッドが複数回呼び出される場合でも、例外をスローすることなく呼び出されるようにして、リソースが常に適切にクリーンアップされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61687-117">To help ensure that resources are always cleaned up appropriately, a <xref:System.IDisposable.Dispose%2A> method should be callable multiple times without throwing an exception.</span></span>  
  
<span data-ttu-id="61687-118"><xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> メソッドのコード例では、再利用するオブジェクトのメンバーがまだ実行中の場合でも、ガベージ コレクションがファイナライザーを実行しようとします。</span><span class="sxs-lookup"><span data-stu-id="61687-118">The code example provided for the <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> method shows how aggressive garbage collection can cause a finalizer to run while a member of the reclaimed object is still executing.</span></span> <span data-ttu-id="61687-119">長い <xref:System.GC.KeepAlive%2A> メソッドの最後に、<xref:System.IDisposable.Dispose%2A> メソッドを呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="61687-119">It is a good idea to call the <xref:System.GC.KeepAlive%2A> method at the end of a lengthy <xref:System.IDisposable.Dispose%2A> method.</span></span>  
  
<a name="Dispose2"></a>
## <a name="dispose-and-disposeboolean"></a><span data-ttu-id="61687-120">Dispose() と Dispose(Boolean)</span><span class="sxs-lookup"><span data-stu-id="61687-120">Dispose() and Dispose(Boolean)</span></span>  

<span data-ttu-id="61687-121"><xref:System.IDisposable> インターフェイスでは、パラメーターのない <xref:System.IDisposable.Dispose%2A> メソッドを 1 つ実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61687-121">The <xref:System.IDisposable> interface requires the implementation of a single parameterless method, <xref:System.IDisposable.Dispose%2A>.</span></span> <span data-ttu-id="61687-122">しかし、Dispose パターンでは 2 種類の `Dispose` メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61687-122">However, the dispose pattern requires two `Dispose` methods to be implemented:</span></span>  
  
- <span data-ttu-id="61687-123">public で非仮想 (Visual Basic では `NonInheritable`) の <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> の実装。パラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="61687-123">A public non-virtual (`NonInheritable` in Visual Basic) <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation that has no parameters.</span></span>  
  
- <span data-ttu-id="61687-124">protected で仮想 (Visual Basic では `Overridable`) の `Dispose` メソッド。シグネチャは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="61687-124">A protected virtual (`Overridable` in Visual Basic) `Dispose` method whose signature is:</span></span>  
  
  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]  
  
### <a name="the-dispose-overload"></a><span data-ttu-id="61687-125">Dispose() オーバーロード</span><span class="sxs-lookup"><span data-stu-id="61687-125">The Dispose() overload</span></span>

<span data-ttu-id="61687-126">この public で非仮想 (Visual Basic では `NonInheritable`)、パラメーターなしの `Dispose` メソッドは、型のコンシューマーによって呼び出されるため、その目的は、アンマネージ リソースを解放し、ファイナライザーが存在する場合、それを実行する必要がないことを示すことです。</span><span class="sxs-lookup"><span data-stu-id="61687-126">Because the public, non-virtual (`NonInheritable` in Visual Basic), parameterless `Dispose` method is called by a consumer of the type, its purpose is to free unmanaged resources and to indicate that the finalizer, if one is present, doesn't have to run.</span></span> <span data-ttu-id="61687-127">このため、次のような標準的な実装があります。</span><span class="sxs-lookup"><span data-stu-id="61687-127">Because of this, it has a standard implementation:</span></span>  
  
[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]  
  
<span data-ttu-id="61687-128">`Dispose` メソッドはオブジェクトのクリーンアップをすべて実行するため、ガベージ コレクターはもはやオブジェクトの <xref:System.Object.Finalize%2A?displayProperty=nameWithType> のオーバーライドを呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="61687-128">The `Dispose` method performs all object cleanup, so the garbage collector no longer needs to call the objects' <xref:System.Object.Finalize%2A?displayProperty=nameWithType> override.</span></span> <span data-ttu-id="61687-129">そこで、<xref:System.GC.SuppressFinalize%2A> メソッドを呼び出して、ガベージ コレクターによるファイナライザーの実行を抑制します。</span><span class="sxs-lookup"><span data-stu-id="61687-129">Therefore, the call to the <xref:System.GC.SuppressFinalize%2A> method prevents the garbage collector from running the finalizer.</span></span> <span data-ttu-id="61687-130">型にファイナライザーがない場合、<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> を呼び出しても無効です。</span><span class="sxs-lookup"><span data-stu-id="61687-130">If the type has no finalizer, the call to <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> has no effect.</span></span> <span data-ttu-id="61687-131">アンマネージ リソースを解放する実際の作業は `Dispose` メソッドの 2 番目のオーバーロードによって実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="61687-131">Note that the actual work of releasing unmanaged resources is performed by the second overload of the `Dispose` method.</span></span>  
  
### <a name="the-disposeboolean-overload"></a><span data-ttu-id="61687-132">Dispose(Boolean) オーバーロード</span><span class="sxs-lookup"><span data-stu-id="61687-132">The Dispose(Boolean) overload</span></span>

<span data-ttu-id="61687-133">2 番目のオーバーロードでは、*disposing* パラメーターは <xref:System.Boolean> で、メソッドの呼び出し元が <xref:System.IDisposable.Dispose%2A> メソッドか (値は `true`)、それともファイナライザーか (値は `false`) を示します。</span><span class="sxs-lookup"><span data-stu-id="61687-133">In the second overload, the *disposing* parameter is a <xref:System.Boolean> that indicates whether the method call comes from a <xref:System.IDisposable.Dispose%2A> method (its value is `true`) or from a finalizer (its value is `false`).</span></span>  
  
<span data-ttu-id="61687-134">メソッドの本体は 2 つのコード ブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="61687-134">The body of the method consists of two blocks of code:</span></span>  
  
- <span data-ttu-id="61687-135">アンマネージ リソースを解放するブロック。</span><span class="sxs-lookup"><span data-stu-id="61687-135">A block that frees unmanaged resources.</span></span> <span data-ttu-id="61687-136">このブロックは、`disposing` パラメーターの値に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="61687-136">This block executes regardless of the value of the `disposing` parameter.</span></span>  
  
- <span data-ttu-id="61687-137">マネージド リソースを解放する条件付きブロック。</span><span class="sxs-lookup"><span data-stu-id="61687-137">A conditional block that frees managed resources.</span></span> <span data-ttu-id="61687-138">このブロックは、`disposing` の値が `true` の場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="61687-138">This block executes if the value of `disposing` is `true`.</span></span> <span data-ttu-id="61687-139">解放するマネージド リソースには、次のオブジェクトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="61687-139">The managed resources that it frees can include:</span></span>  
  
  <span data-ttu-id="61687-140">**<xref:System.IDisposable> を実装するマネージド オブジェクト。**</span><span class="sxs-lookup"><span data-stu-id="61687-140">**Managed objects that implement <xref:System.IDisposable>.**</span></span> <span data-ttu-id="61687-141">条件付きブロックを使用して <xref:System.IDisposable.Dispose%2A> の実装を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="61687-141">The conditional block can be used to call their <xref:System.IDisposable.Dispose%2A> implementation.</span></span> <span data-ttu-id="61687-142">セーフ ハンドルを使用してアンマネージ リソースをラップしている場合は、ここで <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=nameWithType> の実装を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="61687-142">If you have used a safe handle to wrap your unmanaged resource, you should call the <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=nameWithType> implementation here.</span></span>  
  
  <span data-ttu-id="61687-143">**大量のメモリを消費するか、不足しているリソースを消費するマネージド オブジェクト。**</span><span class="sxs-lookup"><span data-stu-id="61687-143">**Managed objects that consume large amounts of memory or consume scarce resources.**</span></span> <span data-ttu-id="61687-144">これらのオブジェクトを `Dispose` メソッドで明示的に解放すると、ガベージ コレクターによって非確定的に解放される場合よりも迅速に解放されます。</span><span class="sxs-lookup"><span data-stu-id="61687-144">Freeing these objects explicitly in the `Dispose` method releases them faster than if they were reclaimed non-deterministically by the garbage collector.</span></span>  
  
<span data-ttu-id="61687-145">メソッドの呼び出し元がファイナライザーの場合 (つまり、*disposing* が `false` の場合)、アンマネージ リソースを解放するコードだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="61687-145">If the method call comes from a finalizer (that is, if *disposing* is `false`), only the code that frees unmanaged resources executes.</span></span> <span data-ttu-id="61687-146">ガベージ コレクターが終了処理の際にマネージド オブジェクトを破棄する順序は定義されていないため、値 `Dispose` を指定した `false` オーバーロードを呼び出すことで、既に解放されている可能性のあるマネージド リソースをファイナライザーが解放しようとすることを防止できます。</span><span class="sxs-lookup"><span data-stu-id="61687-146">Because the order in which the garbage collector destroys managed objects during finalization is not defined, calling this `Dispose` overload with a value of `false` prevents the finalizer from trying to release managed resources that may have already been reclaimed.</span></span>  
  
## <a name="implementing-the-dispose-pattern-for-a-base-class"></a><span data-ttu-id="61687-147">基底クラスでの Dispose パターンの実装</span><span class="sxs-lookup"><span data-stu-id="61687-147">Implementing the dispose pattern for a base class</span></span>

<span data-ttu-id="61687-148">基底クラスで Dispose パターンを実装する場合、以下の項目を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61687-148">If you implement the dispose pattern for a base class, you must provide the following:</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="61687-149"><xref:System.IDisposable.Dispose> を実装し、 `sealed` (Visual Basic では `NotInheritable`) ではないすべてのベース クラスにこのパターンを実装してください。</span><span class="sxs-lookup"><span data-stu-id="61687-149">You should implement this pattern for all base classes that implement <xref:System.IDisposable.Dispose> and are not `sealed` (`NotInheritable` in Visual Basic).</span></span>  
  
- <span data-ttu-id="61687-150"><xref:System.IDisposable.Dispose%2A> メソッドを呼び出す `Dispose(Boolean)` の実装。</span><span class="sxs-lookup"><span data-stu-id="61687-150">A <xref:System.IDisposable.Dispose%2A> implementation that calls the `Dispose(Boolean)` method.</span></span>  
  
- <span data-ttu-id="61687-151">リソースを解放する実際の作業を実行する `Dispose(Boolean)` メソッド。</span><span class="sxs-lookup"><span data-stu-id="61687-151">A `Dispose(Boolean)` method that performs the actual work of releasing resources.</span></span>  
  
- <span data-ttu-id="61687-152">アンマネージ リソースをラップする <xref:System.Runtime.InteropServices.SafeHandle> から派生したクラス (推奨)、または、<xref:System.Object.Finalize%2A?displayProperty=nameWithType> メソッドのオーバーライド。</span><span class="sxs-lookup"><span data-stu-id="61687-152">Either a class derived from <xref:System.Runtime.InteropServices.SafeHandle> that wraps your unmanaged resource (recommended), or an override to the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="61687-153"><xref:System.Runtime.InteropServices.SafeHandle> クラスには、コーディングが不要なファイナライザーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="61687-153">The <xref:System.Runtime.InteropServices.SafeHandle> class provides a finalizer that frees you from having to code one.</span></span>  
  
<span data-ttu-id="61687-154">セーフ ハンドルを使用して基底クラスで Dispose パターンを実装する一般的なパターンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="61687-154">Here's the general pattern for implementing the dispose pattern for a base class that uses a safe handle.</span></span>  
  
[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]  
  
> [!NOTE]
> <span data-ttu-id="61687-155">前の例では、<xref:Microsoft.Win32.SafeHandles.SafeFileHandle> オブジェクトを使用してパターンを示しています。代わりに、<xref:System.Runtime.InteropServices.SafeHandle> から派生した任意のオブジェクトを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="61687-155">The previous example uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object to illustrate the pattern; any object derived from <xref:System.Runtime.InteropServices.SafeHandle> could be used instead.</span></span> <span data-ttu-id="61687-156">例では、<xref:Microsoft.Win32.SafeHandles.SafeFileHandle> オブジェクトを正しくインスタンス化していないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="61687-156">Note that the example does not properly instantiate its <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object.</span></span>  
  
<span data-ttu-id="61687-157"><xref:System.Object.Finalize%2A?displayProperty=nameWithType> をオーバーライドして基底クラスで Dispose パターンを実装する一般的なパターンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="61687-157">Here's the general pattern for implementing the dispose pattern for a base class that overrides <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.</span></span>  
  
[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]  
  
> [!NOTE]
> <span data-ttu-id="61687-158">C# では、[デストラクター](../../csharp/programming-guide/classes-and-structs/destructors.md)を定義することによって、<xref:System.Object.Finalize%2A?displayProperty=nameWithType> をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="61687-158">In C#, you override <xref:System.Object.Finalize%2A?displayProperty=nameWithType> by defining a [destructor](../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a><span data-ttu-id="61687-159">派生クラスでの Dispose パターンの実装</span><span class="sxs-lookup"><span data-stu-id="61687-159">Implementing the dispose pattern for a derived class</span></span>

<span data-ttu-id="61687-160"><xref:System.IDisposable> インターフェイスを実装するクラスから派生したクラスは、<xref:System.IDisposable> の基底クラスでの実装が派生クラスに継承されるため、<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> を実装しないでください。</span><span class="sxs-lookup"><span data-stu-id="61687-160">A class derived from a class that implements the <xref:System.IDisposable> interface shouldn't implement <xref:System.IDisposable>, because the base class implementation of <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> is inherited by its derived classes.</span></span> <span data-ttu-id="61687-161">代わりに、派生クラスで Dispose パターンを実装するには、以下の項目を用意します。</span><span class="sxs-lookup"><span data-stu-id="61687-161">Instead, to implement the dispose pattern for a derived class, you provide the following:</span></span>  
  
- <span data-ttu-id="61687-162">基底クラスのメソッドをオーバーライドして、派生クラスのリソースを解放する実際の作業を実行する `protected Dispose(Boolean)` メソッド。</span><span class="sxs-lookup"><span data-stu-id="61687-162">A `protected Dispose(Boolean)` method that overrides the base class method and performs the actual work of releasing the resources of the derived class.</span></span> <span data-ttu-id="61687-163">このメソッドは、基底クラスの `Dispose(Boolean)` メソッドも呼び出して、引数の破棄状態を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="61687-163">This method should also call the `Dispose(Boolean)` method of the base class and pass its disposing status for the argument.</span></span>  
  
- <span data-ttu-id="61687-164">アンマネージ リソースをラップする <xref:System.Runtime.InteropServices.SafeHandle> から派生したクラス (推奨)、または、<xref:System.Object.Finalize%2A?displayProperty=nameWithType> メソッドのオーバーライド。</span><span class="sxs-lookup"><span data-stu-id="61687-164">Either a class derived from <xref:System.Runtime.InteropServices.SafeHandle> that wraps your unmanaged resource (recommended), or an override to the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="61687-165"><xref:System.Runtime.InteropServices.SafeHandle> クラスには、コーディングが不要なファイナライザーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="61687-165">The <xref:System.Runtime.InteropServices.SafeHandle> class provides a finalizer that frees you from having to code one.</span></span> <span data-ttu-id="61687-166">ファイナライザーを用意する場合は、*disposing* 引数を `false` として `Dispose(Boolean)` オーバーロードを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="61687-166">If you do provide a finalizer, it should call the `Dispose(Boolean)` overload with a *disposing* argument of `false`.</span></span>  
  
<span data-ttu-id="61687-167">セーフ ハンドルを使用して派生クラスで Dispose パターンを実装する一般的なパターンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="61687-167">Here's the general pattern for implementing the dispose pattern for a derived class that uses a safe handle:</span></span>  
  
[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="61687-168">前の例では、<xref:Microsoft.Win32.SafeHandles.SafeFileHandle> オブジェクトを使用してパターンを示しています。代わりに、<xref:System.Runtime.InteropServices.SafeHandle> から派生した任意のオブジェクトを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="61687-168">The previous example uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object to illustrate the pattern; any object derived from <xref:System.Runtime.InteropServices.SafeHandle> could be used instead.</span></span> <span data-ttu-id="61687-169">例では、<xref:Microsoft.Win32.SafeHandles.SafeFileHandle> オブジェクトを正しくインスタンス化していないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="61687-169">Note that the example does not properly instantiate its <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object.</span></span>  
  
<span data-ttu-id="61687-170"><xref:System.Object.Finalize%2A?displayProperty=nameWithType> をオーバーライドして派生クラスで Dispose パターンを実装する一般的なパターンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="61687-170">Here's the general pattern for implementing the dispose pattern for a derived class that overrides <xref:System.Object.Finalize%2A?displayProperty=nameWithType>:</span></span>  
  
[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="61687-171">C# では、[デストラクター](../../csharp/programming-guide/classes-and-structs/destructors.md)を定義することによって、<xref:System.Object.Finalize%2A?displayProperty=nameWithType> をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="61687-171">In C#, you override <xref:System.Object.Finalize%2A?displayProperty=nameWithType> by defining a [destructor](../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
<a name="SafeHandles"></a>   
## <a name="using-safe-handles"></a><span data-ttu-id="61687-172">セーフ ハンドルの使用</span><span class="sxs-lookup"><span data-stu-id="61687-172">Using safe handles</span></span>

<span data-ttu-id="61687-173">オブジェクトのファイナライザーのコードを記述することは、正しく行わないと問題が発生する可能性がある複雑なタスクです。</span><span class="sxs-lookup"><span data-stu-id="61687-173">Writing code for an object's finalizer is a complex task that can cause problems if not done correctly.</span></span> <span data-ttu-id="61687-174">そのため、ファイナライザーを実装するのではなく、<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> オブジェクトを構築することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="61687-174">Therefore, we recommend that you construct <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> objects instead of implementing a finalizer.</span></span>  
  
<span data-ttu-id="61687-175"><xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> クラスから派生したクラスは、処理を中断することなくハンドルの割り当てと解放を行うことで、オブジェクトの有効期間に関する問題を単純化します。</span><span class="sxs-lookup"><span data-stu-id="61687-175">Classes derived from the <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> class simplify object lifetime issues by assigning and releasing handles without interruption.</span></span> <span data-ttu-id="61687-176">セーフ ハンドルは、アプリケーション ドメインのアンロード中に確実に実行されるクリティカル ファイナライザーを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="61687-176">They contain a critical finalizer that is guaranteed to run while an application domain is unloading.</span></span> <span data-ttu-id="61687-177">セーフ ハンドルを使用する利点の詳細については、「<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61687-177">For more information about the advantages of using a safe handle, see <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="61687-178"><xref:Microsoft.Win32.SafeHandles> 名前空間の次の派生クラスは、セーフ ハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="61687-178">The following derived classes in the <xref:Microsoft.Win32.SafeHandles> namespace provide safe handles:</span></span>  
  
- <span data-ttu-id="61687-179">ファイル、メモリ マップ ファイルおよびパイプのための <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>、<xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle>、<xref:Microsoft.Win32.SafeHandles.SafePipeHandle> クラス。</span><span class="sxs-lookup"><span data-stu-id="61687-179">The <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle>, and <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> class, for files, memory mapped files, and pipes.</span></span>  
  
- <span data-ttu-id="61687-180">メモリ ビューのための <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> クラス。</span><span class="sxs-lookup"><span data-stu-id="61687-180">The <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> class, for memory views.</span></span>  
  
- <span data-ttu-id="61687-181">暗号の構成要素のための <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>、<xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle>、<xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> クラス。</span><span class="sxs-lookup"><span data-stu-id="61687-181">The <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle>, and <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> classes, for cryptography constructs.</span></span>  
  
- <span data-ttu-id="61687-182">レジストリ キーのための <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> クラス。</span><span class="sxs-lookup"><span data-stu-id="61687-182">The <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> class, for registry keys.</span></span>  
  
- <span data-ttu-id="61687-183">待機ハンドルのための <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> クラス。</span><span class="sxs-lookup"><span data-stu-id="61687-183">The <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> class, for wait handles.</span></span>  
  
<a name="base"></a>   
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-base-class"></a><span data-ttu-id="61687-184">セーフ ハンドルを使用した基底クラスでの Dispose パターンの実装</span><span class="sxs-lookup"><span data-stu-id="61687-184">Using a safe handle to implement the dispose pattern for a base class</span></span>

<span data-ttu-id="61687-185">次の例は、セーフ ハンドルを使用してアンマネージ リソースをカプセル化する、基底クラス `DisposableStreamResource` での Dispose パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="61687-185">The following example illustrates the dispose pattern for a base class, `DisposableStreamResource`, that uses a safe handle to encapsulate unmanaged resources.</span></span> <span data-ttu-id="61687-186">例では、`DisposableResource` を使用して、開いているファイルを表す <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> オブジェクトをラップする <xref:System.IO.Stream> クラスを定義しています。</span><span class="sxs-lookup"><span data-stu-id="61687-186">It defines a `DisposableResource` class that uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> to wrap a <xref:System.IO.Stream> object that represents an open file.</span></span> <span data-ttu-id="61687-187">`DisposableResource` メソッドには、ファイル ストリームの合計バイト数を返す `Size` プロパティも含まれています。</span><span class="sxs-lookup"><span data-stu-id="61687-187">The `DisposableResource` method also includes a single property, `Size`, that returns the total number of bytes in the file stream.</span></span>  
  
[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]  
  
<a name="derived"></a>   
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-derived-class"></a><span data-ttu-id="61687-188">セーフ ハンドルを使用した派生クラスでの Dispose パターンの実装</span><span class="sxs-lookup"><span data-stu-id="61687-188">Using a safe handle to implement the dispose pattern for a derived class</span></span>

<span data-ttu-id="61687-189">次の例は、前の例で挙げた `DisposableStreamResource2` クラスを継承した派生クラス `DisposableStreamResource` での Dispose パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="61687-189">The following example illustrates the dispose pattern for a derived class, `DisposableStreamResource2`, that inherits from the `DisposableStreamResource` class presented in the previous example.</span></span> <span data-ttu-id="61687-190">このクラスは `WriteFileInfo` メソッドを追加し、<xref:Microsoft.Win32.SafeHandles.SafeFileHandle> オブジェクトを使用して書き込み可能ファイル ハンドルをラップしています。</span><span class="sxs-lookup"><span data-stu-id="61687-190">The class adds an additional method, `WriteFileInfo`, and uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object to wrap the handle of the writable file.</span></span>  
  
[!code-csharp[Conceptual.Disposable#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/derived1.cs#10)]
[!code-vb[Conceptual.Disposable#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/derived1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="61687-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="61687-191">See also</span></span>

- <xref:System.GC.SuppressFinalize%2A>
- <xref:System.IDisposable>
- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>
- <xref:Microsoft.Win32.SafeHandles>
- <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="61687-192">方法: クラスと構造体を定義および使用する (C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="61687-192">How to: Define and Consume Classes and Structs (C++/CLI)</span></span>](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli)
- [<span data-ttu-id="61687-193">Dispose パターン</span><span class="sxs-lookup"><span data-stu-id="61687-193">Dispose Pattern</span></span>](../../../docs/standard/design-guidelines/dispose-pattern.md)
