---
title: <message> の <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: db6717022bf3af0c4922818668595dd3937e9c71
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "61704408"
---
# <a name="claimtyperequirements-for-message"></a><span data-ttu-id="e0ffb-102">\<message> の \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="e0ffb-102">\<claimTypeRequirements> for \<message></span></span>
<span data-ttu-id="e0ffb-103">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0ffb-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="e0ffb-104">このコレクションは、発行されたトークンに含める必要のある必須クレームとオプション クレームを指定するために、サービスによって使用されます。クライアントは、発行されたトークンを使用してサービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e0ffb-104">The collection is used by the service to specify any required and optional claims which must be in the issued token the client uses to access the service.</span></span> <span data-ttu-id="e0ffb-105">WSDL の公開が有効になっていても、発行されるトークンに指定されたクレームの種類が含まれていることを WCF が要求しない場合、サービスは必須クレームの種類をメタデータで公開します。</span><span class="sxs-lookup"><span data-stu-id="e0ffb-105">The service exposes the required claim types in metadata if WSDL publishing is enabled but WCF does not require the issued token contain the specified claim types.</span></span> <span data-ttu-id="e0ffb-106">存在している必須クレームの種類を実施しようとするサービスは、承認ポリシーを使用して実施します。</span><span class="sxs-lookup"><span data-stu-id="e0ffb-106">Services wishing to enforce required claim types are present should do using authorization policy.</span></span>  
  
 <span data-ttu-id="e0ffb-107">フェデレーション クライアント上では、このコレクションには、発行されたトークンに対するクライアントの要求の中でセキュリティ トークン サービスに送信される、必須クレームとオプション クレームのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0ffb-107">On federated clients, this collection contains the list of required and optional claims which is sent to the security token service in the client’s request for an issued token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ffb-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0ffb-108">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
