---
title: ファイナライザー - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 10/08/2018
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
ms.openlocfilehash: 9936d56582afd160bf3464d18efd3acf47c7af60
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924494"
---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="0db64-102">ファイナライザー (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="0db64-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="0db64-103">ガベージ コレクターによってクラス インスタンスが収集されている場合は、ファイナライザー (**デストラクター**とも呼ばれます) を使用して、最終的に必要なすべてのクリーンアップが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0db64-103">Finalizers (which are also called **destructors**) are used to perform any necessary final clean-up when a class instance is being collected by the garbage collector.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0db64-104">解説</span><span class="sxs-lookup"><span data-stu-id="0db64-104">Remarks</span></span>  
  
- <span data-ttu-id="0db64-105">ファイナライザーは、構造体には定義できません。</span><span class="sxs-lookup"><span data-stu-id="0db64-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="0db64-106">クラスでだけ使用します。</span><span class="sxs-lookup"><span data-stu-id="0db64-106">They are only used with classes.</span></span>  
  
- <span data-ttu-id="0db64-107">クラスで使用できるファイナライザーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="0db64-107">A class can only have one finalizer.</span></span>  
  
- <span data-ttu-id="0db64-108">ファイナライザーを継承またはオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0db64-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
- <span data-ttu-id="0db64-109">ファイナライザーを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="0db64-109">Finalizers cannot be called.</span></span> <span data-ttu-id="0db64-110">デストラクターは自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="0db64-110">They are invoked automatically.</span></span>  
  
- <span data-ttu-id="0db64-111">ファイナライザーは修飾子を取らず、パラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="0db64-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="0db64-112">たとえば、次はクラス `Car` に対するファイナライザーの宣言です。</span><span class="sxs-lookup"><span data-stu-id="0db64-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 [!code-csharp[csProgGuideObjects#86](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#86)]  

<span data-ttu-id="0db64-113">ファイナライザーは、式本体の定義として実行することもできます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0db64-113">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 <span data-ttu-id="0db64-114">ファイナライザーは、オブジェクトの基底クラスで <xref:System.Object.Finalize%2A> を暗黙的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0db64-114">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="0db64-115">そのため、ファイナライザーの呼び出しは、暗黙的に次のコードに解釈されます。</span><span class="sxs-lookup"><span data-stu-id="0db64-115">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
```csharp  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 <span data-ttu-id="0db64-116">つまり、派生が最も多いクラスから派生が最も少ないクラスまで、継承チェーンのすべてのインスタンスに対して、`Finalize` メソッドが再帰的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0db64-116">This means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0db64-117">空のファイナライザーは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="0db64-117">Empty finalizers should not be used.</span></span> <span data-ttu-id="0db64-118">ファイナライザーがクラスに存在するときは、エントリが `Finalize` キューで作成されます。</span><span class="sxs-lookup"><span data-stu-id="0db64-118">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="0db64-119">ファイナライザーを呼び出すと、ガベージ コレクターが呼び出され、このキューを処理します。</span><span class="sxs-lookup"><span data-stu-id="0db64-119">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="0db64-120">ファイナライザーが空の場合、パフォーマンスを不必要に低下させるだけです。</span><span class="sxs-lookup"><span data-stu-id="0db64-120">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="0db64-121">ファイナライザーがいつ呼び出されるかはガベージ コレクターによって決定されるため、プログラマは制御できません。</span><span class="sxs-lookup"><span data-stu-id="0db64-121">The programmer has no control over when the finalizer is called because this is determined by the garbage collector.</span></span> <span data-ttu-id="0db64-122">ガベージ コレクターは、アプリケーションが使用していないオブジェクトをチェックします。</span><span class="sxs-lookup"><span data-stu-id="0db64-122">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="0db64-123">終了処理が可能なオブジェクトと考えられる場合、ファイナライザー (存在する場合) を呼び出し、オブジェクトの格納に使用されているメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="0db64-123">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span> 
 
 <span data-ttu-id="0db64-124">(.NET Core アプリケーションではなく) .NET Framework アプリケーションでは、プログラムが存在する場合、ファイナライザーも呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0db64-124">In .NET Framework applications (but not in .NET Core applications), finalizers are also called when the program exits.</span></span> 
  
 <span data-ttu-id="0db64-125"><xref:System.GC.Collect%2A> を呼び出すことによって、ガベージ コレクションを強制的に行うことができます。ただし、パフォーマンスに問題が発生する可能性があるため、通常はこの処理を避けます。</span><span class="sxs-lookup"><span data-stu-id="0db64-125">It is possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="0db64-126">ファイナライザーを使ったリソースの解放</span><span class="sxs-lookup"><span data-stu-id="0db64-126">Using finalizers to release resources</span></span>  
 <span data-ttu-id="0db64-127">一般に C# では、ガベージ コレクションでランタイムにターゲットを設定しない言語で開発する場合ほど、メモリ管理を必要としません。</span><span class="sxs-lookup"><span data-stu-id="0db64-127">In general, C# does not require as much memory management as is needed when you develop with a language that does not target a runtime with garbage collection.</span></span> <span data-ttu-id="0db64-128">.NET Framework のガベージ コレクターが、オブジェクトに対するメモリの割り当てと解放を暗黙的に管理するからです。</span><span class="sxs-lookup"><span data-stu-id="0db64-128">This is because the .NET Framework garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="0db64-129">ただし、ウィンドウ、ファイル、ネットワーク接続などのアンマネージ リソースをアプリケーションでカプセル化するとき、ファイナライザーを使ってこれらのリソースを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0db64-129">However, when your application encapsulates unmanaged resources such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="0db64-130">終了処理が可能なオブジェクトの場合、ガベージ コレクターはそのオブジェクトの `Finalize` メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0db64-130">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>  
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="0db64-131">リソースの明示的な解放</span><span class="sxs-lookup"><span data-stu-id="0db64-131">Explicit release of resources</span></span>  
 <span data-ttu-id="0db64-132">アプリケーションで高額な外部リソースを使用している場合、ガベージ コレクターがオブジェクトを解放する前にリソースを明示的に解放する手段を用意することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="0db64-132">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="0db64-133">この処理を行うには、オブジェクトに対して必要なクリーンアップを実行する `Dispose` メソッドを <xref:System.IDisposable> インターフェイスから実装します。</span><span class="sxs-lookup"><span data-stu-id="0db64-133">You do this by implementing a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="0db64-134">これによって、アプリケーションのパフォーマンスを大幅に向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="0db64-134">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="0db64-135">このようにリソースを明示的に制御する場合でも、ファイナライザーは、`Dispose` メソッドの呼び出しが失敗したときにリソースをクリーンアップするための安全装置になります。</span><span class="sxs-lookup"><span data-stu-id="0db64-135">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method failed.</span></span>  
  
 <span data-ttu-id="0db64-136">リソースのクリーンアップの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0db64-136">For more details about cleaning up resources, see the following topics:</span></span>  
  
- [<span data-ttu-id="0db64-137">アンマネージ リソースのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="0db64-137">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
- [<span data-ttu-id="0db64-138">Dispose メソッドの実装</span><span class="sxs-lookup"><span data-stu-id="0db64-138">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
- [<span data-ttu-id="0db64-139">using ステートメント</span><span class="sxs-lookup"><span data-stu-id="0db64-139">using Statement</span></span>](../../language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="0db64-140">例</span><span class="sxs-lookup"><span data-stu-id="0db64-140">Example</span></span>  
 <span data-ttu-id="0db64-141">次の例では、継承チェーンを形成する 3 つのクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0db64-141">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="0db64-142">`First` が基底クラスであり、`Second` は `First` から派生し、`Third` は `Second` から派生します。</span><span class="sxs-lookup"><span data-stu-id="0db64-142">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="0db64-143">3 つのクラスのいずれにもファイナライザーがあります。</span><span class="sxs-lookup"><span data-stu-id="0db64-143">All three have finalizers.</span></span> <span data-ttu-id="0db64-144">`Main` では、派生が最も多いクラスのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0db64-144">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="0db64-145">プログラムを実行すると、3 つのクラスのファイナライザーが派生が最も多いクラスから派生が最も少ないクラスの順に自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0db64-145">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 [!code-csharp[csProgGuideObjects#85](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#85)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0db64-146">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="0db64-146">C# language specification</span></span>  

<span data-ttu-id="0db64-147">詳細については、「[C# 言語仕様](../../language-reference/language-specification/index.md)」の [デストラクタ―](~/_csharplang/spec/classes.md#destructors)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0db64-147">For more information, see the [Destructors](~/_csharplang/spec/classes.md#destructors) section of the [C# language specification](../../language-reference/language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0db64-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="0db64-148">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="0db64-149">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0db64-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0db64-150">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="0db64-150">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="0db64-151">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="0db64-151">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
