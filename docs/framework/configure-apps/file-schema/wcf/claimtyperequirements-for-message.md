---
title: <claimTypeRequirements> の <message>
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: db6717022bf3af0c4922818668595dd3937e9c71
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106562"
---
# <a name="claimtyperequirements-for-message"></a><span data-ttu-id="a4e9f-102">\<claimTypeRequirements> for \<message></span><span class="sxs-lookup"><span data-stu-id="a4e9f-102">\<claimTypeRequirements> for \<message></span></span>
<span data-ttu-id="a4e9f-103">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4e9f-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="a4e9f-104">このコレクションは、発行されたトークンに含める必要のある必須クレームとオプション クレームを指定するために、サービスによって使用されます。クライアントは、発行されたトークンを使用してサービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a4e9f-104">The collection is used by the service to specify any required and optional claims which must be in the issued token the client uses to access the service.</span></span> <span data-ttu-id="a4e9f-105">WSDL の公開が有効になっていても、発行されるトークンに指定されたクレームの種類が含まれていることを WCF が要求しない場合、サービスは必須クレームの種類をメタデータで公開します。</span><span class="sxs-lookup"><span data-stu-id="a4e9f-105">The service exposes the required claim types in metadata if WSDL publishing is enabled but WCF does not require the issued token contain the specified claim types.</span></span> <span data-ttu-id="a4e9f-106">存在している必須クレームの種類を実施しようとするサービスは、承認ポリシーを使用して実施します。</span><span class="sxs-lookup"><span data-stu-id="a4e9f-106">Services wishing to enforce required claim types are present should do using authorization policy.</span></span>  
  
 <span data-ttu-id="a4e9f-107">フェデレーション クライアント上では、このコレクションには、発行されたトークンに対するクライアントの要求の中でセキュリティ トークン サービスに送信される、必須クレームとオプション クレームのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4e9f-107">On federated clients, this collection contains the list of required and optional claims which is sent to the security token service in the client’s request for an issued token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4e9f-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4e9f-108">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
