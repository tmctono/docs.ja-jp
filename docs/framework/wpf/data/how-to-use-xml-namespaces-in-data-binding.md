---
title: '方法 : データ バインドで XML 名前空間を使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: f6e6e042fa5583fcf91bd15c524537490fb6670c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740577"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="c2932-102">方法 : データ バインドで XML 名前空間を使用する</span><span class="sxs-lookup"><span data-stu-id="c2932-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="c2932-103">例</span><span class="sxs-lookup"><span data-stu-id="c2932-103">Example</span></span>
 <span data-ttu-id="c2932-104">この例では、XML バインディングソースで指定された名前空間を処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c2932-104">This example shows how to handle namespaces specified in your XML binding source.</span></span>

 <span data-ttu-id="c2932-105">XML データに次の XML 名前空間定義がある場合:</span><span class="sxs-lookup"><span data-stu-id="c2932-105">If your XML data has the following XML namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="c2932-106">次の例に示すように、<xref:System.Windows.Data.XmlNamespaceMapping> 要素を使用して、名前空間を <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>にマップできます。</span><span class="sxs-lookup"><span data-stu-id="c2932-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="c2932-107">その後、<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> を使用して、XML 名前空間を参照できます。</span><span class="sxs-lookup"><span data-stu-id="c2932-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the XML namespace.</span></span> <span data-ttu-id="c2932-108">この例の <xref:System.Windows.Controls.ListBox> では、各*項目*の*タイトル*と*dc: date*が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2932-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="c2932-109">指定した <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> は、XML ソースで使用されているものと一致する必要がないことに注意してください。XML ソースでプレフィックスが変更された場合、マッピングは引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="c2932-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the XML source; if the prefix changes in the XML source your mapping still works.</span></span>

 <span data-ttu-id="c2932-110">この特定の例では、XML データは web サービスから取得されますが、<xref:System.Windows.Data.XmlNamespaceMapping> 要素は、埋め込みファイル内のインライン XML データまたは XML データでも機能します。</span><span class="sxs-lookup"><span data-stu-id="c2932-110">In this particular example, the XML data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline XML or XML data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2932-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2932-111">See also</span></span>

- [<span data-ttu-id="c2932-112">XMLDataProvider と XPath クエリを使用して XML データにバインドする</span><span class="sxs-lookup"><span data-stu-id="c2932-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="c2932-113">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="c2932-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="c2932-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="c2932-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
