---
title: .NET Core でアセンブリのアンローダビリティを使用およびデバッグする方法
description: マネージド アセンブリのロードとアンロードに収集可能な AssemblyLoadContext を使用する方法とアンロードの成功を妨げる問題をデバッグする方法について説明します。
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: a3ba2c2809aedd0af03ec965089f8779c430a335
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2019
ms.locfileid: "68671247"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="eb966-103">.NET Core でアセンブリのアンローダビリティを使用およびデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="eb966-103">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="eb966-104">.NET Core 3.0 以降では、一連のアセンブリをロードし、後でアンロードする機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="eb966-104">Starting with .NET Core 3.0, the ability to load and later unload a set of assemblies is supported.</span></span> <span data-ttu-id="eb966-105">.NET Framework では、この目的でカスタム アプリ ドメインが使用されていましたが、.NET Core では、既定のアプリ ドメインは 1 つしかサポートされません。</span><span class="sxs-lookup"><span data-stu-id="eb966-105">In .NET Framework, custom app domains were used for this purpose, but .NET Core only supports a single default app domain.</span></span>

<span data-ttu-id="eb966-106">このため、.NET Core 3.0 以降のバージョンでは、アンロードをサポートするために <xref:System.Runtime.Loader.AssemblyLoadContext> が用意されています。</span><span class="sxs-lookup"><span data-stu-id="eb966-106">.NET Core 3.0 and later versions support unloadability through <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="eb966-107">一連のアセンブリを収集可能な `AssemblyLoadContext` にロードし、その中のメソッドを実行するか、またはリフレクションを使用して調べた後、最後に `AssemblyLoadContext` をアンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="eb966-107">You can load a set of assemblies into a collectible `AssemblyLoadContext`, execute methods in them or just inspect them using reflection, and finally unload the `AssemblyLoadContext`.</span></span> <span data-ttu-id="eb966-108">これにより、その `AssemblyLoadContext` にロードされたアセンブリがアンロードされます。</span><span class="sxs-lookup"><span data-stu-id="eb966-108">That unloads the assemblies loaded into that `AssemblyLoadContext`.</span></span>

<span data-ttu-id="eb966-109">`AssemblyLoadContext` を使用したアンロードと AppDomain を使用したアンロードには、1 つの注目すべき違いがあります。</span><span class="sxs-lookup"><span data-stu-id="eb966-109">There's one noteworthy difference between the unloading using `AssemblyLoadContext` and using AppDomains.</span></span> <span data-ttu-id="eb966-110">AppDomain では、アンロードが強制されます。</span><span class="sxs-lookup"><span data-stu-id="eb966-110">With AppDomains, the unloading is forced.</span></span> <span data-ttu-id="eb966-111">たとえば、アップロード時には、ターゲットの AppDomain で実行中のすべてのスレッドが中止され、ターゲットの AppDomain で作成されたマネージド COM オブジェクトは破棄されます。`AssemblyLoadContext` では、アンロードは "協調的" です。</span><span class="sxs-lookup"><span data-stu-id="eb966-111">At the unload time, all threads running in the target AppDomain are aborted, managed COM objects created in the target AppDomain are destroyed, etc. With `AssemblyLoadContext`, the unload is "cooperative".</span></span> <span data-ttu-id="eb966-112"><xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> メソッドを呼び出すと、アンロードが単に開始されるだけです。</span><span class="sxs-lookup"><span data-stu-id="eb966-112">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> method just initiates the unloading.</span></span> <span data-ttu-id="eb966-113">アンロードは次の場合に完了します。</span><span class="sxs-lookup"><span data-stu-id="eb966-113">The unloading finishes after:</span></span>

- <span data-ttu-id="eb966-114">コール スタックに、`AssemblyLoadContext` にロードされたアセンブリ内のメソッドを含むスレッドがなくなった。</span><span class="sxs-lookup"><span data-stu-id="eb966-114">No threads have methods from the assemblies loaded into the `AssemblyLoadContext` on their call stacks.</span></span>
- <span data-ttu-id="eb966-115">`AssemblyLoadContext` にロードされたアセンブリ内の型、それらの型のインスタンス、およびアセンブリ自体が、次の方法により、`AssemblyLoadContext` の外部で参照されなくなった。</span><span class="sxs-lookup"><span data-stu-id="eb966-115">None of the types from the assemblies loaded into the `AssemblyLoadContext`, instances of those types and the assemblies themselves outside of the `AssemblyLoadContext` are referenced by:</span></span>
  - <span data-ttu-id="eb966-116">弱い参照 (<xref:System.WeakReference> または <xref:System.WeakReference%601>) を除く、`AssemblyLoadContext` の外部での参照。</span><span class="sxs-lookup"><span data-stu-id="eb966-116">References outside of the `AssemblyLoadContext`, except of weak references (<xref:System.WeakReference> or <xref:System.WeakReference%601>).</span></span>
  - <span data-ttu-id="eb966-117">`AssemblyLoadContext` の内部と外部の両方からの強力な GC ハンドル (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span><span class="sxs-lookup"><span data-stu-id="eb966-117">Strong GC handles (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span></span> <span data-ttu-id="eb966-118">または <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>)。</span><span class="sxs-lookup"><span data-stu-id="eb966-118">or <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) from both inside and outside of the `AssemblyLoadContext`.</span></span>

## <a name="using-collectible-assemblyloadcontext"></a><span data-ttu-id="eb966-119">収集可能な AssemblyLoadContext の使用</span><span class="sxs-lookup"><span data-stu-id="eb966-119">Using collectible AssemblyLoadContext</span></span>

<span data-ttu-id="eb966-120">このセクションは、収集可能な `AssemblyLoadContext` に NET Core アプリケーションをロードして、そのエントリ ポイントを実行した後、NET Core アプリケーションをアンロードするための簡単な方法を詳細に説明したステップバイステップのチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="eb966-120">This section contains a detailed step-by-step tutorial that shows a simple way to load a .NET Core application into a collectible `AssemblyLoadContext`, execute its entry point, and then unload it.</span></span> <span data-ttu-id="eb966-121">完全なサンプルについては、<https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb966-121">You can find a complete sample at <https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading>.</span></span>

### <a name="create-a-collectible-assemblyloadcontext"></a><span data-ttu-id="eb966-122">収集可能な AssemblyLoadContext を作成する</span><span class="sxs-lookup"><span data-stu-id="eb966-122">Create a collectible AssemblyLoadContext</span></span>

<span data-ttu-id="eb966-123"><xref:System.Runtime.Loader.AssemblyLoadContext> からクラスを派生させ、その <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> メソッドをオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb966-123">You need to derive your class from the <xref:System.Runtime.Loader.AssemblyLoadContext> and overload its <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="eb966-124">このメソッドは、その `AssemblyLoadContext` に読み込まれたアセンブリと依存関係にあるすべてのアセンブリへの参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="eb966-124">That method resolves references to all assemblies that are dependencies of assemblies loaded into that `AssemblyLoadContext`.</span></span>
<span data-ttu-id="eb966-125">次のコードは、最も簡単なカスタム `AssemblyLoadContext` の例を示します。</span><span class="sxs-lookup"><span data-stu-id="eb966-125">The following code is an example of the simplest custom `AssemblyLoadContext`:</span></span>

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

<span data-ttu-id="eb966-126">ご覧のとおり、`Load` メソッドから `null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="eb966-126">As you can see, the `Load` method returns `null`.</span></span> <span data-ttu-id="eb966-127">つまり、すべての依存関係アセンブリが既定のコンテキストに読み込まれ、新しいコンテキストには、そこに明示的に読み込まれたアセンブリのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eb966-127">That means that all the dependency assemblies are loaded into the default context, and the new context contains only the assemblies explicitly loaded into it.</span></span>

<span data-ttu-id="eb966-128">一部またはすべての依存関係も `AssemblyLoadContext` に読み込む必要がある場合は、`Load` メソッドで `AssemblyDependencyResolver` を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="eb966-128">If you want to load some or all of the dependencies into the `AssemblyLoadContext` too, you can use the `AssemblyDependencyResolver` in the `Load` method.</span></span> <span data-ttu-id="eb966-129">`AssemblyDependencyResolver` は、コンテキストに読み込まれるメイン アセンブリのディレクトリに含まれる " *.deps.json*" ファイルを使用し、そのディレクトリ内のアセンブリ ファイルを使用して、アセンブリ名を解決してアセンブリ ファイルの絶対パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="eb966-129">The `AssemblyDependencyResolver` resolves the assembly names to absolute assembly file paths using the *.deps.json* file contained in the directory of the main assembly loaded into the context and using assembly files in that directory.</span></span>

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a><span data-ttu-id="eb966-130">カスタムの収集可能な AssemblyLoadContext を使用する</span><span class="sxs-lookup"><span data-stu-id="eb966-130">Use a custom collectible AssemblyLoadContext</span></span>

<span data-ttu-id="eb966-131">このセクションでは、より単純な `TestAssemblyLoadContext` が使用されていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="eb966-131">This section assumes the simpler version of the `TestAssemblyLoadContext` is being used.</span></span>

<span data-ttu-id="eb966-132">次のように、カスタム `AssemblyLoadContext` のインスタンスを作成して、アセンブリをそこに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="eb966-132">You can create an instance of the custom `AssemblyLoadContext` and load an assembly into it as follows:</span></span>

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

<span data-ttu-id="eb966-133">読み込まれたアセンブリによって参照される各アセンブリについて、`TestAssemblyLoadContext.Load` メソッドを呼び出して、`TestAssemblyLoadContext` がどこからアセンブリを取得すればよいかを判断できるようにします。</span><span class="sxs-lookup"><span data-stu-id="eb966-133">For each of the assemblies referenced by the loaded assembly, the `TestAssemblyLoadContext.Load` method is called so that the `TestAssemblyLoadContext` can decide where to get the assembly from.</span></span> <span data-ttu-id="eb966-134">この例では、`null` が返されます。これは、ランタイムでアセンブリを読み込むために既定で使用される場所から既定のコンテキストに読み込む必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="eb966-134">In our case, it returns `null` to indicate that it should be loaded into the default context from locations that the runtime uses to load assemblies by default.</span></span>

<span data-ttu-id="eb966-135">アセンブリが読み込まれたので、そこからメソッドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="eb966-135">Now that an assembly was loaded, you can execute a method from it.</span></span> <span data-ttu-id="eb966-136">`Main` メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb966-136">Run the `Main` method:</span></span>

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

<span data-ttu-id="eb966-137">`Main` メソッドが返ると、カスタム `AssemblyLoadContext` で `Unload` メソッドを呼び出すか、`AssemblyLoadContext` に対する参照を削除することにより、アンロードを開始できます。</span><span class="sxs-lookup"><span data-stu-id="eb966-137">After the `Main` method returns, you can initiate unloading by either calling the `Unload` method on the custom `AssemblyLoadContext` or getting rid of the reference you have to the `AssemblyLoadContext`:</span></span>

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

<span data-ttu-id="eb966-138">これだけでテスト アセンブリをアンロードできます。</span><span class="sxs-lookup"><span data-stu-id="eb966-138">This is sufficient to unload the test assembly.</span></span> <span data-ttu-id="eb966-139">では、実際に、これらすべてをインライン化できない個別のメソッドに配置して、`TestAssemblyLoadContext`、`Assembly`、および `MethodInfo` (`Assembly.EntryPoint`) が、スタック スロット参照 (実数または JIT 対応のローカル) でキープ アライブできないようにしましょう。</span><span class="sxs-lookup"><span data-stu-id="eb966-139">Let's actually put all of this into a separate non-inlineable method to ensure that the `TestAssemblyLoadContext`, `Assembly`, and `MethodInfo` (the `Assembly.EntryPoint`) can't be kept alive by stack slot references (real- or JIT-introduced locals).</span></span> <span data-ttu-id="eb966-140">これにより、`TestAssemblyLoadContext` をキープ アライブし、アンロードを妨ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="eb966-140">That could keep the `TestAssemblyLoadContext` alive and prevent the unload.</span></span>

<span data-ttu-id="eb966-141">また、`AssemblyLoadContext` への弱い参照が返されるので、後でこれを使用して、アンロードの完了を検出できます。</span><span class="sxs-lookup"><span data-stu-id="eb966-141">Also, return a weak reference to the `AssemblyLoadContext` so that you can use it later to detect unload completion.</span></span>

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

<span data-ttu-id="eb966-142">これで、この関数を実行して、アセンブリのロード、実行、アンロードを行うことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eb966-142">Now you can run this function to load, execute, and unload the assembly.</span></span>

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

<span data-ttu-id="eb966-143">ただし、アンロードは即座には完了しません。</span><span class="sxs-lookup"><span data-stu-id="eb966-143">However, the unload doesn't complete immediately.</span></span> <span data-ttu-id="eb966-144">前述のとおり、これは、GC に依存して、テスト アセンブリからすべてのオブジェクトを収集します。</span><span class="sxs-lookup"><span data-stu-id="eb966-144">As previously mentioned, it relies on the GC to collect all the objects from the test assembly.</span></span> <span data-ttu-id="eb966-145">多くの場合、アンロードは完了するまで待機する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="eb966-145">In many cases, it isn't necessary to wait for the unload completion.</span></span> <span data-ttu-id="eb966-146">しかしながら、アンロードが完了したことを認識できると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb966-146">However, there are cases where it's useful to know that the unload has finished.</span></span> <span data-ttu-id="eb966-147">たとえば、ディスクからカスタム `AssemblyLoadContext` にロードされたアセンブリ ファイルを削除したい場合などです。</span><span class="sxs-lookup"><span data-stu-id="eb966-147">For example, you may want to delete the assembly file that was loaded into the custom `AssemblyLoadContext` from disk.</span></span> <span data-ttu-id="eb966-148">このような場合、以下のコード スニペットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb966-148">In such a case, the following code snippet can be used.</span></span> <span data-ttu-id="eb966-149">ループ内で、GC をトリガーし、カスタム `AssemblyLoadContext` への弱い参照が、ターゲット オブジェクトが収集されたことを示す `null` に設定されるまでファイナライザーが待機します。</span><span class="sxs-lookup"><span data-stu-id="eb966-149">It triggers a GC and waits for pending finalizers in a loop until the weak reference to the custom `AssemblyLoadContext` is set to `null`, indicating the target object was collected.</span></span> <span data-ttu-id="eb966-150">ほとんどの場合、ループは 1 回だけ通る必要があることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="eb966-150">Note that in most cases, just one pass through the loop is required.</span></span> <span data-ttu-id="eb966-151">しかしながら、より複雑な場合、つまり `AssemblyLoadContext` で実行されるコードによって作成されるオブジェクトにファイナライザーが含まれている場合は、ループを複数回通ることが必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb966-151">However, for more complex cases where objects created by the code running in the `AssemblyLoadContext` have finalizers, more passes may be needed.</span></span>

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a><span data-ttu-id="eb966-152">アンロード イベント</span><span class="sxs-lookup"><span data-stu-id="eb966-152">The Unloading event</span></span>

<span data-ttu-id="eb966-153">アンロードの開始時に何らかのクリーンアップを実行するために、カスタム `AssemblyLoadContext` にロードされたコードが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="eb966-153">In some cases, it may be necessary for the code loaded into a custom `AssemblyLoadContext` to perform some cleanup when the unloading is initiated.</span></span> <span data-ttu-id="eb966-154">たとえば、スレッドの停止、一部の強力な GC ハンドルのクリーンアップなどが必要になる場合があります。このような場合、`Unloading` イベントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb966-154">For example, it may need to stop threads, clean up some strong GC handles, etc. The `Unloading` event can be used in such cases.</span></span> <span data-ttu-id="eb966-155">必要なクリーンアップを実行するハンドラーをこのイベントにフックすることができます。</span><span class="sxs-lookup"><span data-stu-id="eb966-155">A handler that performs the necessary cleanup can be hooked to this event.</span></span>

### <a name="troubleshoot-unloadability-issues"></a><span data-ttu-id="eb966-156">アンローダビリティ問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="eb966-156">Troubleshoot unloadability issues</span></span>

<span data-ttu-id="eb966-157">アンロードの協調的な性質のために、収集可能な `AssemblyLoadContext`の内容をキープ アライブしてアンロードを妨げている参照があることを忘れてしまいがちです。</span><span class="sxs-lookup"><span data-stu-id="eb966-157">Due to the cooperative nature of the unloading, it's easy to forget about references keeping the stuff in a collectible `AssemblyLoadContext` alive and preventing unload.</span></span> <span data-ttu-id="eb966-158">参照を保持できるものを以下に要約します (一部は明確ではありません)。</span><span class="sxs-lookup"><span data-stu-id="eb966-158">Here is a summary of things (some of them non-obvious) that can hold the references:</span></span>

- <span data-ttu-id="eb966-159">収集可能な `AssemblyLoadContext` の外部から保持され、スタック スロットまたはプロセッサ レジスタ (ユーザー コードで明示的に、または JIT で暗黙的に作成されるメソッド ローカル)、静的変数、または強い/固定の GC ハンドルに格納され、次のものを推移的に指す通常の参照。</span><span class="sxs-lookup"><span data-stu-id="eb966-159">Regular references held from outside of the collectible `AssemblyLoadContext`, stored in a stack slot or a processor register (method locals, either explicitly created by the user code or implicitly by the JIT), a static variable or a strong / pinning GC handle, and transitively pointing to:</span></span>
  - <span data-ttu-id="eb966-160">収集可能な `AssemblyLoadContext` に読み込まれたアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="eb966-160">An assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
  - <span data-ttu-id="eb966-161">このようなアセンブリ内の型。</span><span class="sxs-lookup"><span data-stu-id="eb966-161">A type from such an assembly.</span></span>
  - <span data-ttu-id="eb966-162">このようなアセンブリ内の型のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="eb966-162">An instance of a type from such an assembly.</span></span>
- <span data-ttu-id="eb966-163">収集可能な `AssemblyLoadContext` に読み込まれたアセンブリからコードを実行するスレッド。</span><span class="sxs-lookup"><span data-stu-id="eb966-163">Threads running code from an assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="eb966-164">収集可能な `AssemblyLoadContext` 内部で作成されたカスタムの収集不可能な `AssemblyLoadContext` 型のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="eb966-164">Instances of custom non-collectible `AssemblyLoadContext` types created inside of the collectible `AssemblyLoadContext`</span></span>
- <span data-ttu-id="eb966-165">コールバックがカスタムの `AssemblyLoadContext` 内のメソッドに設定された保留中の <xref:System.Threading.RegisteredWaitHandle> インスタンス。</span><span class="sxs-lookup"><span data-stu-id="eb966-165">Pending <xref:System.Threading.RegisteredWaitHandle> instances with callbacks set to methods in the custom `AssemblyLoadContext`</span></span>

<span data-ttu-id="eb966-166">オブジェクトをルーティングするスタック スロット/プロセッサ レジスタを見つけるためのヒント:</span><span class="sxs-lookup"><span data-stu-id="eb966-166">Hints to find stack slot / processor register rooting an object:</span></span>

- <span data-ttu-id="eb966-167">関数呼び出しの結果を別の関数に直接渡すと、ユーザーが作成したローカル変数がない場合でも、ルートが作成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb966-167">Passing function call results directly to another function may create a root even though there is no user-created local variable.</span></span>
- <span data-ttu-id="eb966-168">オブジェクトへの参照がメソッド内の任意の時点で使用可能だった場合、JIT により、現在の関数で必要な期間、スタック スロット/プロセッサ レジスタ内に参照を持することが決定される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb966-168">If a reference to an object was available at any point in a method, the JIT might have decided to keep the reference in a stack slot / processor register for as long as it wants in the current function.</span></span>

## <a name="debug-unloading-issues"></a><span data-ttu-id="eb966-169">アンロードに関する問題のデバッグ</span><span class="sxs-lookup"><span data-stu-id="eb966-169">Debug unloading issues</span></span>

<span data-ttu-id="eb966-170">アンロードに関する問題のデバッグは、面倒な場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb966-170">Debugging issues with unloading can be tedious.</span></span> <span data-ttu-id="eb966-171">何が `AssemblyLoadContext` を保持しているかはわからないが、アンロードが失敗する状況に陥ることがあります。</span><span class="sxs-lookup"><span data-stu-id="eb966-171">You can get into situations where you don't know what can be holding an `AssemblyLoadContext` alive, but the unload fails.</span></span>
<span data-ttu-id="eb966-172">最も役立つツールは、WinDbg (Unix では LLDB) と SOS プラグインです。</span><span class="sxs-lookup"><span data-stu-id="eb966-172">The best weapon to help with that is WinDbg (LLDB on Unix) with the SOS plugin.</span></span> <span data-ttu-id="eb966-173">特定の `AssemblyLoadContext` に属する `LoaderAllocator` をキープ アライブしているのが何かを突き止める必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb966-173">You need to find what's keeping a `LoaderAllocator` belonging to the specific `AssemblyLoadContext` alive.</span></span>
<span data-ttu-id="eb966-174">このプラグインを使用すると、GC ヒープ オブジェクト、その階層、およびルートを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="eb966-174">This plugin allows you to look at GC heap objects, their hierarchies, and roots.</span></span>
<span data-ttu-id="eb966-175">プラグインをデバッガーに読み込むには、次のコマンドをデバッガーのコマンド ラインに入力します。</span><span class="sxs-lookup"><span data-stu-id="eb966-175">To load the plugin into the debugger, enter the following command in the debugger command line:</span></span>

<span data-ttu-id="eb966-176">WinDbg の場合 (WinDbg では、.NET Core アプリケーションを中断すると、自動的に実行されるようです):</span><span class="sxs-lookup"><span data-stu-id="eb966-176">In WinDbg (it seems WinDbg does that automatically when breaking into .NET Core application):</span></span>

```console
.loadby sos coreclr
```

<span data-ttu-id="eb966-177">LLDB の場合:</span><span class="sxs-lookup"><span data-stu-id="eb966-177">In LLDB:</span></span>

```console
plugin load /path/to/libsosplugin.so
```

<span data-ttu-id="eb966-178">アンロードの問題が発生するプログラム例をデバッグしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="eb966-178">Let's try to debug an example program that has problems with unloading.</span></span> <span data-ttu-id="eb966-179">ソース コードの内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="eb966-179">Source code is included below.</span></span> <span data-ttu-id="eb966-180">WinDbg でこのプログラムを実行すると、このデバッガーでは、アンロードが成功したかどうかを確認しようとした直後で中断されます。</span><span class="sxs-lookup"><span data-stu-id="eb966-180">When you run it under WinDbg, the program breaks into the debugger right after attempting to check for the unload success.</span></span> <span data-ttu-id="eb966-181">この後、原因の究明を開始できます。</span><span class="sxs-lookup"><span data-stu-id="eb966-181">You can then start looking for the culprits.</span></span>

<span data-ttu-id="eb966-182">Unix で LLDB を使用してデバッグする場合は、次の例の SOS コマンドの前に `!` がないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eb966-182">Note that if you debug using LLDB on Unix, the SOS commands in the following examples don't have the `!` in front of them.</span></span>

```console
!dumpheap -type LoaderAllocator
```

<span data-ttu-id="eb966-183">このコマンドは、GC ヒープ内にあり、型名に `LoaderAllocator` を含むすべてのオブジェクトをダンプします。</span><span class="sxs-lookup"><span data-stu-id="eb966-183">This command dumps all objects with a type name containing `LoaderAllocator` that are in the GC heap.</span></span> <span data-ttu-id="eb966-184">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="eb966-184">Here is an example:</span></span>

```console
         Address               MT     Size
000002b78000ce40 00007ffadc93a288       48     
000002b78000ceb0 00007ffadc93a218       24     

Statistics:
              MT    Count    TotalSize Class Name
00007ffadc93a218        1           24 System.Reflection.LoaderAllocatorScout
00007ffadc93a288        1           48 System.Reflection.LoaderAllocator
Total 2 objects
```

<span data-ttu-id="eb966-185">次の例の "Statistics:" パーツで、`System.Reflection.LoaderAllocator` に属する `MT` (`MethodTable`) を確認します。これが、注目すべきオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="eb966-185">In the "Statistics:" part below, check the `MT` (`MethodTable`) belonging to the `System.Reflection.LoaderAllocator`, which is the object we care about.</span></span> <span data-ttu-id="eb966-186">最初にリストでこのエントリと `MT` が一致するエントリを見つけて、オブジェクト自体のアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="eb966-186">Then in the list at the beginning, find the entry with `MT` matching that one and get the address of the object itself.</span></span> <span data-ttu-id="eb966-187">この例では、"000002b78000ce40" です。</span><span class="sxs-lookup"><span data-stu-id="eb966-187">In our case, it is "000002b78000ce40"</span></span>

<span data-ttu-id="eb966-188">`LoaderAllocator` オブジェクトのアドレスがわかったので、別のコマンドを使用して GC ルートを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="eb966-188">Now that we know the address of the `LoaderAllocator` object, we can use another command to find its GC roots</span></span>

```console
!gcroot -all 0x000002b78000ce40 
```

<span data-ttu-id="eb966-189">このコマンドは、`LoaderAllocator` インスタンスが発生するオブジェクト参照のチェーンをダンプします。</span><span class="sxs-lookup"><span data-stu-id="eb966-189">This command dumps the chain of object references that lead to the `LoaderAllocator` instance.</span></span> <span data-ttu-id="eb966-190">リストはルートから始まります。ルートは、`LoaderAllocator` をキープ アライブしているエンティティであるため、デバッグしている問題の核心になります。</span><span class="sxs-lookup"><span data-stu-id="eb966-190">The list starts with the root, which is the entity that keeps our `LoaderAllocator` alive and thus is the core of the problem you're debugging.</span></span> <span data-ttu-id="eb966-191">ルートは、スタック スロット、プロセッサ レジスタ、GC ハンドル、または静的変数のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="eb966-191">The root can be a stack slot, a processor register, a GC handle, or a static variable.</span></span>

<span data-ttu-id="eb966-192">`gcroot` コマンドの出力例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eb966-192">Here is an example of the output of the `gcroot` command:</span></span>

```console
Thread 4ac:
    000000cf9499dd20 00007ffa7d0236bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
        rbp-20: 000000cf9499dd90
            ->  000002b78000d328 System.Reflection.RuntimeMethodInfo
            ->  000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
            ->  000002b78000d1d0 System.RuntimeType
            ->  000002b78000ce40 System.Reflection.LoaderAllocator

HandleTable:
    000002b7f8a81198 (strong handle)
    -> 000002b78000d948 test.Test
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

    000002b7f8a815f8 (pinned handle)
    -> 000002b790001038 System.Object[]
    -> 000002b78000d390 example.TestInfo
    -> 000002b78000d328 System.Reflection.RuntimeMethodInfo
    -> 000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
    -> 000002b78000d1d0 System.RuntimeType
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

Found 3 roots.
```

<span data-ttu-id="eb966-193">ここで、修正するために、ルートがどこにあるかを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb966-193">Now you need to figure out where the root is located so you can fix it.</span></span> <span data-ttu-id="eb966-194">最も簡単なケースは、ルートがスタック スロットまたはプロセッサ レジスタである場合です。</span><span class="sxs-lookup"><span data-stu-id="eb966-194">The easiest case is when the root is a stack slot or a processor register.</span></span> <span data-ttu-id="eb966-195">この場合、`gcroot` には、フレームにルートとその関数を実行するスレッドを含む関数の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb966-195">In that case, the `gcroot` shows you the name of the function whose frame contains the root and the thread executing that function.</span></span> <span data-ttu-id="eb966-196">難解なケースは、ルートが静的変数または GC ハンドルの場合です。</span><span class="sxs-lookup"><span data-stu-id="eb966-196">The difficult case is when the root is a static variable or a GC handle.</span></span> 

<span data-ttu-id="eb966-197">前述の例では、1 番目のルートは、アドレス `rbp-20` にある関数 `example.Program.Main(System.String[])` のフレームに格納されている `System.Reflection.RuntimeMethodInfo` 型のローカルです (`rbp` はプロセッサ レジスタ `rbp` で、-20 は、そのレジスタからの 16 進のオフセットです)。</span><span class="sxs-lookup"><span data-stu-id="eb966-197">In the previous example, the first root is a local of type `System.Reflection.RuntimeMethodInfo` stored in the frame of the function `example.Program.Main(System.String[])` at address `rbp-20` (`rbp` is the processor register `rbp` and -20 is a hexadecimal offset from that register).</span></span>

<span data-ttu-id="eb966-198">2 番目のルートは通常の (強い) `GCHandle` で、`test.Test` クラスのインスタンスへの参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="eb966-198">The second root is a normal (strong) `GCHandle` that holds a reference to an instance of the `test.Test` class.</span></span> 

<span data-ttu-id="eb966-199">3 番目のルートは、固定の `GCHandle` です。</span><span class="sxs-lookup"><span data-stu-id="eb966-199">The third root is a pinned `GCHandle`.</span></span> <span data-ttu-id="eb966-200">これは、実際には静的変数です。</span><span class="sxs-lookup"><span data-stu-id="eb966-200">This one is actually a static variable.</span></span> <span data-ttu-id="eb966-201">残念ながら、これを確認する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="eb966-201">Unfortunately, there is no way to tell.</span></span> <span data-ttu-id="eb966-202">参照型の静的変数は、内部のランタイム構造体内のマネージド オブジェクト配列に格納されます。</span><span class="sxs-lookup"><span data-stu-id="eb966-202">Statics for reference types are stored in a managed object array in internal runtime structures.</span></span>

<span data-ttu-id="eb966-203">`AssemblyLoadContext` のアンロードが妨げられる可能性のあるもう 1 つのケースは、スタック上の `AssemblyLoadContext` に読み込まれたアセンブリ内のメソッドのフレームがスレッドに含まれている場合です。</span><span class="sxs-lookup"><span data-stu-id="eb966-203">Another case that can prevent unloading of an `AssemblyLoadContext` is when a thread has a frame of a method from an assembly loaded into the `AssemblyLoadContext` on its stack.</span></span> <span data-ttu-id="eb966-204">すべてのスレッドのマネージド コール スタックをダンプすると、これを確認できます。</span><span class="sxs-lookup"><span data-stu-id="eb966-204">You can check that by dumping managed call stacks of all threads:</span></span>

```console
~*e !clrstack
```

<span data-ttu-id="eb966-205">コマンドは、"すべてのスレッドに `!clrstack` コマンドを適用する" ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="eb966-205">The command means "apply to all threads the `!clrstack` command".</span></span> <span data-ttu-id="eb966-206">このコマンドの出力例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eb966-206">The following is the output of that command for the example.</span></span> <span data-ttu-id="eb966-207">残念ながら、Unix の LLDB には、すべてのスレッドにコマンドを適用する方法がないため、手動でスレッドを切り替えて、`clrstack` コマンドを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb966-207">Unfortunately, LLDB on Unix doesn't have any way to apply a command to all threads, so you'll need to resort to manually switching threads and repeating the `clrstack` command.</span></span>
<span data-ttu-id="eb966-208">デバッガーで "マネージド スタックを調べることができません" と表示されたすべてのスレッドを無視します。</span><span class="sxs-lookup"><span data-stu-id="eb966-208">Ignore all threads where the debugger says "Unable to walk the managed stack."</span></span>

```console
OS Thread Id: 0x6ba8 (0)
        Child SP               IP Call Site
0000001fc697d5c8 00007ffb50d9de12 [HelperMethodFrame: 0000001fc697d5c8] System.Diagnostics.Debugger.BreakInternal()
0000001fc697d6d0 00007ffa864765fa System.Diagnostics.Debugger.Break()
0000001fc697d700 00007ffa864736bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
0000001fc697d998 00007ffae5fdc1e3 [GCFrame: 0000001fc697d998] 
0000001fc697df28 00007ffae5fdc1e3 [GCFrame: 0000001fc697df28] 
OS Thread Id: 0x2ae4 (1)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x61a4 (2)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x7fdc (3)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5390 (4)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5ec8 (5)
        Child SP               IP Call Site
0000001fc70ff6e0 00007ffb5437f6e4 [DebuggerU2MCatchHandlerFrame: 0000001fc70ff6e0] 
OS Thread Id: 0x4624 (6)
        Child SP               IP Call Site
GetFrameContext failed: 1
0000000000000000 0000000000000000 
OS Thread Id: 0x60bc (7)
        Child SP               IP Call Site
0000001fc727f158 00007ffb5437fce4 [HelperMethodFrame: 0000001fc727f158] System.Threading.Thread.SleepInternal(Int32)
0000001fc727f260 00007ffb37ea7c2b System.Threading.Thread.Sleep(Int32)
0000001fc727f290 00007ffa865005b3 test.Program.ThreadProc() [E:\unloadability\test\Program.cs @ 17]
0000001fc727f2c0 00007ffb37ea6a5b System.Threading.Thread.ThreadMain_ThreadStart()
0000001fc727f2f0 00007ffadbc4cbe3 System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object)
0000001fc727f568 00007ffae5fdc1e3 [GCFrame: 0000001fc727f568] 
0000001fc727f7f0 00007ffae5fdc1e3 [DebuggerU2MCatchHandlerFrame: 0000001fc727f7f0] 

```

<span data-ttu-id="eb966-209">ご覧のとおり、最後のスレッドには、`test.Program.ThreadProc()` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb966-209">As you can see, the last thread has `test.Program.ThreadProc()`.</span></span> <span data-ttu-id="eb966-210">これは、`AssemblyLoadContext` に読み込まれたアセンブリ内の関数であるため、これが `AssemblyLoadContext` をキープ アライブしています。</span><span class="sxs-lookup"><span data-stu-id="eb966-210">This is a function from the assembly loaded into the `AssemblyLoadContext`, and so it keeps the `AssemblyLoadContext` alive.</span></span>

## <a name="example-source-with-unloadability-issues"></a><span data-ttu-id="eb966-211">アンローダビリティの問題を発生するソース例</span><span class="sxs-lookup"><span data-stu-id="eb966-211">Example source with unloadability issues</span></span>

<span data-ttu-id="eb966-212">前述のデバッグ例では、次のコードが使用されています。</span><span class="sxs-lookup"><span data-stu-id="eb966-212">The following code is used in the previous debugging example.</span></span>

### <a name="main-testing-program"></a><span data-ttu-id="eb966-213">メインのテスト プログラム</span><span class="sxs-lookup"><span data-stu-id="eb966-213">Main testing program</span></span>

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a><span data-ttu-id="eb966-214">TestAssemblyLoadContext に読み込まれたプログラム</span><span class="sxs-lookup"><span data-stu-id="eb966-214">Program loaded into the TestAssemblyLoadContext</span></span>

<span data-ttu-id="eb966-215">次のコードは、メインのテスト プログラムで `ExecuteAndUnload` メソッドに渡された `test.dll` を表します。</span><span class="sxs-lookup"><span data-stu-id="eb966-215">The following code represents the `test.dll` passed to the `ExecuteAndUnload` method in the main testing program.</span></span>

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
