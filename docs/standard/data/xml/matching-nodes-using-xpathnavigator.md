---
title: XPathNavigator によるノードの一致
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 882e92c6c8cb6e638ca299ed4c43b9da8f4bf235
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923323"
---
# <a name="matching-nodes-using-xpathnavigator"></a><span data-ttu-id="1058a-102">XPathNavigator によるノードの一致</span><span class="sxs-lookup"><span data-stu-id="1058a-102">Matching Nodes using XPathNavigator</span></span>
<span data-ttu-id="1058a-103"><xref:System.Xml.XPath.XPathNavigator> クラスは、ノードが XPath 式に一致するかどうかを調べる <xref:System.Xml.XPath.XPathNavigator.Matches%2A> メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1058a-103">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method to determine if a node matches an XPath expression.</span></span> <span data-ttu-id="1058a-104"><xref:System.Xml.XPath.XPathNavigator.Matches%2A> メソッドは XPath 式を入力として取り、現在のノードが与えられた XPath 式またはコンパイル済み <xref:System.Boolean> オブジェクトと一致するかどうかを示す <xref:System.Xml.XPath.XPathExpression> を返します。</span><span class="sxs-lookup"><span data-stu-id="1058a-104">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method takes an XPath expression as input and returns a <xref:System.Boolean> that indicates if the current node matches the given XPath expression or the given compiled <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
## <a name="matching-nodes"></a><span data-ttu-id="1058a-105">ノードの一致</span><span class="sxs-lookup"><span data-stu-id="1058a-105">Matching Nodes</span></span>  
 <span data-ttu-id="1058a-106"><xref:System.Xml.XPath.XPathNavigator.Matches%2A> メソッドは、現在のノードが指定した XPath 式と一致すると `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="1058a-106">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method returns `true` if the current node matches the XPath expression specified.</span></span> <span data-ttu-id="1058a-107">たとえば次のコード サンプルで、<xref:System.Xml.XPath.XPathNavigator.Matches%2A> メソッドは、現在のノードが要素 `true` であり、要素 `b` が属性 `b` を持つ場合に `c` を返します。</span><span class="sxs-lookup"><span data-stu-id="1058a-107">For example, in the code example that follows, the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method will return `true` if the current node is the element `b`, and element `b` has an attribute `c`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1058a-108"><xref:System.Xml.XPath.XPathNavigator.Matches%2A> メソッドは <xref:System.Xml.XPath.XPathNavigator> の状態を変えません。</span><span class="sxs-lookup"><span data-stu-id="1058a-108">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method does not change the state of the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a><span data-ttu-id="1058a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="1058a-109">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="1058a-110">XPath データ モデルを使用した XML データの処理</span><span class="sxs-lookup"><span data-stu-id="1058a-110">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="1058a-111">XPathNavigator を使用した XML データの選択</span><span class="sxs-lookup"><span data-stu-id="1058a-111">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="1058a-112">XPathNavigator による XPath 式の評価</span><span class="sxs-lookup"><span data-stu-id="1058a-112">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="1058a-113">XPath クエリで認識されるノード型</span><span class="sxs-lookup"><span data-stu-id="1058a-113">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="1058a-114">XPath クエリおよび名前空間</span><span class="sxs-lookup"><span data-stu-id="1058a-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [<span data-ttu-id="1058a-115">コンパイルされた XPath 式</span><span class="sxs-lookup"><span data-stu-id="1058a-115">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
