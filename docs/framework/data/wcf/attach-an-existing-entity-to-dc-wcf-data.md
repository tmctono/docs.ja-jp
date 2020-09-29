---
title: '方法: 既存のエンティティを DataServiceContext にアタッチする (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 69ca64f4ab3470c1a4f58c582b31c06aed9cadd5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166132"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>方法: 既存のエンティティを DataServiceContext にアタッチする (WCF Data Services)

データ サービスにエンティティが既に存在する場合、クエリを最初に実行することなく、WCF Data Services クライアント ライブラリを使用して、エンティティを表すオブジェクトを <xref:System.Data.Services.Client.DataServiceContext> に直接アタッチできます。 詳細については、「[データ サービスの更新](updating-the-data-service-wcf-data-services.md)」を参照してください。  
  
 このトピックの例では、Northwind サンプル データ サービスおよび自動生成されたクライアント データ サービス クラスを使用します。 このサービスとクライアント データ クラスは、「[WCF Data Services クイックスタート](quickstart-wcf-data-services.md)」を完了すると作成されます。  
  
## <a name="example"></a>例  

 次の例は、データ サービスに保存する変更を含む既存の `Customer` オブジェクトを作成する方法を示します。 オブジェクトがコンテキストにアタッチされ、<xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> メソッドが呼び出される前に、<xref:System.Data.Services.Client.EntityStates.Modified> メソッドが呼び出されてアタッチされたオブジェクトが <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> としてマークされます。  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>関連項目

- [WCF Data Services クライアント ライブラリ](wcf-data-services-client-library.md)
