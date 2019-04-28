---
title: System.Xml の使用法
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: KrzysztofCwalina
ms.openlocfilehash: fc94ac62d1f2413c5f51446a8f6d0a52d9151557
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650129"
---
# <a name="systemxml-usage"></a><span data-ttu-id="19dc3-102">System.Xml の使用法</span><span class="sxs-lookup"><span data-stu-id="19dc3-102">System.Xml Usage</span></span>
<span data-ttu-id="19dc3-103">このセクションで内に存在するいくつかの型の使用方法について説明<xref:System.Xml?displayProperty=nameWithType>XML データを表すために使用する名前空間。</span><span class="sxs-lookup"><span data-stu-id="19dc3-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="19dc3-104">**X DO NOT** 使用<xref:System.Xml.XmlNode>または<xref:System.Xml.XmlDocument>XML データを表します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="19dc3-105">インスタンスを使用して優先<xref:System.Xml.XPath.IXPathNavigable>、 <xref:System.Xml.XmlReader>、 <xref:System.Xml.XmlWriter>、またはのサブタイプ<xref:System.Xml.Linq.XNode>代わりにします。</span><span class="sxs-lookup"><span data-stu-id="19dc3-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="19dc3-106">`XmlNode` `XmlDocument`パブリック Api で公開するために設計されていません。</span><span class="sxs-lookup"><span data-stu-id="19dc3-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="19dc3-107">**✓ DO** 使用`XmlReader`、 `IXPathNavigable`、またはのサブタイプ`XNode`をそのまま使用したり、XML を返すメンバーの入力または出力として。</span><span class="sxs-lookup"><span data-stu-id="19dc3-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="19dc3-108">代わりにこれらの抽象化を使用して、 `XmlDocument`、 `XmlNode`、または<xref:System.Xml.XPath.XPathDocument>これ、インメモリ XML ドキュメントの特定の実装からメソッドを分離し、公開仮想の XML データ ソースを操作することができますので、 `XNode`、 `XmlReader`、または<xref:System.Xml.XPath.XPathNavigator>します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="19dc3-109">**X DO NOT** サブクラス`XmlDocument`を基になるオブジェクト モデルまたはデータ ソースの XML ビューを表す型を作成するかどうか。</span><span class="sxs-lookup"><span data-stu-id="19dc3-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="19dc3-110">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="19dc3-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="19dc3-111">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="19dc3-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19dc3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="19dc3-112">See also</span></span>

- [<span data-ttu-id="19dc3-113">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="19dc3-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="19dc3-114">使用方法のガイドライン</span><span class="sxs-lookup"><span data-stu-id="19dc3-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
