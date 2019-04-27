---
title: XML 名前空間 (Visual Basic) の使用
ms.date: 07/20/2015
ms.assetid: 428bf4b0-e348-4ffd-986b-d905d5a0e7fa
ms.openlocfilehash: b2b9db9ed547858eb5358d5e3c871c6a84d22ae6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907791"
---
# <a name="working-with-xml-namespaces-visual-basic"></a><span data-ttu-id="90cc5-102">XML 名前空間 (Visual Basic) の使用</span><span class="sxs-lookup"><span data-stu-id="90cc5-102">Working with XML Namespaces (Visual Basic)</span></span>
<span data-ttu-id="90cc5-103">このセクションのトピックでは、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] で名前空間がどのようにサポートされるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="90cc5-103">The topics in this section describe how [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supports namespaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90cc5-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="90cc5-104">In This Section</span></span>  
  
|<span data-ttu-id="90cc5-105">トピック</span><span class="sxs-lookup"><span data-stu-id="90cc5-105">Topic</span></span>|<span data-ttu-id="90cc5-106">説明</span><span class="sxs-lookup"><span data-stu-id="90cc5-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="90cc5-107">名前空間の概要 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="90cc5-107">Namespaces Overview (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)|<span data-ttu-id="90cc5-108">このトピックでは、名前空間、<xref:System.Xml.Linq.XName> クラス、および <xref:System.Xml.Linq.XNamespace> クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="90cc5-108">This topic introduces namespaces, the <xref:System.Xml.Linq.XName> class, and the <xref:System.Xml.Linq.XNamespace> class.</span></span>|  
|[<span data-ttu-id="90cc5-109">方法: 名前空間 (LINQ to XML) を持つドキュメントの作成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90cc5-109">How to: Create a Document with Namespaces (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-document-with-namespaces.md)|<span data-ttu-id="90cc5-110">名前空間を持つドキュメントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90cc5-110">Shows how to create documents with namespaces.</span></span>|  
|[<span data-ttu-id="90cc5-111">方法: コントロールの Namespace プレフィックス (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="90cc5-111">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-control-namespace-prefixes-linq-to-xml.md)|<span data-ttu-id="90cc5-112">グローバル名前空間を宣言することで名前空間プレフィックスを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90cc5-112">Shows how to control namespace prefixes by declaring global namespaces.</span></span>|  
|[<span data-ttu-id="90cc5-113">Visual Basic での既定の名前空間のスコープ</span><span class="sxs-lookup"><span data-stu-id="90cc5-113">Scope of Default Namespaces in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/scope-of-default-namespaces.md)|<span data-ttu-id="90cc5-114">既定の名前空間内の XML に対するクエリの適切な記述方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90cc5-114">Demonstrates the appropriate way to write queries for XML in the default namespace.</span></span>|  
|[<span data-ttu-id="90cc5-115">グローバル名前空間 (Visual Basic) (LINQ to XML) の使用</span><span class="sxs-lookup"><span data-stu-id="90cc5-115">Working with Global Namespaces (Visual Basic) (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-global-namespaces-linq-to-xml.md)|<span data-ttu-id="90cc5-116">Visual Basic、およびそれらを使用する理由にグローバル名前空間のセマンティクスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="90cc5-116">Explains the semantics of global namespaces in Visual Basic, and reasons for using them.</span></span>|  
|[<span data-ttu-id="90cc5-117">方法: (Visual Basic) の名前空間内の XML に対するクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="90cc5-117">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-queries-on-xml-in-namespaces.md)|<span data-ttu-id="90cc5-118">Visual Basic の linq to XML のクエリ XML 名前空間を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="90cc5-118">Demonstrates how to specify XML namespaces in Visual Basic LINQ to XML queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90cc5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="90cc5-119">See also</span></span>

- [<span data-ttu-id="90cc5-120">プログラミング ガイド (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90cc5-120">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
