---
title: '方法: サービス操作 (WCF Data Services) の定義します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: dbd14ba9ed24fb3f18946e817f61f8cbf2e9b1b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936553"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a><span data-ttu-id="4ab32-102">方法: サービス操作 (WCF Data Services) の定義します。</span><span class="sxs-lookup"><span data-stu-id="4ab32-102">How to: Define a Service Operation (WCF Data Services)</span></span>

[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="4ab32-103">は、サーバー上でサービス操作として定義されたメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="4ab32-103">expose methods that are defined on the server as service operations.</span></span> <span data-ttu-id="4ab32-104">サービス操作では、サーバーで定義されているメソッドに URI を介してアクセスを提供するデータ サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4ab32-104">Service operations allow a data service to provide access through a URI to a method that is defined on the server.</span></span> <span data-ttu-id="4ab32-105">サービス操作を定義するには、適用、[`WebGet]`または`[WebInvoke]`属性をメソッド。</span><span class="sxs-lookup"><span data-stu-id="4ab32-105">To define a service operation, apply the [`WebGet]` or `[WebInvoke]` attribute to the method.</span></span> <span data-ttu-id="4ab32-106">クエリ演算子をサポートするために、サービス操作を返す必要があります、<xref:System.Linq.IQueryable%601>インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4ab32-106">To support query operators, the service operation must return an <xref:System.Linq.IQueryable%601> instance.</span></span> <span data-ttu-id="4ab32-107">サービス操作は、<xref:System.Data.Services.DataService%601.CurrentDataSource%2A> の <xref:System.Data.Services.DataService%601> プロパティを介して、基になるデータ ソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4ab32-107">Service operations may access the underlying data source through the <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> property on the <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="4ab32-108">詳細については、次を参照してください。[サービス操作](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ab32-108">For more information, see [Service Operations](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span></span>

<span data-ttu-id="4ab32-109">このトピックの例では、`GetOrdersByCity` という名前のサービス操作を定義します。このサービス操作は、<xref:System.Linq.IQueryable%601> オブジェクトおよび関連する `Orders` オブジェクトのフィルターされた `Order_Details` インスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="4ab32-109">The example in this topic defines a service operation named `GetOrdersByCity` that returns a filtered <xref:System.Linq.IQueryable%601> instance of `Orders` and related `Order_Details` objects.</span></span> <span data-ttu-id="4ab32-110">この例は、Northwind サンプル データ サービスのデータ ソースである <xref:System.Data.Objects.ObjectContext> インスタンスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4ab32-110">The example accesses the <xref:System.Data.Objects.ObjectContext> instance that is the data source for the Northwind sample data service.</span></span> <span data-ttu-id="4ab32-111">このサービスの作成を完了すると、 [WCF Data Services クイック スタート](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ab32-111">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>

### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a><span data-ttu-id="4ab32-112">Northwind データ サービスのサービス操作を定義するには</span><span class="sxs-lookup"><span data-stu-id="4ab32-112">To define a service operation in the Northwind data service</span></span>

1. <span data-ttu-id="4ab32-113">Northwind データ サービス プロジェクトで Northwind.svc ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ab32-113">In the Northwind data service project, open the Northwind.svc file.</span></span>

2. <span data-ttu-id="4ab32-114">`Northwind` クラスで、次に示すように `GetOrdersByCity` というサービス操作メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="4ab32-114">In the `Northwind` class, define a service operation method named `GetOrdersByCity` as follows:</span></span>

     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationdef)]

3. <span data-ttu-id="4ab32-115">`InitializeService` クラスの `Northwind` メソッドで次のコードを追加して、サービス操作へのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ab32-115">In the `InitializeService` method of the `Northwind` class, add the following code to enable access to the service operation:</span></span>

     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationconfig)]

### <a name="to-query-the-getordersbycity-service-operation"></a><span data-ttu-id="4ab32-116">GetOrdersByCity サービス操作をクエリするには</span><span class="sxs-lookup"><span data-stu-id="4ab32-116">To query the GetOrdersByCity service operation</span></span>

- <span data-ttu-id="4ab32-117">Web ブラウザーで次のいずれかの URI を入力して、次の例で定義されているサービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4ab32-117">In a Web browser, enter one of the following URIs to invoke the service operation that is defined in the following example:</span></span>

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`

## <a name="example"></a><span data-ttu-id="4ab32-118">例</span><span class="sxs-lookup"><span data-stu-id="4ab32-118">Example</span></span>

<span data-ttu-id="4ab32-119">次の例は、`GetOrderByCity` という名前のサービス操作を Northwind データ サービスに実装します。</span><span class="sxs-lookup"><span data-stu-id="4ab32-119">The following example implements a service operation named `GetOrderByCity` on the Northwind data service.</span></span> <span data-ttu-id="4ab32-120">この操作は、ADO.NET Entity Framework を使用して、`Orders` オブジェクトのセットおよび関連する `Order_Details` オブジェクトを、指定した都市名に基づく <xref:System.Linq.IQueryable%601> インスタンスとして返します。</span><span class="sxs-lookup"><span data-stu-id="4ab32-120">This operation uses the ADO.NET Entity Framework to return a set of `Orders` and related `Order_Details` objects as an <xref:System.Linq.IQueryable%601> instance based on the provided city name.</span></span>

> [!NOTE]
> <span data-ttu-id="4ab32-121">メソッドは <xref:System.Linq.IQueryable%601> インスタンスを返すので、クエリ操作は、このサービス操作エンドポイントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4ab32-121">Query operators are supported on this service operation endpoint because the method returns an <xref:System.Linq.IQueryable%601> instance.</span></span>

[!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperation)]
[!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperation)]

## <a name="see-also"></a><span data-ttu-id="4ab32-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ab32-122">See also</span></span>

- [<span data-ttu-id="4ab32-123">WCF Data Services の定義</span><span class="sxs-lookup"><span data-stu-id="4ab32-123">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
