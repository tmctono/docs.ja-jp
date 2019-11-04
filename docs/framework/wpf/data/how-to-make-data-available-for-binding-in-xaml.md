---
title: '方法 : XAML でデータをバインディング可能にする'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 2bfd9809a6ad487a7e706366dc6bce8fe951c940
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459759"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="61580-102">方法 : XAML でデータをバインディング可能にする</span><span class="sxs-lookup"><span data-stu-id="61580-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="61580-103">このトピックでは、アプリケーションのニーズに応じて、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]でデータをバインドできるようにするさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="61580-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61580-104">例</span><span class="sxs-lookup"><span data-stu-id="61580-104">Example</span></span>  
 <span data-ttu-id="61580-105">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]からバインドする共通言語ランタイム (CLR) オブジェクトがある場合、オブジェクトをバインドに使用できるようにするには、そのオブジェクトをリソースとして定義し、それに `x:Key`を指定します。</span><span class="sxs-lookup"><span data-stu-id="61580-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="61580-106">次の例では、`PersonName`という名前の文字列プロパティを持つ `Person` オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="61580-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="61580-107">`Person` オブジェクト (`<src>` 要素を含む強調表示されている行) は、`SDKSample`という名前空間で定義されています。</span><span class="sxs-lookup"><span data-stu-id="61580-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="61580-108">次に、`<TextBlock>` 要素を含む強調表示された行に表示されているように、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]内のオブジェクトに <xref:System.Windows.Controls.TextBlock> コントロールをバインドできます。</span><span class="sxs-lookup"><span data-stu-id="61580-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="61580-109">または、次の例のように <xref:System.Windows.Data.ObjectDataProvider> クラスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="61580-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="61580-110">`<TextBlock>` 要素を含む強調表示された行に示すように、同じ方法でバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="61580-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="61580-111">この例では、結果は同じです。テキストコンテンツ `Joe`の <xref:System.Windows.Controls.TextBlock> があります。</span><span class="sxs-lookup"><span data-stu-id="61580-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="61580-112">ただし、<xref:System.Windows.Data.ObjectDataProvider> クラスには、メソッドの結果にバインドする機能などの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="61580-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="61580-113">提供される機能が必要な場合は、<xref:System.Windows.Data.ObjectDataProvider> クラスの使用を選択できます。</span><span class="sxs-lookup"><span data-stu-id="61580-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="61580-114">ただし、既に作成されているオブジェクトにバインドする場合は、次の例に示すように、コードで `DataContext` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61580-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="61580-115"><xref:System.Windows.Data.XmlDataProvider> クラスを使用してバインディングのために [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] データにアクセスする方法については、「 [XMLDataProvider と XPath クエリを使用して XML データにバインド](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61580-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="61580-116"><xref:System.Windows.Data.ObjectDataProvider> クラスを使用してバインドする [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] データにアクセスするには、「 [XDocument、XElement、または LINQ FOR XML のクエリ結果へのバインド](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61580-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="61580-117">バインド先のデータを指定するさまざまな方法の詳細については、「[バインディングソースを指定](how-to-specify-the-binding-source.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61580-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="61580-118">バインドできるデータの種類や、独自の共通言語ランタイム (CLR) オブジェクトをバインド用に実装する方法の詳細については、「[バインディングソースの概要](binding-sources-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61580-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61580-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="61580-119">See also</span></span>

- [<span data-ttu-id="61580-120">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="61580-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="61580-121">方法トピック</span><span class="sxs-lookup"><span data-stu-id="61580-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
