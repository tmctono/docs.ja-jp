---
title: '方法: Visual Basic での配列の並べ替え'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 467d1bcce6bda2feb5a8e59c152cb292d753e79b
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700974"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="3a70b-102">方法: Visual Basic で配列を並べ替える</span><span class="sxs-lookup"><span data-stu-id="3a70b-102">How to: sort an array in Visual Basic</span></span>

<span data-ttu-id="3a70b-103">この記事では、Visual Basic で文字列の配列を並べ替える方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="3a70b-103">This article shows an example of how to sort an array of strings in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="3a70b-104">例</span><span class="sxs-lookup"><span data-stu-id="3a70b-104">Example</span></span>

<span data-ttu-id="3a70b-105">この例では、`zooAnimals` という名前の @no__t 0 オブジェクトの配列を宣言し、それを設定して、アルファベット順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="3a70b-105">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span></span>
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a><span data-ttu-id="3a70b-106">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="3a70b-106">Robust programming</span></span>

<span data-ttu-id="3a70b-107">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a70b-107">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="3a70b-108">配列が空です (<xref:System.ArgumentNullException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="3a70b-108">Array is empty (<xref:System.ArgumentNullException> class).</span></span>
- <span data-ttu-id="3a70b-109">配列は多次元 (<xref:System.RankException> クラス) です。</span><span class="sxs-lookup"><span data-stu-id="3a70b-109">Array is multidimensional (<xref:System.RankException> class).</span></span>
- <span data-ttu-id="3a70b-110">配列の1つ以上の要素が <xref:System.IComparable> インターフェイス (<xref:System.InvalidOperationException> クラス) を実装していません。</span><span class="sxs-lookup"><span data-stu-id="3a70b-110">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="3a70b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a70b-111">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3a70b-112">配列</span><span class="sxs-lookup"><span data-stu-id="3a70b-112">Arrays</span></span>](index.md)
- [<span data-ttu-id="3a70b-113">配列のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3a70b-113">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="3a70b-114">コレクション</span><span class="sxs-lookup"><span data-stu-id="3a70b-114">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="3a70b-115">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="3a70b-115">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)
