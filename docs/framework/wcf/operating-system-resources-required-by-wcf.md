---
title: WCF に必要なオペレーティング システム リソース
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100952"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="615c1-102">WCF に必要なオペレーティング システム リソース</span><span class="sxs-lookup"><span data-stu-id="615c1-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="615c1-103">Windows Communication Foundation (WCF) は、関数へのオペレーティング システムによって提供されるいくつかのリソースに依存します。</span><span class="sxs-lookup"><span data-stu-id="615c1-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="615c1-104">このリソースを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="615c1-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="615c1-105">リソース</span><span class="sxs-lookup"><span data-stu-id="615c1-105">Resource</span></span>|<span data-ttu-id="615c1-106">説明</span><span class="sxs-lookup"><span data-stu-id="615c1-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="615c1-107">Microsoft 分散トランザクション コーディネーター (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="615c1-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="615c1-108">OleTx トランザクションをサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="615c1-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="615c1-109">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="615c1-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="615c1-110">IIS を使用してアプリケーションをホストする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="615c1-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="615c1-111">Windows プロセス アクティブ化サービス (WAS)</span><span class="sxs-lookup"><span data-stu-id="615c1-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="615c1-112">WAS を使用してアプリケーションをホストする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="615c1-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="615c1-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="615c1-113">See also</span></span>

- [<span data-ttu-id="615c1-114">システム要件</span><span class="sxs-lookup"><span data-stu-id="615c1-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
