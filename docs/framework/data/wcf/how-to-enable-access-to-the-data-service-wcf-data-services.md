---
title: '方法: データ サービスへのアクセスを有効にする (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: 62622a5788a735497a6869c114c572e947067449
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155420"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="23aaa-102">方法: データ サービスへのアクセスを有効にする (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="23aaa-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>

<span data-ttu-id="23aaa-103">WCF Data Services では、データ サービスによって公開されているリソースに明示的にアクセス権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23aaa-103">In WCF Data Services, you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="23aaa-104">つまり、新しいデータ サービスを作成した後も、個々のリソースに対し、エンティティ セットとして明示的にアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23aaa-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="23aaa-105">このトピックでは、[クイックスタート](quickstart-wcf-data-services.md)を完了するときに作成する Northwind データ サービスの 5 つのエンティティ セットへの読み取りおよび書き込みアクセスを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23aaa-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="23aaa-106"><xref:System.Data.Services.EntitySetRights> 列挙体は <xref:System.FlagsAttribute> を使用して定義されているので、論理和演算子を使用して 1 つのエンティティ セットに複数のアクセス許可を指定できます。</span><span class="sxs-lookup"><span data-stu-id="23aaa-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23aaa-107">ASP.NET アプリケーションにアクセスできるクライアントは、データ サービスによって公開されるリソースにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="23aaa-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="23aaa-108">運用データ サービスで、リソースへの承認されていないアクセスを防止するために、アプリケーション自身もセキュリティで保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23aaa-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="23aaa-109">詳細については、「[ASP.NET Web サイトのセキュリティ保護](/previous-versions/aspnet/91f66yxt(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23aaa-109">For more information, see [Securing ASP.NET Web Sites](/previous-versions/aspnet/91f66yxt(v=vs.100)).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="23aaa-110">データ サービスへのアクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="23aaa-110">To enable access to the data service</span></span>  
  
- <span data-ttu-id="23aaa-111">データ サービスのコードで、`InitializeService` 関数のプレースホルダーのコードを次の内容で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="23aaa-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="23aaa-112">これにより、クライアントから `Orders` および `Order_Details` エンティティ セットへの読み取りおよび書き込みアクセスと、`Customers` エンティティ セットへの読み取り専用アクセスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="23aaa-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23aaa-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="23aaa-113">See also</span></span>

- [<span data-ttu-id="23aaa-114">方法: IIS 上で実行する WCF Data Service を開発する</span><span class="sxs-lookup"><span data-stu-id="23aaa-114">How to: Develop a WCF Data Service Running on IIS</span></span>](how-to-develop-a-wcf-data-service-running-on-iis.md)
- [<span data-ttu-id="23aaa-115">データ サービスの構成</span><span class="sxs-lookup"><span data-stu-id="23aaa-115">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)
