---
title: ジェネリック型 (ジェネリック) の概要
description: 実際のデータ型をいじらずにタイプ セーフなデータ構造を定義できるコード テンプレートとしてジェネリックがどのように機能するかを説明します。
author: kuhlenh
ms.author: wiwagn
ms.date: 10/09/2018
ms.openlocfilehash: 3c1181f5be717f328ae906c6009fc8a34b904c89
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "61923852"
---
# <a name="generic-types-overview"></a><span data-ttu-id="eae82-103">ジェネリック型の概要</span><span class="sxs-lookup"><span data-stu-id="eae82-103">Generic types overview</span></span>

<span data-ttu-id="eae82-104">開発者は、暗黙的か明示的かに関わらず、.NET では常にジェネリックを使用します。</span><span class="sxs-lookup"><span data-stu-id="eae82-104">Developers use generics all the time in .NET, whether implicitly or explicitly.</span></span> <span data-ttu-id="eae82-105">.NET で LINQ を使用していると、<xref:System.Collections.Generic.IEnumerable%601> を操作することがあります。</span><span class="sxs-lookup"><span data-stu-id="eae82-105">When you use LINQ in .NET, did you ever notice that you're working with <xref:System.Collections.Generic.IEnumerable%601>?</span></span> <span data-ttu-id="eae82-106">または、Entity Framework を使用してデータベースと通信するための "汎用リポジトリ" のオンライン サンプルでは、ほとんどのメソッドが IQueryable\<T> を返すことに気付きます。</span><span class="sxs-lookup"><span data-stu-id="eae82-106">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return IQueryable\<T>?</span></span> <span data-ttu-id="eae82-107">これらの例の **T** とは何で、なぜそこにあるのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="eae82-107">You may have wondered what the **T** is in these examples and why it's in there.</span></span>

<span data-ttu-id="eae82-108">**ジェネリック**は、.NET Framework 2.0 で導入され、本質的に "コード テンプレート" であり、開発者は実際のデータ型をいじらずに[タイプ セーフな](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100))データ構造を定義できます。</span><span class="sxs-lookup"><span data-stu-id="eae82-108">First introduced in the .NET Framework 2.0, **generics** are essentially a "code template" that allows developers to define [type-safe](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) data structures without committing to an actual data type.</span></span> <span data-ttu-id="eae82-109">たとえば、<xref:System.Collections.Generic.List%601> は[ジェネリック コレクション](xref:System.Collections.Generic)であり、`List<int>`、`List<string>`、`List<Person>` などの任意の型で宣言および使用できます。</span><span class="sxs-lookup"><span data-stu-id="eae82-109">For example, <xref:System.Collections.Generic.List%601> is a [generic collection](xref:System.Collections.Generic) that can be declared and used with any type, such as `List<int>`, `List<string>`, or `List<Person>`.</span></span>

<span data-ttu-id="eae82-110">ジェネリックが便利な理由を理解するために、ジェネリックを追加する前と後の特定のクラス <xref:System.Collections.ArrayList> を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="eae82-110">To understand why generics are useful, let's take a look at a specific class before and after adding generics: <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="eae82-111">.NET Framework 1.0 で、`ArrayList` 要素の型は <xref:System.Object> です。</span><span class="sxs-lookup"><span data-stu-id="eae82-111">In .NET Framework 1.0, the `ArrayList` elements were of type <xref:System.Object>.</span></span> <span data-ttu-id="eae82-112">これは、追加されたすべての要素は自動的に `Object` に変換されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="eae82-112">This meant that any element added was silently converted into an `Object`.</span></span> <span data-ttu-id="eae82-113">リストから要素を読み取るときも同じことが起こります。</span><span class="sxs-lookup"><span data-stu-id="eae82-113">The same would happen when reading the elements from the list.</span></span> <span data-ttu-id="eae82-114">このプロセスは[ボックス化とボックス化解除](../csharp/programming-guide/types/boxing-and-unboxing.md)と呼ばれ、パフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="eae82-114">This process is known as [boxing and unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md), and it impacts performance.</span></span> <span data-ttu-id="eae82-115">ただし、それだけでなく、コンパイル時にリスト内のデータの型を判断する方法がありません。</span><span class="sxs-lookup"><span data-stu-id="eae82-115">More than that, however, there's no way to determine the type of data in the list at compile time.</span></span> <span data-ttu-id="eae82-116">これは脆弱なコードを助長します。</span><span class="sxs-lookup"><span data-stu-id="eae82-116">This makes for some fragile code.</span></span> <span data-ttu-id="eae82-117">ジェネリックは、リストの各インスタンスに含まれるデータの型を定義することで、この問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="eae82-117">Generics solve this problem by defining the type of data each instance of list will contain.</span></span> <span data-ttu-id="eae82-118">たとえば、`List<int>` には整数だけを追加でき、`List<Person>` には Persons だけを追加できます。</span><span class="sxs-lookup"><span data-stu-id="eae82-118">For example, you can only add integers to `List<int>` and only add Persons to `List<Person>`.</span></span>

<span data-ttu-id="eae82-119">ジェネリックは、実行時にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="eae82-119">Generics are also available at runtime.</span></span> <span data-ttu-id="eae82-120">これは、使用されているデータ構造の型をランタイムが認識し、より効率的メモリに格納できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="eae82-120">This means the runtime knows what type of data structure you're using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="eae82-121">実行時にデータ構造の型がわかるといかに効率的かということを示す小さなプログラムの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eae82-121">The following example is a small program that illustrates the efficiency of knowing the data structure type at runtime:</span></span>

```csharp
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }
```

<span data-ttu-id="eae82-122">このプログラムで、次のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="eae82-122">This program produces output similar to the following:</span></span>

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

<span data-ttu-id="eae82-123">最初にわかるのは、非ジェネリック リストよりジェネリック リストの方が並べ替えがはるかに高速であるということです。</span><span class="sxs-lookup"><span data-stu-id="eae82-123">The first thing you can notice here is that sorting the generic list is significantly faster than sorting the non-generic list.</span></span> <span data-ttu-id="eae82-124">また、ジェネリック リストの型が具体的 ([System.Int32]) であるのに対して、非ジェネリック リストの型は一般的であることもわかります。</span><span class="sxs-lookup"><span data-stu-id="eae82-124">You might also notice that the type for the generic list is distinct ([System.Int32]), whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="eae82-125">ジェネリック `List<int>` の場合はランタイムはそれを <xref:System.Int32> 型と認識してメモリの整数配列にリストの要素を格納できるのに対し、非ジェネリック `ArrayList` の場合はオブジェクトに対して各リスト要素をキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae82-125">Because the runtime knows the generic `List<int>` is of type <xref:System.Int32>, it can store the list elements in an underlying integer array in memory while the non-generic `ArrayList` has to cast each list element to an object.</span></span> <span data-ttu-id="eae82-126">この例で示すように、余分なキャストに時間がかかり、リストの並べ替え速度が低下します。</span><span class="sxs-lookup"><span data-stu-id="eae82-126">As this example shows, the extra casts take up time and slow down the list sort.</span></span>

<span data-ttu-id="eae82-127">ジェネリックの型をランタイムが認識することのもう 1 つの利点は、デバッグ エクスペリエンスの向上です。</span><span class="sxs-lookup"><span data-stu-id="eae82-127">An additional advantage of the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="eae82-128">C# でジェネリックをデバッグすると、データ構造内の各要素の型がわかります。</span><span class="sxs-lookup"><span data-stu-id="eae82-128">When you're debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="eae82-129">ジェネリックでない場合は、各要素の型を知ることはできません。</span><span class="sxs-lookup"><span data-stu-id="eae82-129">Without generics, you would have no idea what type each element was.</span></span>

## <a name="see-also"></a><span data-ttu-id="eae82-130">参照</span><span class="sxs-lookup"><span data-stu-id="eae82-130">See also</span></span>

- [<span data-ttu-id="eae82-131">ジェネリック (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="eae82-131">C# Programming Guide - Generics</span></span>](../../docs/csharp/programming-guide/generics/index.md)
