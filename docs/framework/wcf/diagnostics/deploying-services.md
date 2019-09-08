---
title: サービスの配置
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 684b781c568518cfb321d8021e4f7062e855e6aa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798144"
---
# <a name="deploying-services"></a><span data-ttu-id="da553-102">サービスの配置</span><span class="sxs-lookup"><span data-stu-id="da553-102">Deploying Services</span></span>
<span data-ttu-id="da553-103">このトピックでは、Windows Communication Foundation (WCF) アプリケーションを実行時環境に配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da553-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="da553-104">アプリケーションのホスト環境の選択</span><span class="sxs-lookup"><span data-stu-id="da553-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="da553-105">WCF サービスは、マネージコードをサポートする任意の Windows プロセスで実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="da553-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="da553-106">アクティブにするには、サービスを作成してそのコンテキストと有効期間を制御するランタイム環境内で、サービスをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da553-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="da553-107">ホスティング環境の範囲は、最も単純なコンソール アプリケーション内、Windows サービスやインターネット インフォメーション サービス (IIS) のようなサーバー環境、あるいは Windows アクティブ化サービス (WAS) で管理されるワーカー プロセス内での実行にまで及びます。</span><span class="sxs-lookup"><span data-stu-id="da553-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="da553-108">WCF アプリケーションのさまざまなホスティングオプションを確認するには、「[ホスティングサービス](../hosting-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da553-108">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da553-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="da553-109">See also</span></span>

- [<span data-ttu-id="da553-110">ホスティング</span><span class="sxs-lookup"><span data-stu-id="da553-110">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="da553-111">ホスティング サービス</span><span class="sxs-lookup"><span data-stu-id="da553-111">Hosting Services</span></span>](../hosting-services.md)
