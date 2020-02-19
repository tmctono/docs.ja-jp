---
title: '方法 : Web サービスにバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 3a3f6edc974448ddab9fe30e97bdc1130d3b97dc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449973"
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="983d7-102">方法 : Web サービスにバインドする</span><span class="sxs-lookup"><span data-stu-id="983d7-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="983d7-103">この例では、Web サービスメソッド呼び出しによって返されるオブジェクトにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="983d7-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="983d7-104">例</span><span class="sxs-lookup"><span data-stu-id="983d7-104">Example</span></span>  
 <span data-ttu-id="983d7-105">この例では、MSDN/TechNet Publishing System (MTPS) コンテンツサービスを使用して、指定されたドキュメントでサポートされている言語の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="983d7-105">This example uses the MSDN/TechNet Publishing System (MTPS) Content Service to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="983d7-106">Web サービスを呼び出す前に、その Web サービスへの参照を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="983d7-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="983d7-107">Visual Studio を使用して MTPS サービスへの Web 参照を作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="983d7-107">To create a Web reference to the MTPS service using Visual Studio, follow the following steps:</span></span>  
  
1. <span data-ttu-id="983d7-108">Visual Studio でプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="983d7-108">Open your project in Visual Studio.</span></span>  
  
2. <span data-ttu-id="983d7-109">**[プロジェクト]** メニューの **[Web 参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="983d7-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3. <span data-ttu-id="983d7-110">ダイアログボックスで、 **URL**を[http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)に設定します。</span><span class="sxs-lookup"><span data-stu-id="983d7-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4. <span data-ttu-id="983d7-111">[実行 **] をクリックし、[** 参照の**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="983d7-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="983d7-112">次に、Web サービスメソッドを呼び出し、適切なコントロールまたはウィンドウの <xref:System.Windows.FrameworkElement.DataContext%2A> を、返されたオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="983d7-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="983d7-113">MTPS サービスの `GetContent` メソッドは、`getContentRequest` オブジェクトへの参照を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="983d7-113">The `GetContent` method of the MTPS service takes a reference to the `getContentRequest` object.</span></span> <span data-ttu-id="983d7-114">したがって、次の例では、最初に要求オブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="983d7-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="983d7-115"><xref:System.Windows.FrameworkElement.DataContext%2A> が設定されたら、<xref:System.Windows.FrameworkElement.DataContext%2A> が設定されているオブジェクトのプロパティへのバインドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="983d7-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="983d7-116">この例では、<xref:System.Windows.FrameworkElement.DataContext%2A> は `GetContent` メソッドによって返される `getContentResponse` オブジェクトに設定されます。</span><span class="sxs-lookup"><span data-stu-id="983d7-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the `getContentResponse` object returned by the `GetContent` method.</span></span> <span data-ttu-id="983d7-117">次の例では、<xref:System.Windows.Controls.ItemsControl> をにバインドし、`getContentResponse`の `availableVersionsAndLocales` の `locale` 値を表示します。</span><span class="sxs-lookup"><span data-stu-id="983d7-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the `locale` values of `availableVersionsAndLocales` of `getContentResponse`.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="983d7-118">`getContentResponse`の構造の詳細については、[コンテンツサービスのドキュメント](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="983d7-118">For information about the structure of `getContentResponse`, see [Content Service documentation](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983d7-119">参照</span><span class="sxs-lookup"><span data-stu-id="983d7-119">See also</span></span>

- [<span data-ttu-id="983d7-120">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="983d7-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="983d7-121">バインディング ソースの概要</span><span class="sxs-lookup"><span data-stu-id="983d7-121">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="983d7-122">XAML でデータをバインディング可能にする</span><span class="sxs-lookup"><span data-stu-id="983d7-122">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
