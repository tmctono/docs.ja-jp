---
title: 関数型プログラミングと手続き型プログラミング (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: ea1015a5-d4c8-4d79-8e1e-ba17a40a4f39
ms.openlocfilehash: 0b525f13298e7402369b890516434cec47e01542
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398436"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-visual-basic"></a><span data-ttu-id="b5b1d-102">関数型プログラミングと手続き型プログラミング (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5b1d-102">Functional vs. Procedural Programming (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="b5b1d-103">XML アプリケーションには、次のようにさまざまな種類があります。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-103">There are various types of XML applications:</span></span>  
  
- <span data-ttu-id="b5b1d-104">ソース XML ドキュメントを受け取り、そのドキュメントとは構造の異なる新しい XML ドキュメントを生成するアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b5b1d-104">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
- <span data-ttu-id="b5b1d-105">ソース XML ドキュメントを受け取り、HTML や CSV テキスト ファイルなどのまったく異なる形式のドキュメントを生成するアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b5b1d-105">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
- <span data-ttu-id="b5b1d-106">ソース XML ドキュメントを受け取り、データベースにレコードを挿入するアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b5b1d-106">Some applications take source XML documents, and insert records into a database.</span></span>  
  
- <span data-ttu-id="b5b1d-107">データベースなどの別のソースからデータを受け取り、そのデータから XML ドキュメントを作成するアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b5b1d-107">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="b5b1d-108">XML アプリケーションには他にも種類がありますが、上記のアプリケーションは XML プログラマが実装する必要がある代表的な機能です。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-108">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="b5b1d-109">上記のすべてのアプリケーションで、開発者は 2 つの対照的な方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-109">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
- <span data-ttu-id="b5b1d-110">宣言型の方法を使用する関数型構築</span><span class="sxs-lookup"><span data-stu-id="b5b1d-110">Functional construction using a declarative approach.</span></span>  
  
- <span data-ttu-id="b5b1d-111">プロシージャ コードを使用するメモリ内の XML ツリーの変更</span><span class="sxs-lookup"><span data-stu-id="b5b1d-111">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="b5b1d-112">LINQ to XML は両方の方法をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-112">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="b5b1d-113">関数型の方法を使用する場合は、ソース ドキュメントを受け取り、必要な構造を持つ完全に新しいドキュメントが生成される変換を記述します。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-113">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="b5b1d-114">XML ツリーを直接変更する場合は、メモリ内の XML ツリーでノード間を移動し、必要に応じてノードを挿入、削除、変更します。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-114">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="b5b1d-115">いずれの方法でも LINQ to XML を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-115">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="b5b1d-116">同じクラスを使用し、場合によっては同じメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-116">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="b5b1d-117">ただし、2 つの方法の構造と目標はかなり異なります。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-117">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="b5b1d-118">たとえば、これらの方法のうち、どちらのパフォーマンスが優れているか、また使用するメモリ量はどちらが多い (または少ない) かは、状況によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-118">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="b5b1d-119">また、どちらの方法が保守性に優れたコードをより簡単に記述し生成できるかも、状況によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-119">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="b5b1d-120">2 つの方法の違いについては、「[メモリ内の XML ツリーの変更と関数型構築 (LINQ to XML) (Visual Basic)](in-memory-xml-tree-modification-vs-functional-construction.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-120">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)](in-memory-xml-tree-modification-vs-functional-construction.md).</span></span>  
  
 <span data-ttu-id="b5b1d-121">関数型変換の記述に関するチュートリアルについては、「[XML の純粋関数型変換 (Visual Basic)](pure-functional-transformations-of-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5b1d-121">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (Visual Basic)](pure-functional-transformations-of-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b1d-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5b1d-122">See also</span></span>

- [<span data-ttu-id="b5b1d-123">LINQ to XML プログラミングの概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5b1d-123">LINQ to XML Programming Overview (Visual Basic)</span></span>](linq-to-xml-programming-overview.md)
