---
title: メタデータ エンドポイントを公開する
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 4c6ac81f0c97415dc21ff3346178dd1e9936b7a5
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319892"
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="430e8-102">メタデータ エンドポイントを公開する</span><span class="sxs-lookup"><span data-stu-id="430e8-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="430e8-103">Windows Communication Foundation (WCF) サービスは、1つまたは複数のメタデータエンドポイントを公開することによってメタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="430e8-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="430e8-104">サービス メタデータを公開すると、そのメタデータで WS-MetadataExchange (MEX) や HTTP/GET 要求などの標準化プロトコルを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="430e8-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="430e8-105">メタデータのエンドポイントは、アドレス、バインディング、およびコントラクトを持つ他のサービス エンドポイントに似ており、構成またはコードを使用してサービス ホストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="430e8-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="430e8-106">メタデータ エンドポイントの公開を有効にするには、<xref:System.ServiceModel.Description.ServiceMetadataBehavior> サービス動作をサービスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="430e8-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="430e8-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="430e8-107">In This Section</span></span>  
 [<span data-ttu-id="430e8-108">方法 : 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="430e8-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="430e8-109">Ws-metadataexchange または HTTP/GET 要求を使用して、クライアントが `?wsdl` クエリ文字列を使用してメタデータを取得できるように、メタデータを公開するように WCF サービスを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="430e8-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="430e8-110">方法 : コードを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="430e8-110">How to: Publish Metadata for a Service Using Code</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="430e8-111">WCF サービスのメタデータ公開をコードで有効にする方法を示します。これにより、クライアントは、Ws-metadataexchange または HTTP/GET 要求を使用して、`?wsdl` クエリ文字列を使用してメタデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="430e8-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="430e8-112">参照</span><span class="sxs-lookup"><span data-stu-id="430e8-112">See also</span></span>

- [<span data-ttu-id="430e8-113">メタデータの公開</span><span class="sxs-lookup"><span data-stu-id="430e8-113">Publishing Metadata</span></span>](./feature-details/publishing-metadata.md)
