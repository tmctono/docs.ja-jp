---
title: WCF に必要なオペレーティング システム リソース
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: c2c26d769424a8d0655591cb10b4b13df8a15884
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961136"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="c1515-102">WCF に必要なオペレーティング システム リソース</span><span class="sxs-lookup"><span data-stu-id="c1515-102">Operating System Resources Required by WCF</span></span>

<span data-ttu-id="c1515-103">Windows Communication Foundation (WCF) は、オペレーティングシステムによって機能するために提供されるいくつかのリソースに依存します。</span><span class="sxs-lookup"><span data-stu-id="c1515-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="c1515-104">次の表は、これらのリソースを示しています。</span><span class="sxs-lookup"><span data-stu-id="c1515-104">The following table lists those resources:</span></span>

|<span data-ttu-id="c1515-105">リソース</span><span class="sxs-lookup"><span data-stu-id="c1515-105">Resource</span></span>|<span data-ttu-id="c1515-106">説明</span><span class="sxs-lookup"><span data-stu-id="c1515-106">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="c1515-107">Microsoft 分散トランザクション コーディネーター (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="c1515-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="c1515-108">OleTx トランザクションをサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="c1515-108">Required to support OleTx transactions.</span></span>|
|<span data-ttu-id="c1515-109">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="c1515-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="c1515-110">IIS を使用してアプリケーションをホストする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="c1515-110">Required if you want to use IIS to host your application.</span></span>|
|<span data-ttu-id="c1515-111">Windows プロセス アクティブ化サービス (WAS)</span><span class="sxs-lookup"><span data-stu-id="c1515-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="c1515-112">WAS を使用してアプリケーションをホストする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="c1515-112">Required if you want to use WAS to host your application.</span></span>|
