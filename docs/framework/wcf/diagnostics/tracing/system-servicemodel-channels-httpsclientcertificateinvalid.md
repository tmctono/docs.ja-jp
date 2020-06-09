---
title: System.ServiceModel.Channels.HttpsClientCertificateInvalid
ms.date: 03/30/2017
ms.assetid: 8884dda1-fa0e-4d2a-8079-7042c51b64ef
ms.openlocfilehash: 2437e89574d83a64e2690326ff2d2ba058234ec8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599556"
---
# <a name="systemservicemodelchannelshttpsclientcertificateinvalid"></a><span data-ttu-id="77c6d-102">System.ServiceModel.Channels.HttpsClientCertificateInvalid</span><span class="sxs-lookup"><span data-stu-id="77c6d-102">System.ServiceModel.Channels.HttpsClientCertificateInvalid</span></span>
<span data-ttu-id="77c6d-103">クライアント証明書が無効です。</span><span class="sxs-lookup"><span data-stu-id="77c6d-103">Client certificate is invalid.</span></span>  
  
## <a name="description"></a><span data-ttu-id="77c6d-104">説明</span><span class="sxs-lookup"><span data-stu-id="77c6d-104">Description</span></span>  
 <span data-ttu-id="77c6d-105">このトレースは、HTTPS リスナーが、クライアントによって提供された証明書が無効であることを検出したことを示します。</span><span class="sxs-lookup"><span data-stu-id="77c6d-105">This trace indicates that the certificate provided by the client was found to be invalid by the HTTPS listener.</span></span> <span data-ttu-id="77c6d-106">HTTPS リスナーは、この証明書を使用してクライアントの信頼性を検証しようとしていました。</span><span class="sxs-lookup"><span data-stu-id="77c6d-106">The HTTPS listener was attempting to validate the authenticity of the client using this certificate.</span></span> <span data-ttu-id="77c6d-107">サービスをホストしているサーバーによって証明書の証明機関が認識されないと、証明書は無効になります。</span><span class="sxs-lookup"><span data-stu-id="77c6d-107">A certificate could be invalid if its Certificate Authority is not recognized by the server hosting the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c6d-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="77c6d-108">See also</span></span>

- [<span data-ttu-id="77c6d-109">トレース</span><span class="sxs-lookup"><span data-stu-id="77c6d-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="77c6d-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="77c6d-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="77c6d-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="77c6d-111">Administration and Diagnostics</span></span>](../index.md)
