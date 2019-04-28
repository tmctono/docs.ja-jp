---
title: '方法: データ バインドで XML 名前空間を使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 38bf6e8f88b0325193d49148cd6c33031f7b0a6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931912"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="ccebd-102">方法: データ バインドで XML 名前空間を使用する</span><span class="sxs-lookup"><span data-stu-id="ccebd-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="ccebd-103">例</span><span class="sxs-lookup"><span data-stu-id="ccebd-103">Example</span></span>  
 <span data-ttu-id="ccebd-104">この例では、[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] のバインディング ソースに指定された名前空間の処理方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ccebd-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="ccebd-105">[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] データに次の [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 名前空間定義がある場合:</span><span class="sxs-lookup"><span data-stu-id="ccebd-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="ccebd-106">使用することができます、<xref:System.Windows.Data.XmlNamespaceMapping>要素に名前空間にマップを<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="ccebd-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="ccebd-107">使用することができますし、<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>を参照する、[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]名前空間。</span><span class="sxs-lookup"><span data-stu-id="ccebd-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="ccebd-108"><xref:System.Windows.Controls.ListBox>この例では、表示、*タイトル*と*dc:date*それぞれの*項目*します。</span><span class="sxs-lookup"><span data-stu-id="ccebd-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="ccebd-109">なお、<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>指定で使用されるものと一致する必要はありません、[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]ソース; でプレフィックスが変更された場合、[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]ソース マッピングが正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="ccebd-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="ccebd-110">この例では、 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] web サービスでは、基になるが、<xref:System.Windows.Data.XmlNamespaceMapping>要素はインラインでも動作[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]または[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]埋め込みファイル内のデータ。</span><span class="sxs-lookup"><span data-stu-id="ccebd-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccebd-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccebd-111">See also</span></span>

- [<span data-ttu-id="ccebd-112">XMLDataProvider と XPath クエリを使用して XML データにバインドする</span><span class="sxs-lookup"><span data-stu-id="ccebd-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="ccebd-113">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="ccebd-113">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="ccebd-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="ccebd-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
