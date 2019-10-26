---
title: '方法 : データ バインドで XML 名前空間を使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 9d8ddc5445bac28c68cd6cc99acf3313613a8c7f
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919668"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="4f07f-102">方法 : データ バインドで XML 名前空間を使用する</span><span class="sxs-lookup"><span data-stu-id="4f07f-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="4f07f-103">例</span><span class="sxs-lookup"><span data-stu-id="4f07f-103">Example</span></span>
 <span data-ttu-id="4f07f-104">この例では、[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] のバインディング ソースに指定された名前空間の処理方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4f07f-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>

 <span data-ttu-id="4f07f-105">[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] データに次の [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 名前空間定義がある場合:</span><span class="sxs-lookup"><span data-stu-id="4f07f-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="4f07f-106">次の例に示すように、<xref:System.Windows.Data.XmlNamespaceMapping> 要素を使用して、名前空間を <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>にマップできます。</span><span class="sxs-lookup"><span data-stu-id="4f07f-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="4f07f-107">その後、<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> を使用して、[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 名前空間を参照できます。</span><span class="sxs-lookup"><span data-stu-id="4f07f-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="4f07f-108">この例の <xref:System.Windows.Controls.ListBox> では、各*項目*の*タイトル*と*dc: date*が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f07f-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="4f07f-109">指定した <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> は、[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ソースで使用されているものと一致する必要がないことに注意してください。[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ソースでプレフィックスが変更された場合、マッピングは引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="4f07f-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>

 <span data-ttu-id="4f07f-110">この例では、[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] データは web サービスから取得されますが、<xref:System.Windows.Data.XmlNamespaceMapping> 要素はインライン [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] または埋め込みファイル内のデータの [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] でも機能します。</span><span class="sxs-lookup"><span data-stu-id="4f07f-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f07f-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f07f-111">See also</span></span>

- [<span data-ttu-id="4f07f-112">XMLDataProvider と XPath クエリを使用して XML データにバインドする</span><span class="sxs-lookup"><span data-stu-id="4f07f-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="4f07f-113">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="4f07f-113">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="4f07f-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="4f07f-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
