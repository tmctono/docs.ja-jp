---
title: '方法: Visual Basic で配列を並べ替える'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3c701d1b65d31315ba931cca729e465ba7d766b5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620872"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="992e8-102">方法: Visual Basic で配列を並べ替える</span><span class="sxs-lookup"><span data-stu-id="992e8-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="992e8-103">この例の配列を宣言する`String`という名前のオブジェクト`zooAnimals`、それを設定し、アルファベット順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="992e8-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="992e8-104">例</span><span class="sxs-lookup"><span data-stu-id="992e8-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="992e8-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="992e8-105">Compiling the Code</span></span>  
 <span data-ttu-id="992e8-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="992e8-106">This example requires:</span></span>  
  
- <span data-ttu-id="992e8-107">Mscorlib.dll へのアクセスと<xref:System>名前空間。</span><span class="sxs-lookup"><span data-stu-id="992e8-107">Access to Mscorlib.dll and the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="992e8-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="992e8-108">Robust Programming</span></span>  
 <span data-ttu-id="992e8-109">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="992e8-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="992e8-110">配列が空 (<xref:System.ArgumentNullException>クラス)</span><span class="sxs-lookup"><span data-stu-id="992e8-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
- <span data-ttu-id="992e8-111">配列が多次元 (<xref:System.RankException>クラス)</span><span class="sxs-lookup"><span data-stu-id="992e8-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
- <span data-ttu-id="992e8-112">配列の 1 つまたは複数の要素を実装しない、<xref:System.IComparable>インターフェイス (<xref:System.InvalidOperationException>クラス)</span><span class="sxs-lookup"><span data-stu-id="992e8-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="992e8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="992e8-113">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="992e8-114">配列</span><span class="sxs-lookup"><span data-stu-id="992e8-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="992e8-115">配列のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="992e8-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="992e8-116">コレクション</span><span class="sxs-lookup"><span data-stu-id="992e8-116">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="992e8-117">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="992e8-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
