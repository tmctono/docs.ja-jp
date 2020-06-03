---
title: XPathNavigator による XML データへのアクセス
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: c57b46e6-5c77-408f-bc4e-67a5dcc9cc05
ms.openlocfilehash: 8cba6e106623169f5575684162bf3be383563275
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202313"
---
# <a name="accessing-xml-data-using-xpathnavigator"></a><span data-ttu-id="37451-102">XPathNavigator による XML データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="37451-102">Accessing XML Data using XPathNavigator</span></span>
<span data-ttu-id="37451-103"><xref:System.Xml.XPath.XPathNavigator> クラスは、<xref:System.Xml.XPath.XPathDocument> オブジェクトまたは <xref:System.Xml.XmlDocument> オブジェクト内でのノード間の移動、XML データの抽出、および厳密に型指定された XML データにアクセスするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="37451-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to navigate nodes, extract XML data and access strongly typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37451-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="37451-104">In This Section</span></span>  
 [<span data-ttu-id="37451-105">XPathNavigator を使用するノード セットのナビゲーション</span><span class="sxs-lookup"><span data-stu-id="37451-105">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="37451-106"><xref:System.Xml.XPath.XPathNavigator> オブジェクトまたは <xref:System.Xml.XPath.XPathDocument> オブジェクト内で、ノードの移動に使用される <xref:System.Xml.XmlDocument> クラスでのノード セットの移動メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="37451-106">Describes the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class used to navigate nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="37451-107">XPathNavigator を使用する属性と名前空間のナビゲーション</span><span class="sxs-lookup"><span data-stu-id="37451-107">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="37451-108"><xref:System.Xml.XPath.XPathNavigator> クラスにおける属性ノードと名前空間ノードの移動メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="37451-108">Describes the attribute and namespace node navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="37451-109">XpathNavigator を使用した XML データの抽出</span><span class="sxs-lookup"><span data-stu-id="37451-109">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="37451-110"><xref:System.Xml.XPath.XPathDocument> オブジェクトまたは <xref:System.Xml.XmlDocument> オブジェクトから XML データを抽出する各種のメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="37451-110">Describes the various methods of extracting XML data from an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="37451-111">厳密に型指定された XML データへの XPathNavigator を使用したアクセス</span><span class="sxs-lookup"><span data-stu-id="37451-111">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="37451-112"><xref:System.Xml.XPath.XPathDocument> オブジェクトまたは <xref:System.Xml.XmlDocument> オブジェクト内で <xref:System.Xml.XPath.XPathNavigator> クラスを使用して、厳密に型指定された XML データにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="37451-112">Describes accessing strongly typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="37451-113">ユーザー定義の関数と変数</span><span class="sxs-lookup"><span data-stu-id="37451-113">User Defined Functions and Variables</span></span>](../../../../docs/standard/data/xml/user-defined-functions-and-variables.md)  
 <span data-ttu-id="37451-114">カスタム クラス <xref:System.Xml.Xsl.XsltContext> を、拡張関数および変数をサポートする <xref:System.Xml.Xsl.IXsltContextFunction> インターフェイスおよび <xref:System.Xml.Xsl.IXsltContextVariable> インターフェイスと共に実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="37451-114">Describes implementing a custom <xref:System.Xml.Xsl.XsltContext> class along with the interfaces <xref:System.Xml.Xsl.IXsltContextFunction> and <xref:System.Xml.Xsl.IXsltContextVariable> that support extension functions and variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37451-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="37451-115">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="37451-116">XPath データ モデルを使用した XML データの処理</span><span class="sxs-lookup"><span data-stu-id="37451-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="37451-117">XPathDocument および XmlDocument を使用した XML データの読み取り</span><span class="sxs-lookup"><span data-stu-id="37451-117">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [<span data-ttu-id="37451-118">XPathNavigator を使用した XML データの選択、評価、および照合</span><span class="sxs-lookup"><span data-stu-id="37451-118">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="37451-119">XPathNavigator による XML データの編集</span><span class="sxs-lookup"><span data-stu-id="37451-119">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="37451-120">XPathNavigator を使用したスキーマ検証</span><span class="sxs-lookup"><span data-stu-id="37451-120">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
