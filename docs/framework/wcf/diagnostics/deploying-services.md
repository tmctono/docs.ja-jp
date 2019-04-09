---
title: サービスの配置
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 2c3cd17b597fafcd02b9155089bc583fafbc9dea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085762"
---
# <a name="deploying-services"></a><span data-ttu-id="a76cb-102">サービスの配置</span><span class="sxs-lookup"><span data-stu-id="a76cb-102">Deploying Services</span></span>
<span data-ttu-id="a76cb-103">このトピックでは、実行時環境に Windows Communication Foundation (WCF) アプリケーションをデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a76cb-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="a76cb-104">アプリケーションのホスト環境の選択</span><span class="sxs-lookup"><span data-stu-id="a76cb-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="a76cb-105">マネージ コードをサポートする任意の Windows プロセスで実行するのには、WCF サービスが設計されています。</span><span class="sxs-lookup"><span data-stu-id="a76cb-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="a76cb-106">アクティブにするには、サービスを作成してそのコンテキストと有効期間を制御するランタイム環境内で、サービスをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76cb-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="a76cb-107">ホスティング環境の範囲は、最も単純なコンソール アプリケーション内、Windows サービスやインターネット インフォメーション サービス (IIS) のようなサーバー環境、あるいは Windows アクティブ化サービス (WAS) で管理されるワーカー プロセス内での実行にまで及びます。</span><span class="sxs-lookup"><span data-stu-id="a76cb-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="a76cb-108">WCF アプリケーションのさまざまなホスティング オプションを確認するを参照してください。[ホスティング サービス](../../../../docs/framework/wcf/hosting-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="a76cb-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76cb-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a76cb-109">See also</span></span>

- [<span data-ttu-id="a76cb-110">ホスト</span><span class="sxs-lookup"><span data-stu-id="a76cb-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)
- [<span data-ttu-id="a76cb-111">ホスティング サービス</span><span class="sxs-lookup"><span data-stu-id="a76cb-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
