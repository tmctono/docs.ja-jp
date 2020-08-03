---
title: 配列での foreach の使用 - C# プログラミング ガイド
description: C# で foreach ステートメントを使用すると、配列の要素が反復処理されます。 1 次元配列の場合、foreach によってインデックスの昇順で要素が処理されます。
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: d924a3ef3351cbb30b809a1542f35314ee721852
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474541"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="5ede6-104">配列での foreach の使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="5ede6-104">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="5ede6-105">[foreach](../../language-reference/keywords/foreach-in.md) ステートメントでは、配列の要素の反復処理を、簡単かつ安全に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5ede6-105">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="5ede6-106">1 次元配列の場合、`foreach` ステートメントは、インデックス 0 から始まりインデックス `Length - 1` で終わるインデックスの昇順で要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="5ede6-106">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

<span data-ttu-id="5ede6-107">多次元配列の場合、右端の次元のインデックスが最初に加算されていき、次にその左の次元、またその左、というような方法で各要素がトラバースされます。</span><span class="sxs-lookup"><span data-stu-id="5ede6-107">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

<span data-ttu-id="5ede6-108">ただし、多次元配列では、入れ子になった [for](../../language-reference/keywords/for.md) ループを使用した方が、配列要素を処理する順序をより厳密に制御できます。</span><span class="sxs-lookup"><span data-stu-id="5ede6-108">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ede6-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ede6-109">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="5ede6-110">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5ede6-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5ede6-111">配列</span><span class="sxs-lookup"><span data-stu-id="5ede6-111">Arrays</span></span>](index.md)
- [<span data-ttu-id="5ede6-112">1 次元配列</span><span class="sxs-lookup"><span data-stu-id="5ede6-112">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="5ede6-113">多次元配列</span><span class="sxs-lookup"><span data-stu-id="5ede6-113">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="5ede6-114">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="5ede6-114">Jagged Arrays</span></span>](jagged-arrays.md)
