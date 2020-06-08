---
title: XPathNavigator による XML データの編集
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b1f91616-3115-4264-9821-c66589d11d11
ms.openlocfilehash: 11395c52e399068e5242a1e041ebd9ed94bc2881
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292073"
---
# <a name="editing-xml-data-using-xpathnavigator"></a><span data-ttu-id="ba78a-102">XPathNavigator による XML データの編集</span><span class="sxs-lookup"><span data-stu-id="ba78a-102">Editing XML Data using XPathNavigator</span></span>
<span data-ttu-id="ba78a-103"><xref:System.Xml.XPath.XPathNavigator> クラスは、<xref:System.Xml.XmlDocument> オブジェクトに含まれる XML ドキュメントでノードと値の挿入、変更、および削除を行うメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="ba78a-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert, modify and remove nodes and values from an XML document contained in an <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="ba78a-104">ノードと値の挿入、変更、および削除を行うこれらのメソッドを使用するには、<xref:System.Xml.XPath.XPathNavigator> オブジェクトが編集可能である必要があります。つまり、その <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> プロパティを true にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba78a-104">In order to use any of these methods to insert, modify, and remove nodes and values, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be true.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba78a-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ba78a-105">In This Section</span></span>  
 [<span data-ttu-id="ba78a-106">XPathNavigator による XML データの挿入</span><span class="sxs-lookup"><span data-stu-id="ba78a-106">Insert XML Data using XPathNavigator</span></span>](insert-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="ba78a-107"><xref:System.Xml.XmlDocument> クラスを使用して <xref:System.Xml.XPath.XPathNavigator> オブジェクトに兄弟、子、および属性のノードと値を挿入する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba78a-107">Describes how to insert sibling, child, attribute nodes and values in to an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="ba78a-108">XpathNavigator による XML データの変更</span><span class="sxs-lookup"><span data-stu-id="ba78a-108">Modify XML Data using XPathNavigator</span></span>](modify-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="ba78a-109"><xref:System.Xml.XmlDocument> クラスを使用して <xref:System.Xml.XPath.XPathNavigator> オブジェクトのノードと値を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba78a-109">Describes how to modify nodes and values in an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="ba78a-110">XPathNavigator による XML データの削除</span><span class="sxs-lookup"><span data-stu-id="ba78a-110">Remove XML Data using XPathNavigator</span></span>](remove-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="ba78a-111"><xref:System.Xml.XmlDocument> クラスを使用して <xref:System.Xml.XPath.XPathNavigator> オブジェクトからノードと値を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba78a-111">Describes how to remove nodes and values from an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba78a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba78a-112">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="ba78a-113">XPath データ モデルを使用した XML データの処理</span><span class="sxs-lookup"><span data-stu-id="ba78a-113">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="ba78a-114">XPathDocument および XmlDocument を使用した XML データの読み取り</span><span class="sxs-lookup"><span data-stu-id="ba78a-114">Reading XML Data using XPathDocument and XmlDocument</span></span>](reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [<span data-ttu-id="ba78a-115">XPathNavigator を使用した XML データの選択、評価、および照合</span><span class="sxs-lookup"><span data-stu-id="ba78a-115">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="ba78a-116">XPathNavigator による XML データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="ba78a-116">Accessing XML Data using XPathNavigator</span></span>](accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="ba78a-117">XPathNavigator を使用したスキーマ検証</span><span class="sxs-lookup"><span data-stu-id="ba78a-117">Schema Validation using XPathNavigator</span></span>](schema-validation-using-xpathnavigator.md)
