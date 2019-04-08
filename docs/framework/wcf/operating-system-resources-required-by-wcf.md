---
title: WCF に必要なオペレーティング システム リソース
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100952"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="d8305-102">WCF に必要なオペレーティング システム リソース</span><span class="sxs-lookup"><span data-stu-id="d8305-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="d8305-103">Windows Communication Foundation (WCF) は、関数へのオペレーティング システムによって提供されるいくつかのリソースに依存します。</span><span class="sxs-lookup"><span data-stu-id="d8305-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="d8305-104">このリソースを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d8305-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="d8305-105">リソース</span><span class="sxs-lookup"><span data-stu-id="d8305-105">Resource</span></span>|<span data-ttu-id="d8305-106">説明</span><span class="sxs-lookup"><span data-stu-id="d8305-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d8305-107">Microsoft 分散トランザクション コーディネーター (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="d8305-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="d8305-108">OleTx トランザクションをサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="d8305-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="d8305-109">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="d8305-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="d8305-110">IIS を使用してアプリケーションをホストする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="d8305-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="d8305-111">Windows プロセス アクティブ化サービス (WAS)</span><span class="sxs-lookup"><span data-stu-id="d8305-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="d8305-112">WAS を使用してアプリケーションをホストする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="d8305-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8305-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8305-113">See also</span></span>

- [<span data-ttu-id="d8305-114">システム要件</span><span class="sxs-lookup"><span data-stu-id="d8305-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
