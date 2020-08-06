---
title: コンパイラにより生成された例外 - C# プログラミング ガイド
description: コンパイラにより生成された例外について説明します。 自動的にスローされる例外とそのエラー条件の一覧を確認します。
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 1def83f72e83976ac672ec35169b4950a20ef54e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302062"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="bf048-104">コンパイラにより生成された例外 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="bf048-104">Compiler-Generated Exceptions (C# Programming Guide)</span></span>

<span data-ttu-id="bf048-105">一部の例外は、基本操作が失敗した場合に .NET ランタイムによって自動的にスローされます。</span><span class="sxs-lookup"><span data-stu-id="bf048-105">Some exceptions are thrown automatically by the .NET runtime when basic operations fail.</span></span> <span data-ttu-id="bf048-106">次の表には、これらの例外とそのエラー条件が一覧で示されています。</span><span class="sxs-lookup"><span data-stu-id="bf048-106">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="bf048-107">例外</span><span class="sxs-lookup"><span data-stu-id="bf048-107">Exception</span></span>|<span data-ttu-id="bf048-108">説明</span><span class="sxs-lookup"><span data-stu-id="bf048-108">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="bf048-109">算術演算中に発生する例外 (<xref:System.DivideByZeroException>、<xref:System.OverflowException> など) の基底クラスです。</span><span class="sxs-lookup"><span data-stu-id="bf048-109">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="bf048-110">要素の実際の型が配列の実際の型に適合していないことが原因で、指定された要素を配列に格納できない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="bf048-110">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="bf048-111">整数値のゼロ除算が試行されたときにスローされます。</span><span class="sxs-lookup"><span data-stu-id="bf048-111">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="bf048-112">インデックスがゼロよりも小さい場合またはインデックスが配列の境界外にある場合に、配列のインデックス作成が試行されたときにスローされます。</span><span class="sxs-lookup"><span data-stu-id="bf048-112">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="bf048-113">基本データ型からインターフェイスまたは派生型への明示的な変換が実行時に失敗したときにスローされます。</span><span class="sxs-lookup"><span data-stu-id="bf048-113">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="bf048-114">値が [null](../../language-reference/keywords/null.md) であるオブジェクトを参照しようとするとスローされます。</span><span class="sxs-lookup"><span data-stu-id="bf048-114">Thrown when an attempt is made to reference an object whose value is [null](../../language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="bf048-115">[new](../../language-reference/operators/new-operator.md) 演算子を使用したメモリの割り当てに失敗するとスローされます。</span><span class="sxs-lookup"><span data-stu-id="bf048-115">Thrown when an attempt to allocate memory using the [new](../../language-reference/operators/new-operator.md) operator fails.</span></span> <span data-ttu-id="bf048-116">これは、共通言語ランタイムで使用できるメモリが足りなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="bf048-116">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="bf048-117">`checked` コンテキストで算術演算がオーバーフローしたときにスローされます。</span><span class="sxs-lookup"><span data-stu-id="bf048-117">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="bf048-118">保留中のメソッド呼び出しが多すぎることが原因で実行スタックが不足したときにスローされます。通常は、非常に深い再帰か無限再帰があることを示します。</span><span class="sxs-lookup"><span data-stu-id="bf048-118">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="bf048-119">静的コンストラクターが例外をスローし、その例外をキャッチするための対応する `catch` 句がない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="bf048-119">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf048-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf048-120">See also</span></span>

- [<span data-ttu-id="bf048-121">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="bf048-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bf048-122">例外と例外処理</span><span class="sxs-lookup"><span data-stu-id="bf048-122">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="bf048-123">例外処理</span><span class="sxs-lookup"><span data-stu-id="bf048-123">Exception Handling</span></span>](./exception-handling.md)
- [<span data-ttu-id="bf048-124">try-catch</span><span class="sxs-lookup"><span data-stu-id="bf048-124">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="bf048-125">try-finally</span><span class="sxs-lookup"><span data-stu-id="bf048-125">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="bf048-126">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="bf048-126">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
