---
title: openGenericCERCall MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- open generic CER calls
- constrained execution regions
- openGenericCERCall MDA
- CER calls
- managed debugging assistants (MDAs), CER calls
- generics [.NET Framework], open generic CER calls
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
ms.openlocfilehash: 7492a4c0547680a6ace85a5f7c98567770f5575a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181775"
---
# <a name="opengenericcercall-mda"></a><span data-ttu-id="9b839-102">openGenericCERCall MDA</span><span class="sxs-lookup"><span data-stu-id="9b839-102">openGenericCERCall MDA</span></span>

<span data-ttu-id="9b839-103">`openGenericCERCall` マネージド デバッグ アシスタントは、ルート メソッドにジェネリック型変数を持つ制約された実行領域 (CER) グラフが JIT コンパイル時またはネイティブ イメージ生成時に処理されている場合に、少なくとも 1 つのジェネリック型変数がオブジェクト参照型であることを警告するためにアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="9b839-103">The `openGenericCERCall` managed debugging assistant is activated to warn that a constrained execution region (CER) graph with generic type variables at the root method is being processed at JIT-compilation or native image generation time and at least one of the generic type variables is an object reference type.</span></span>

## <a name="symptoms"></a><span data-ttu-id="9b839-104">現象</span><span class="sxs-lookup"><span data-stu-id="9b839-104">Symptoms</span></span>

<span data-ttu-id="9b839-105">スレッドが中止されたとき、またはアプリケーション ドメインがアンロードされたときに CER コードが実行されません。</span><span class="sxs-lookup"><span data-stu-id="9b839-105">CER code does not run when a thread is aborted or when an application domain is unloaded.</span></span>

## <a name="cause"></a><span data-ttu-id="9b839-106">原因</span><span class="sxs-lookup"><span data-stu-id="9b839-106">Cause</span></span>

<span data-ttu-id="9b839-107">JIT コンパイル時には、処理結果のコードが共有され、オブジェクト参照型変数がそれぞれ任意のオブジェクト参照型になる可能性があるため、オブジェクト参照型を含むインスタンス化は代理にすぎません。</span><span class="sxs-lookup"><span data-stu-id="9b839-107">At JIT-compilation time, an instantiation containing an object reference type is only representative because the resultant code is shared, and each of the object reference type variables might be any object reference type.</span></span> <span data-ttu-id="9b839-108">このため、一部のランタイム リソースを前もって準備することが妨げられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9b839-108">This can prevent the preparation of some run-time resources ahead of time.</span></span>

<span data-ttu-id="9b839-109">特に、ジェネリック型変数を含むメソッドは、バックグラウンドでリソースを遅延割り当てする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9b839-109">In particular, methods with generic type variables can lazily allocate resources in the background.</span></span> <span data-ttu-id="9b839-110">このようなメソッドは、ジェネリック辞書エントリと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9b839-110">These are referred to as generic dictionary entries.</span></span> <span data-ttu-id="9b839-111">たとえば、ジェネリック型変数である`List<T> list = new List<T>();``T`ステートメントの場合、ランタイムは実行時に正確なインスタンス化`List<Object>, List<String>`を作成する必要があります( など)。</span><span class="sxs-lookup"><span data-stu-id="9b839-111">For instance, for the statement `List<T> list = new List<T>();` where `T` is a generic type variable the runtime must look up and possibly create the exact instantiation at run time, for example, `List<Object>, List<String>`, and so forth.</span></span> <span data-ttu-id="9b839-112">この操作は、メモリ不足など、開発者が制御できないさまざまな理由で失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="9b839-112">This can fail for a variety of reasons beyond the developer's control, such as running out of memory.</span></span>

<span data-ttu-id="9b839-113">この MDA は、JIT コンパイル時にのみアクティブになり、正確なインスタンス化が存在するときにはアクティブになりません。</span><span class="sxs-lookup"><span data-stu-id="9b839-113">This MDA should only be activated at JIT-compilation time, not when there is an exact instantiation.</span></span>

<span data-ttu-id="9b839-114">この MDA がアクティブになるとき、正しくないインスタンス化に対して CER が機能しないという症状が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9b839-114">When this MDA is activated, the likely symptoms are that CERs are not functional for the bad instantiations.</span></span> <span data-ttu-id="9b839-115">実際、MDA がアクティブになる状況下では、ランタイムは CER の実装を試みません。</span><span class="sxs-lookup"><span data-stu-id="9b839-115">In fact, the runtime has not attempted to implement a CER under the circumstances that caused the MDA to be activated.</span></span> <span data-ttu-id="9b839-116">そのため、開発者が CER の共有インスタンス化を使用している場合、目的の CER の領域内で発生した JIT コンパイル エラー、ジェネリック型の読み込みエラー、スレッドの中止などはキャッチされません。</span><span class="sxs-lookup"><span data-stu-id="9b839-116">So if the developer uses a shared instantiation of the CER, then JIT-compilation errors, generics type loading errors, or thread aborts within the region of the intended CER are not caught.</span></span>

## <a name="resolution"></a><span data-ttu-id="9b839-117">解決策</span><span class="sxs-lookup"><span data-stu-id="9b839-117">Resolution</span></span>

<span data-ttu-id="9b839-118">CER が存在する可能性があるメソッドには、オブジェクト参照型であるジェネリック型変数を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9b839-118">Do not use generic type variables that are of object reference type for methods that may contain a CER.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="9b839-119">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="9b839-119">Effect on the Runtime</span></span>

<span data-ttu-id="9b839-120">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="9b839-120">This MDA has no effect on the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="9b839-121">Output</span><span class="sxs-lookup"><span data-stu-id="9b839-121">Output</span></span>

<span data-ttu-id="9b839-122">この MDA からの出力例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9b839-122">The following is a sample of output from this MDA:</span></span>
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution.
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a><span data-ttu-id="9b839-123">構成</span><span class="sxs-lookup"><span data-stu-id="9b839-123">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a><span data-ttu-id="9b839-124">例</span><span class="sxs-lookup"><span data-stu-id="9b839-124">Example</span></span>

<span data-ttu-id="9b839-125">CER コードは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9b839-125">The CER code is not executed.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Runtime.CompilerServices;

class Program
{
    static void Main(string[] args)
    {
        CallGenericMethods();
    }
    static void CallGenericMethods()
    {
        // This call is correct. The instantiation of the method
        // contains only nonreference types.
        MyClass.GenericMethodWithCer<int>();

        // This call is incorrect. A shared version of the method that
        // cannot be completely analyzed will be JIT-compiled. The
        // MDA will be activated at JIT-compile time, not at run time.
        MyClass.GenericMethodWithCer<String>();
    }
}

class MyClass
{
    public static void GenericMethodWithCer<T>()
    {
        RuntimeHelpers.PrepareConstrainedRegions();
        try
        {

        }
        finally
        {
            // This is the start of the CER.
            Console.WriteLine("In finally block.");
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="9b839-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b839-126">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [<span data-ttu-id="9b839-127">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="9b839-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
