---
title: 基本的なプログラミング ライフサイクル
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: 6d9ea3b877e7c735cf789039b2a6956037372888
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782409"
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="76ae4-102">基本的なプログラミング ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="76ae4-102">Basic Programming Lifecycle</span></span>
<span data-ttu-id="76ae4-103">Windows Communication Foundation (WCF) は、アプリケーションまたは異なるアプリケーション プラットフォームで、インターネット経由で、同じコンピューターでがかどうかとの通信を使用できます。</span><span class="sxs-lookup"><span data-stu-id="76ae4-103">Windows Communication Foundation (WCF) enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="76ae4-104">このトピックでは、WCF アプリケーションを構築するために必要なタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-104">This topic outlines the tasks that are required to build a WCF application.</span></span> <span data-ttu-id="76ae4-105">実際のサンプル アプリケーションでは、次を参照してください。[チュートリアル入門](../../../docs/framework/wcf/getting-started-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-105">For a working sample application, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="76ae4-106">基本的なタスク</span><span class="sxs-lookup"><span data-stu-id="76ae4-106">The Basic Tasks</span></span>  
 <span data-ttu-id="76ae4-107">基本的な作業は、次の順序で行います。</span><span class="sxs-lookup"><span data-stu-id="76ae4-107">The basic tasks to perform are, in order:</span></span>  
  
1. <span data-ttu-id="76ae4-108">サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-108">Define the service contract.</span></span> <span data-ttu-id="76ae4-109">サービス コントラクトでは、サービスの署名、交換するデータ、およびコントラクトに必要なその他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> <span data-ttu-id="76ae4-110">詳細については、次を参照してください。 [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md)します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-110">For more information, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
2. <span data-ttu-id="76ae4-111">コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-111">Implement the contract.</span></span> <span data-ttu-id="76ae4-112">サービス コントラクトを実装するには、そのコントラクトを実装するクラスを作成し、ランタイムに必要なカスタム動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> <span data-ttu-id="76ae4-113">詳細については、次を参照してください。 [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md)します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-113">For more information, see [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
3. <span data-ttu-id="76ae4-114">エンドポイントおよびその他の動作情報を指定して、サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-114">Configure the service by specifying endpoints and other behavior information.</span></span> <span data-ttu-id="76ae4-115">詳細については、次を参照してください。[サービスを構成する](../../../docs/framework/wcf/configuring-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-115">For more information, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
4. <span data-ttu-id="76ae4-116">サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="76ae4-116">Host the service.</span></span> <span data-ttu-id="76ae4-117">詳細については、次を参照してください。[ホスティング サービス](../../../docs/framework/wcf/hosting-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-117">For more information, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
5. <span data-ttu-id="76ae4-118">クライアント アプリケーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-118">Build a client application.</span></span> <span data-ttu-id="76ae4-119">詳細については、次を参照してください。[クライアントを構築する](../../../docs/framework/wcf/building-clients.md)します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-119">For more information, see [Building Clients](../../../docs/framework/wcf/building-clients.md).</span></span>  
  
 <span data-ttu-id="76ae4-120">このセクションのトピックではこの順に従って説明しますが、手順を最初から実行しないシナリオもあります。</span><span class="sxs-lookup"><span data-stu-id="76ae4-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="76ae4-121">たとえば、既存のサービスを使用するクライアントを構築する場合は、手順 5. から開始します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="76ae4-122">また、既存のクライアント アプリケーションが使用するサービスを構築する場合は、手順 5. を省略できます。</span><span class="sxs-lookup"><span data-stu-id="76ae4-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="76ae4-123">サービス コントラクトの作成に慣れているが、参照することも[拡張機能の概要](../../../docs/framework/wcf/introduction-to-extensibility.md)します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](../../../docs/framework/wcf/introduction-to-extensibility.md).</span></span> <span data-ttu-id="76ae4-124">確認して、サービスに関する問題があれば、 [WCF トラブルシューティング クイック スタート](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)を同じまたは類似した問題があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="76ae4-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ae4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="76ae4-125">See also</span></span>

- [<span data-ttu-id="76ae4-126">サービス コントラクトの実装</span><span class="sxs-lookup"><span data-stu-id="76ae4-126">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
