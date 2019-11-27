---
title: '方法: 配列を並べ替える'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3fb9af8de0fc86075fdccd64506c855c1c720660
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351852"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="bcdc5-102">方法: Visual Basic で配列を並べ替える</span><span class="sxs-lookup"><span data-stu-id="bcdc5-102">How to: sort an array in Visual Basic</span></span>

<span data-ttu-id="bcdc5-103">この記事では、Visual Basic で文字列の配列を並べ替える方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="bcdc5-103">This article shows an example of how to sort an array of strings in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="bcdc5-104">例</span><span class="sxs-lookup"><span data-stu-id="bcdc5-104">Example</span></span>

<span data-ttu-id="bcdc5-105">この例では、`zooAnimals`という名前の `String` オブジェクトの配列を宣言し、それを設定して、アルファベット順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="bcdc5-105">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span></span>
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a><span data-ttu-id="bcdc5-106">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="bcdc5-106">Robust programming</span></span>

<span data-ttu-id="bcdc5-107">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bcdc5-107">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="bcdc5-108">配列が空です (<xref:System.ArgumentNullException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="bcdc5-108">Array is empty (<xref:System.ArgumentNullException> class).</span></span>
- <span data-ttu-id="bcdc5-109">配列は多次元 (<xref:System.RankException> クラス) です。</span><span class="sxs-lookup"><span data-stu-id="bcdc5-109">Array is multidimensional (<xref:System.RankException> class).</span></span>
- <span data-ttu-id="bcdc5-110">配列の1つ以上の要素が <xref:System.IComparable> インターフェイス (<xref:System.InvalidOperationException> クラス) を実装していません。</span><span class="sxs-lookup"><span data-stu-id="bcdc5-110">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="bcdc5-111">参照</span><span class="sxs-lookup"><span data-stu-id="bcdc5-111">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bcdc5-112">配列</span><span class="sxs-lookup"><span data-stu-id="bcdc5-112">Arrays</span></span>](index.md)
- [<span data-ttu-id="bcdc5-113">配列のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bcdc5-113">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="bcdc5-114">コレクション</span><span class="sxs-lookup"><span data-stu-id="bcdc5-114">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="bcdc5-115">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="bcdc5-115">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)
