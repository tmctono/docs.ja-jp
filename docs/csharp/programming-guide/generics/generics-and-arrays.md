---
title: ジェネリックと配列 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: a8fad38fac07b9e8d51529d3ab7070328a333dbb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75703014"
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="3958e-102">ジェネリックと配列 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="3958e-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="3958e-103">C# 2.0 以降、下限が 0 の一次元配列は自動的に <xref:System.Collections.Generic.IList%601> を実装します。</span><span class="sxs-lookup"><span data-stu-id="3958e-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="3958e-104">これにより、同じコードで配列や他のコレクション型を反復処理できるジェネリック メソッドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3958e-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="3958e-105">この手法は主に、コレクションのデータを読み込むときに便利です。</span><span class="sxs-lookup"><span data-stu-id="3958e-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="3958e-106"><xref:System.Collections.Generic.IList%601> インターフェイスを使用して配列の要素を追加したり、削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3958e-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="3958e-107">このコンテキストの配列で、<xref:System.Collections.Generic.IList%601> のような、<xref:System.Collections.Generic.IList%601.RemoveAt%2A> メソッドを呼び出そうとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3958e-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="3958e-108">次のコード例からは、<xref:System.Collections.Generic.IList%601> 入力パラメーターを受け取る単一のジェネリック メソッドがリストと配列 (この例では、整数の配列) の両方を反復処理できることがわかります。</span><span class="sxs-lookup"><span data-stu-id="3958e-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a><span data-ttu-id="3958e-109">参照</span><span class="sxs-lookup"><span data-stu-id="3958e-109">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="3958e-110">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="3958e-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3958e-111">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="3958e-111">Generics</span></span>](./index.md)
- [<span data-ttu-id="3958e-112">配列</span><span class="sxs-lookup"><span data-stu-id="3958e-112">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="3958e-113">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="3958e-113">Generics</span></span>](../../../standard/generics/index.md)
