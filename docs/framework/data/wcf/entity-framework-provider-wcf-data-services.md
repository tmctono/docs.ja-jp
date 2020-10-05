---
title: Entity Framework プロバイダー (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: cb7bd7e793f73fc34057150ee5217dba6653237e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172646"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Entity Framework プロバイダー (WCF Data Services)

WCF Data Services と同様に、ADO.NET Entity Framework は、エンティティ リレーションシップ モデルの型である Entity Data Model をベースにしています。 Entity Framework では、Entity Data Model の実装 ("*概念モデル*" と呼ばれます) に対する操作が、データ ソースに対する同等の操作に変換されます。 このことから、Entity Framework はリレーショナル データに基づくデータ サービスの理想的なプロバイダーとして使用でき、また、Entity Framework をサポートするデータ プロバイダーが存在するデータベースであれば、WCF Data Services で使用できます。 現在 Entity Framework がサポートされているデータ ソースの一覧については、「[Entity Framework プロバイダー](/ef/ef6/fundamentals/providers/)」を参照してください。
  
 概念モデルでは、エンティティ コンテナーはサービスのルートです。 データ サービスでデータを公開する前に、Entity Framework で概念モデルを定義する必要があります。 詳細については、[ADO.NET Entity Framework データ ソースを使用してデータ サービスを作成する](create-a-data-service-using-an-adonet-ef-data-wcf.md)」を参照してください。  
  
 WCF Data Services では、エンティティのコンカレンシー トークンを定義できるようにすることで、オプティミスティック コンカレンシー モデルがサポートされています。 このコンカレンシー トークンは、エンティティの 1 つ以上のプロパティが含まれており、要求、更新、または削除されているデータに対して行われた変更があるかどうかを判断するためにデータ サービスによって使用されます。 要求内の eTag から取得したトークンの値がエンティティの現在の値と異なる場合、データ サービスで例外が発生します。 プロパティがコンカレンシー トークンの一部であることを示す場合、Entity Framework プロバイダーで定義されているデータ モデルに属性 `ConcurrencyMode="Fixed"` を適用する必要があります。 コンカレンシー トークンには、キー プロパティまたはナビゲーション プロパティを含めることはできません。 詳細については、「[データ サービスの更新](updating-the-data-service-wcf-data-services.md)」を参照してください。  
  
 Entity Framework について詳しくは、「[Entity Framework の概要](../adonet/ef/overview.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目

- [Data Services プロバイダー](data-services-providers-wcf-data-services.md)
- [リフレクション プロバイダー](reflection-provider-wcf-data-services.md)
- [Entity Data Model](../adonet/entity-data-model.md)
