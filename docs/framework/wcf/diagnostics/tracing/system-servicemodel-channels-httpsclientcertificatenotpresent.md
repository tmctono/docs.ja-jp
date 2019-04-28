---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 15ae13563cfcfb3765559cafb2d31bd6482df7b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767313"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="3b60e-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="3b60e-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="3b60e-103">クライアント証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="3b60e-103">Client certificate is required.</span></span> <span data-ttu-id="3b60e-104">要求内で証明書が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="3b60e-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3b60e-105">説明</span><span class="sxs-lookup"><span data-stu-id="3b60e-105">Description</span></span>  
 <span data-ttu-id="3b60e-106">このトレースは、HTTPS リスナーがクライアント証明書に関連付けられていない HTTPS 要求を受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="3b60e-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="3b60e-107">リスナーはすべての HTTPS 要求においてクライアント証明書を必要とするように構成されているため、リスナーによるクライアントの信頼性の検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="3b60e-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b60e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b60e-108">See also</span></span>

- [<span data-ttu-id="3b60e-109">トレース</span><span class="sxs-lookup"><span data-stu-id="3b60e-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="3b60e-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3b60e-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3b60e-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="3b60e-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
