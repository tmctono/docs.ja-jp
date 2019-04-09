---
title: メタデータ エンドポイントを公開する
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 143a46ce18a0d9dee89bbbffac9be9a467e951df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121733"
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="22040-102">メタデータ エンドポイントを公開する</span><span class="sxs-lookup"><span data-stu-id="22040-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="22040-103">Windows Communication Foundation (WCF) サービスは、1 つまたは複数のメタデータ エンドポイントを発行することによって、メタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="22040-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="22040-104">サービス メタデータを公開すると、そのメタデータで WS-MetadataExchange (MEX) や HTTP/GET 要求などの標準化プロトコルを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="22040-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="22040-105">メタデータのエンドポイントは、アドレス、バインディング、およびコントラクトを持つ他のサービス エンドポイントに似ており、構成またはコードを使用してサービス ホストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="22040-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="22040-106">メタデータ エンドポイントの公開を有効にするには、<xref:System.ServiceModel.Description.ServiceMetadataBehavior> サービス動作をサービスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22040-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22040-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="22040-107">In This Section</span></span>  
 [<span data-ttu-id="22040-108">方法: 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="22040-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="22040-109">クライアントは、Ws-metadataexchange または HTTP/GET 要求を使用して、使用してメタデータを取得できるように、メタデータを公開する WCF サービスを構成する方法を示します、`?wsdl`クエリ文字列。</span><span class="sxs-lookup"><span data-stu-id="22040-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="22040-110">方法: コードを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="22040-110">How to: Publish Metadata for a Service Using Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="22040-111">クライアントは、Ws-metadataexchange または HTTP/GET 要求を使用して、使用してメタデータを取得できるように、コード内の WCF サービスのメタデータの公開を有効にする方法を示します、`?wsdl`クエリ文字列。</span><span class="sxs-lookup"><span data-stu-id="22040-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22040-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="22040-112">See also</span></span>

- [<span data-ttu-id="22040-113">メタデータの公開</span><span class="sxs-lookup"><span data-stu-id="22040-113">Publishing Metadata</span></span>](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
