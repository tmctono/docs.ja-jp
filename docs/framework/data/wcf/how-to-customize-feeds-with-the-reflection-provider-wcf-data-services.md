---
title: '方法: リフレクションプロバイダーを使用したフィードのカスタマイズ (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: 43f46729ba84356bcb6507779bef9e4fd35bc315
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790677"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="40519-102">方法: リフレクションプロバイダーを使用したフィードのカスタマイズ (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="40519-102">How to: Customize Feeds with the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="40519-103">では、データ サービス応答の Atom シリアル化をカスタマイズして、AtomPub プロトコルで定義されている未使用の要素にエンティティのプロパティをマップできます。</span><span class="sxs-lookup"><span data-stu-id="40519-103">enables you to customize the Atom serialization in a data service response so that properties of an entity may be mapped to unused elements that are defined in the AtomPub protocol.</span></span> <span data-ttu-id="40519-104">このトピックでは、リフレクション プロバイダーを使用して、定義されているデータ モデル内のエンティティ型のマッピング属性を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="40519-104">This topic shows how to define mapping attributes for the entity types in a data model that is defined by using the reflection provider.</span></span> <span data-ttu-id="40519-105">詳細については、「[フィードのカスタマイズ](feed-customization-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40519-105">For more information, see [Feed Customization](feed-customization-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="40519-106">この例のデータモデルは、トピック「 [How to:リフレクションプロバイダーを使用してデータサービスを作成する](create-a-data-service-using-rp-wcf-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="40519-106">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](create-a-data-service-using-rp-wcf-data-services.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="40519-107">例</span><span class="sxs-lookup"><span data-stu-id="40519-107">Example</span></span>  
 <span data-ttu-id="40519-108">次の例では、`Order` 型の両方のプロパティが既存の Atom 要素にマップされます。</span><span class="sxs-lookup"><span data-stu-id="40519-108">In the following example, both properties of the `Order` type are mapped to existing Atom elements.</span></span> <span data-ttu-id="40519-109">`Product` 型の `Item` プロパティは、別の名前空間のカスタム フィード属性にマップされます。</span><span class="sxs-lookup"><span data-stu-id="40519-109">The `Product` property of the `Item` type is mapped to a custom feed attribute in a separate namespace.</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a><span data-ttu-id="40519-110">例</span><span class="sxs-lookup"><span data-stu-id="40519-110">Example</span></span>  
 <span data-ttu-id="40519-111">前の例では、URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` に次の結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="40519-111">The previous example returns the following result for the URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a><span data-ttu-id="40519-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="40519-112">See also</span></span>

- [<span data-ttu-id="40519-113">リフレクション プロバイダー</span><span class="sxs-lookup"><span data-stu-id="40519-113">Reflection Provider</span></span>](reflection-provider-wcf-data-services.md)
