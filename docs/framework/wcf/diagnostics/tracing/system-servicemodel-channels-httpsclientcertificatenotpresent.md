---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 3e3bedca7a46f147ee3d9e143cea7e57095c99d1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602045"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="690ba-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="690ba-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="690ba-103">クライアント証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="690ba-103">Client certificate is required.</span></span> <span data-ttu-id="690ba-104">要求内で証明書が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="690ba-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="690ba-105">説明</span><span class="sxs-lookup"><span data-stu-id="690ba-105">Description</span></span>  
 <span data-ttu-id="690ba-106">このトレースは、HTTPS リスナーがクライアント証明書に関連付けられていない HTTPS 要求を受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="690ba-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="690ba-107">リスナーはすべての HTTPS 要求においてクライアント証明書を必要とするように構成されているため、リスナーによるクライアントの信頼性の検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="690ba-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="690ba-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="690ba-108">See also</span></span>

- [<span data-ttu-id="690ba-109">トレース</span><span class="sxs-lookup"><span data-stu-id="690ba-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="690ba-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="690ba-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="690ba-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="690ba-111">Administration and Diagnostics</span></span>](../index.md)
