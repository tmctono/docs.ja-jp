---
title: '方法: リフレクション プロバイダー (WCF Data Services) を使用してデータ サービスを作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 70f232bb510ebfcd125a699f434cd1deea9f8a64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172693"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="d1bab-102">方法: リフレクション プロバイダー (WCF Data Services) を使用してデータ サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-102">How to: Create a Data Service Using the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="d1bab-103">これらのクラスが実装するオブジェクトとして公開されている限り、任意のクラスに基づいているデータ モデルを定義することができます、<xref:System.Linq.IQueryable%601>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d1bab-103">enables you to define a data model that is based on arbitrary classes as long as those classes are exposed as objects that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="d1bab-104">詳細については、次を参照してください。[データ サービス プロバイダー](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-104">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1bab-105">例</span><span class="sxs-lookup"><span data-stu-id="d1bab-105">Example</span></span>  
 <span data-ttu-id="d1bab-106">次の例は、`Orders` および `Items` を含むデータ モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-106">The following example defines a data model that includes `Orders` and `Items`.</span></span> <span data-ttu-id="d1bab-107">エンティティ コンテナー クラス `OrderItemData` には、<xref:System.Linq.IQueryable%601> インターフェイスを返す 2 つのパブリック メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="d1bab-107">The entity container class `OrderItemData` has two public methods that return <xref:System.Linq.IQueryable%601> interfaces.</span></span> <span data-ttu-id="d1bab-108">これらのインターフェイスは、`Orders` エンティティ型と `Items` エンティティ型のエンティティ セットです。</span><span class="sxs-lookup"><span data-stu-id="d1bab-108">These interfaces are the entity sets of the `Orders` and `Items` entity types.</span></span> <span data-ttu-id="d1bab-109">`Order` には複数の `Items` を含めることができるので、`Orders` エンティティ型には `Items` オブジェクトのコレクションを返す `Items` ナビゲーション プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d1bab-109">An `Order` can include multiple `Items`, so the `Orders` entity type has an `Items` navigation property that returns a collection of `Items` objects.</span></span> <span data-ttu-id="d1bab-110">`OrderItemData` エンティティ コンテナー クラスは、<xref:System.Data.Services.DataService%601> データ サービスが派生する `OrderItems` クラスのジェネリック型です。</span><span class="sxs-lookup"><span data-stu-id="d1bab-110">The `OrderItemData` entity container class is the generic type of the <xref:System.Data.Services.DataService%601> class from which the `OrderItems` data service is derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1bab-111">この例はメモリ内のデータ プロバイダーを示し、変更は現在のオブジェクト インスタンスの外部で永続化されないので、<xref:System.Data.Services.IUpdatable> インターフェイスを実装する利点はありません。</span><span class="sxs-lookup"><span data-stu-id="d1bab-111">Because this example demonstrates an in-memory data provider and changes are not persisted outside of the current object instances, there is no benefit derived from implementing the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="d1bab-112">実装する例については、<xref:System.Data.Services.IUpdatable>インターフェイスは、「[方法。SQL データ ソースを LINQ を使用してデータ サービスを作成する](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-112">For an example that implements the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria reflection provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria reflection provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a><span data-ttu-id="d1bab-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1bab-113">See also</span></span>

- [<span data-ttu-id="d1bab-114">方法: LINQ to SQL データ ソースを使用してデータ サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="d1bab-114">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
- [<span data-ttu-id="d1bab-115">Data Services プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d1bab-115">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="d1bab-116">方法: ADO.NET Entity Framework データ ソースを使用してデータ サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="d1bab-116">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
