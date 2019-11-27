---
title: LINQ to XML における遅延実行とレイジー評価
ms.date: 07/20/2015
ms.assetid: 31998eed-b95e-47fb-a865-9de1f337d1fb
ms.openlocfilehash: 8e94b9133a2d2dd287fba91600c94460a5204b2c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346407"
---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-visual-basic"></a><span data-ttu-id="b3fed-102">LINQ to XML での遅延実行とレイジー評価 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3fed-102">Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)</span></span>
<span data-ttu-id="b3fed-103">クエリと軸の操作は、多くの場合、遅延実行を使用するように実装されています。</span><span class="sxs-lookup"><span data-stu-id="b3fed-103">Query and axis operations are often implemented to use deferred execution.</span></span> <span data-ttu-id="b3fed-104">このトピックでは、遅延実行の要件と利点、および実装に関する注意点について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3fed-104">This topic explains the requirements and advantages of deferred execution, and some implementation considerations.</span></span>  
  
## <a name="deferred-execution"></a><span data-ttu-id="b3fed-105">遅延実行</span><span class="sxs-lookup"><span data-stu-id="b3fed-105">Deferred Execution</span></span>  
 <span data-ttu-id="b3fed-106">遅延実行とは、"*具体*" 値が実際に必要となるまで、式の評価を遅らせることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b3fed-106">Deferred execution means that the evaluation of an expression is delayed until its *realized* value is actually required.</span></span> <span data-ttu-id="b3fed-107">大きなデータ コレクションの操作が必要な場合、特に連結されたクエリや操作が含まれているプログラムでは、遅延実行によってパフォーマンスが大幅に向上することがあります。</span><span class="sxs-lookup"><span data-stu-id="b3fed-107">Deferred execution can greatly improve performance when you have to manipulate large data collections, especially in programs that contain a series of chained queries or manipulations.</span></span> <span data-ttu-id="b3fed-108">最も効果的なケースでは、遅延実行を使用することによって、ソース コレクションの繰り返し処理を 1 度行うだけで済むようになります。</span><span class="sxs-lookup"><span data-stu-id="b3fed-108">In the best case, deferred execution enables only a single iteration through the source collection.</span></span>  
  
 <span data-ttu-id="b3fed-109">LINQ テクノロジでは、コア <xref:System.Linq?displayProperty=nameWithType> クラスのメンバーにおいても、<xref:System.Xml.Linq.Extensions?displayProperty=nameWithType> などのさまざまな LINQ 名前空間の拡張メソッドにおいても、遅延実行が広く利用されています。</span><span class="sxs-lookup"><span data-stu-id="b3fed-109">The LINQ technologies make extensive use of deferred execution in both the members of core <xref:System.Linq?displayProperty=nameWithType> classes and in the extension methods in the various LINQ namespaces, such as <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.</span></span>  
  
## <a name="eager-vs-lazy-evaluation"></a><span data-ttu-id="b3fed-110">集中評価とレイジー評価</span><span class="sxs-lookup"><span data-stu-id="b3fed-110">Eager vs. Lazy Evaluation</span></span>  
 <span data-ttu-id="b3fed-111">遅延実行を実装するメソッドを記述するときは、レイジー評価と集中評価のどちらを使用してメソッドを実装するかについても決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3fed-111">When you write a method that implements deferred execution, you also have to decide whether to implement the method using lazy evaluation or eager evaluation.</span></span>  
  
- <span data-ttu-id="b3fed-112">"*レイジー評価*" では、反復子を呼び出すたびに、ソース コレクションの 1 つの要素が処理されます。</span><span class="sxs-lookup"><span data-stu-id="b3fed-112">In *lazy evaluation*, a single element of the source collection is processed during each call to the iterator.</span></span> <span data-ttu-id="b3fed-113">これが、一般的な反復子の実装方法です。</span><span class="sxs-lookup"><span data-stu-id="b3fed-113">This is the typical way in which iterators are implemented.</span></span>  
  
- <span data-ttu-id="b3fed-114">"*集中評価*" では、反復子への最初の呼び出しの結果として、コレクション全体が処理されます。</span><span class="sxs-lookup"><span data-stu-id="b3fed-114">In *eager evaluation*, the first call to the iterator will result in the entire collection being processed.</span></span> <span data-ttu-id="b3fed-115">ソース コレクションの一時的なコピーが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b3fed-115">A temporary copy of the source collection might also be required.</span></span> <span data-ttu-id="b3fed-116">たとえば <xref:System.Linq.Enumerable.OrderBy%2A> メソッドでは、最初の要素を返す前に、コレクション全体を並べ替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3fed-116">For example, the <xref:System.Linq.Enumerable.OrderBy%2A> method has to sort the entire collection before it returns the first element.</span></span>  
  
 <span data-ttu-id="b3fed-117">通常は、レイジー評価を使用するとパフォーマンスが向上します。コレクション評価時のオーバーヘッド処理が均等に分散され、一時データの使用が最小限に抑えられるためです。</span><span class="sxs-lookup"><span data-stu-id="b3fed-117">Lazy evaluation usually yields better performance because it distributes overhead processing evenly throughout the evaluation of the collection and minimizes the use of temporary data.</span></span> <span data-ttu-id="b3fed-118">もちろん、操作によっては、中間結果を具体化するより他に方法がない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b3fed-118">Of course, for some operations, there is no other option than to materialize intermediate results.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b3fed-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="b3fed-119">Next Steps</span></span>  
 <span data-ttu-id="b3fed-120">このチュートリアルの次のトピックでは、遅延実行について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3fed-120">The next topic in this tutorial illustrates deferred execution:</span></span>  
  
- [<span data-ttu-id="b3fed-121">遅延実行の例 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3fed-121">Deferred Execution Example (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3fed-122">参照</span><span class="sxs-lookup"><span data-stu-id="b3fed-122">See also</span></span>

- [<span data-ttu-id="b3fed-123">チュートリアル: 遅延実行 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3fed-123">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)
- [<span data-ttu-id="b3fed-124">概念と用語 (関数型変換) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3fed-124">Concepts and Terminology (Functional Transformation) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)
- [<span data-ttu-id="b3fed-125">集計操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3fed-125">Aggregation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)
