---
title: '方法: リフレクション プロバイダーでフィードをカスタマイズする (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: fb22e87569a8e243813b3186232b6989abeb2a5e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161309"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>方法: リフレクション プロバイダーでフィードをカスタマイズする (WCF Data Services)

WCF Data Services では、データ サービス応答の Atom シリアル化をカスタマイズして、AtomPub プロトコルで定義されている未使用の要素にエンティティのプロパティをマップできます。 このトピックでは、リフレクション プロバイダーを使用して、定義されているデータ モデル内のエンティティ型のマッピング属性を定義する方法について説明します。 詳細については、「[フィードのカスタマイズ](feed-customization-wcf-data-services.md)」を参照してください。  
  
 次の例のデータ モデルは、トピック「[方法: リフレクション プロバイダーを使用してデータ サービスを作成する](create-a-data-service-using-rp-wcf-data-services.md)」で定義されています。  
  
## <a name="example"></a>例  

 次の例では、`Order` 型の両方のプロパティが既存の Atom 要素にマップされます。 `Product` 型の `Item` プロパティは、別の名前空間のカスタム フィード属性にマップされます。  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>例  

 前の例では、URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` に次の結果が返されます。  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>関連項目

- [リフレクション プロバイダー](reflection-provider-wcf-data-services.md)
