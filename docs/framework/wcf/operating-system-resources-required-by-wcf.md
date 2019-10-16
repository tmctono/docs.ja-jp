---
title: WCF に必要なオペレーティング システム リソース
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: ac9bd5ed7c2092720c6521d0f78185c3fbf9f94b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318940"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="e7036-102">WCF に必要なオペレーティング システム リソース</span><span class="sxs-lookup"><span data-stu-id="e7036-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="e7036-103">Windows Communication Foundation (WCF) は、オペレーティングシステムによって機能するために提供されるいくつかのリソースに依存します。</span><span class="sxs-lookup"><span data-stu-id="e7036-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="e7036-104">このリソースを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e7036-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="e7036-105">リソース</span><span class="sxs-lookup"><span data-stu-id="e7036-105">Resource</span></span>|<span data-ttu-id="e7036-106">説明</span><span class="sxs-lookup"><span data-stu-id="e7036-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e7036-107">Microsoft 分散トランザクション コーディネーター (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="e7036-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="e7036-108">OleTx トランザクションをサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="e7036-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="e7036-109">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="e7036-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="e7036-110">IIS を使用してアプリケーションをホストする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="e7036-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="e7036-111">Windows プロセス アクティブ化サービス (WAS)</span><span class="sxs-lookup"><span data-stu-id="e7036-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="e7036-112">WAS を使用してアプリケーションをホストする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="e7036-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7036-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7036-113">See also</span></span>

- [<span data-ttu-id="e7036-114">システム要件</span><span class="sxs-lookup"><span data-stu-id="e7036-114">System Requirements</span></span>](wcf-system-requirements.md)
