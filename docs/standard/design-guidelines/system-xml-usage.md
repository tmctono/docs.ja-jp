---
title: System.Xml の使用法
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 2ecb709684834a8280c841eb8eef4f024481f7a4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743589"
---
# <a name="systemxml-usage"></a><span data-ttu-id="21b2b-102">System.Xml の使用法</span><span class="sxs-lookup"><span data-stu-id="21b2b-102">System.Xml Usage</span></span>
<span data-ttu-id="21b2b-103">このセクションでは、XML データを表すために使用できる <xref:System.Xml?displayProperty=nameWithType> 名前空間に存在するいくつかの型の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21b2b-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>

 <span data-ttu-id="21b2b-104">❌ <xref:System.Xml.XmlNode> または <xref:System.Xml.XmlDocument> を使用して XML データを表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="21b2b-104">❌ DO NOT use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="21b2b-105">代わりに、<xref:System.Xml.Linq.XNode> の <xref:System.Xml.XPath.IXPathNavigable>、<xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter>、またはサブタイプのインスタンスの使用を優先します。</span><span class="sxs-lookup"><span data-stu-id="21b2b-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="21b2b-106">`XmlNode` と `XmlDocument` は、パブリック Api で公開するように設計されていません。</span><span class="sxs-lookup"><span data-stu-id="21b2b-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>

 <span data-ttu-id="21b2b-107">✔️は、XML を受け入れるか返すメンバーの入力または出力として、`XNode` の `XmlReader`、`IXPathNavigable`、またはサブタイプを使用します。</span><span class="sxs-lookup"><span data-stu-id="21b2b-107">✔️ DO use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>

 <span data-ttu-id="21b2b-108">`XmlDocument`、`XmlNode`、または <xref:System.Xml.XPath.XPathDocument>ではなく、これらの抽象化を使用します。これにより、メモリ内の XML ドキュメントの特定の実装からメソッドが分離され、`XNode`、`XmlReader`、または <xref:System.Xml.XPath.XPathNavigator>を公開する仮想 XML データソースとの連携が可能になります。</span><span class="sxs-lookup"><span data-stu-id="21b2b-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>

 <span data-ttu-id="21b2b-109">基になるオブジェクトモデルまたはデータソースの XML ビューを表す型を作成する場合は ❌ `XmlDocument` をサブクラス化しません。</span><span class="sxs-lookup"><span data-stu-id="21b2b-109">❌ DO NOT subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>

 <span data-ttu-id="21b2b-110">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="21b2b-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="21b2b-111">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="21b2b-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="21b2b-112">参照</span><span class="sxs-lookup"><span data-stu-id="21b2b-112">See also</span></span>

- [<span data-ttu-id="21b2b-113">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="21b2b-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="21b2b-114">使用方法のガイドライン</span><span class="sxs-lookup"><span data-stu-id="21b2b-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
