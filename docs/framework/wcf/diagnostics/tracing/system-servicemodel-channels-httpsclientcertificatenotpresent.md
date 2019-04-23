---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 15ae13563cfcfb3765559cafb2d31bd6482df7b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201183"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="2e35f-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="2e35f-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="2e35f-103">クライアント証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e35f-103">Client certificate is required.</span></span> <span data-ttu-id="2e35f-104">要求内で証明書が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="2e35f-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2e35f-105">説明</span><span class="sxs-lookup"><span data-stu-id="2e35f-105">Description</span></span>  
 <span data-ttu-id="2e35f-106">このトレースは、HTTPS リスナーがクライアント証明書に関連付けられていない HTTPS 要求を受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="2e35f-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="2e35f-107">リスナーはすべての HTTPS 要求においてクライアント証明書を必要とするように構成されているため、リスナーによるクライアントの信頼性の検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2e35f-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e35f-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e35f-108">See also</span></span>

- [<span data-ttu-id="2e35f-109">トレース</span><span class="sxs-lookup"><span data-stu-id="2e35f-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2e35f-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2e35f-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2e35f-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="2e35f-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
