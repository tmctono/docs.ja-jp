---
title: 配列での foreach の使用 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: a22cb939370b38780881eca0d9585a14002c8250
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966412"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="19499-102">配列での foreach の使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="19499-102">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="19499-103">[foreach](../../language-reference/keywords/foreach-in.md) ステートメントでは、配列の要素の反復処理を、簡単かつ安全に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="19499-103">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="19499-104">1 次元配列の場合、`foreach` ステートメントは、インデックス 0 から始まりインデックス `Length - 1` で終わるインデックスの昇順で要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="19499-104">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

<span data-ttu-id="19499-105">多次元配列の場合、右端の次元のインデックスが最初に加算されていき、次にその左の次元、またその左、というような方法で各要素がトラバースされます。</span><span class="sxs-lookup"><span data-stu-id="19499-105">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

<span data-ttu-id="19499-106">ただし、多次元配列では、入れ子になった [for](../../language-reference/keywords/for.md) ループを使用した方が、配列要素を処理する順序をより厳密に制御できます。</span><span class="sxs-lookup"><span data-stu-id="19499-106">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="19499-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="19499-107">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="19499-108">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="19499-108">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="19499-109">配列</span><span class="sxs-lookup"><span data-stu-id="19499-109">Arrays</span></span>](index.md)
- [<span data-ttu-id="19499-110">1 次元配列</span><span class="sxs-lookup"><span data-stu-id="19499-110">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="19499-111">多次元配列</span><span class="sxs-lookup"><span data-stu-id="19499-111">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="19499-112">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="19499-112">Jagged Arrays</span></span>](jagged-arrays.md)
