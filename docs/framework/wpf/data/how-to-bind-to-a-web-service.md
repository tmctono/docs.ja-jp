---
title: '方法: Web サービスにバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 2c3bc1f2142f07aba3df2da6c46117d3907443a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304988"
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="18bfb-102">方法: Web サービスにバインドする</span><span class="sxs-lookup"><span data-stu-id="18bfb-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="18bfb-103">この例では、Web サービス メソッドの呼び出しによって返されるオブジェクトにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="18bfb-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18bfb-104">例</span><span class="sxs-lookup"><span data-stu-id="18bfb-104">Example</span></span>  
 <span data-ttu-id="18bfb-105">この例では、 [MSDN/TechNet Publishing System (MTPS) コンテンツ サービス](https://go.microsoft.com/fwlink/?LinkId=95677)指定されたドキュメントでサポートされる言語の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="18bfb-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](https://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="18bfb-106">Web サービスを呼び出す前への参照を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18bfb-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="18bfb-107">MTPS のサービスを使用する Web 参照を作成する[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="18bfb-107">To create a Web reference to the MTPS service using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], follow the following steps:</span></span>  
  
1. <span data-ttu-id="18bfb-108">[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] でプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="18bfb-108">Open your project in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span></span>  
  
2. <span data-ttu-id="18bfb-109">**プロジェクト** メニューのをクリックして**Web 参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="18bfb-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3. <span data-ttu-id="18bfb-110">ダイアログ ボックスで、設定、 **URL**に[ http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)します。</span><span class="sxs-lookup"><span data-stu-id="18bfb-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4. <span data-ttu-id="18bfb-111">キーを押して**移動**し**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="18bfb-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="18bfb-112">次に、Web サービス メソッドを呼び出して設定と、<xref:System.Windows.FrameworkElement.DataContext%2A>の適切なコントロールまたはウィンドウに返されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18bfb-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="18bfb-113">**GetContent** MTPS サービスのメソッドへの参照を受け取り、 **getContentRequest**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18bfb-113">The **GetContent** method of the MTPS service takes a reference to the **getContentRequest** object.</span></span> <span data-ttu-id="18bfb-114">そのため、次の例は、要求オブジェクトを最初に設定します。</span><span class="sxs-lookup"><span data-stu-id="18bfb-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="18bfb-115">後に、<xref:System.Windows.FrameworkElement.DataContext%2A>するオブジェクトのプロパティへのバインドを作成できます、設定されている、<xref:System.Windows.FrameworkElement.DataContext%2A>に設定されています。</span><span class="sxs-lookup"><span data-stu-id="18bfb-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="18bfb-116">この例で、<xref:System.Windows.FrameworkElement.DataContext%2A>に設定されている、 **getContentResponse**によって返されるオブジェクト、 **GetContent**メソッド。</span><span class="sxs-lookup"><span data-stu-id="18bfb-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the **getContentResponse** object returned by the **GetContent** method.</span></span> <span data-ttu-id="18bfb-117">次の例では、<xref:System.Windows.Controls.ItemsControl>にバインドし、表示、**ロケール**の値**availableVersionsAndLocales**の**getContentResponse**します。</span><span class="sxs-lookup"><span data-stu-id="18bfb-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the **locale** values of **availableVersionsAndLocales** of **getContentResponse**.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="18bfb-118">構造体について**getContentResponse**を参照してください[コンテンツ サービス ドキュメント](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx)します。</span><span class="sxs-lookup"><span data-stu-id="18bfb-118">For information about the structure of **getContentResponse**, see [Content Service documentation](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18bfb-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="18bfb-119">See also</span></span>

- [<span data-ttu-id="18bfb-120">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="18bfb-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="18bfb-121">バインディング ソースの概要</span><span class="sxs-lookup"><span data-stu-id="18bfb-121">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="18bfb-122">XAML でデータをバインディング可能にする</span><span class="sxs-lookup"><span data-stu-id="18bfb-122">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
