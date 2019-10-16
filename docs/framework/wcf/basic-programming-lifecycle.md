---
title: 基本的なプログラミング ライフサイクル
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: fe578ba3c655c9c9ea8398b9b2e4d4f974153c8e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320824"
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="1d699-102">基本的なプログラミング ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="1d699-102">Basic Programming Lifecycle</span></span>
<span data-ttu-id="1d699-103">Windows Communication Foundation (WCF) を使用すると、アプリケーションは、同じコンピューター上、インターネット上、または異なるアプリケーションプラットフォーム上にあるかどうかを通信できます。</span><span class="sxs-lookup"><span data-stu-id="1d699-103">Windows Communication Foundation (WCF) enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="1d699-104">このトピックでは、WCF アプリケーションの構築に必要なタスクの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="1d699-104">This topic outlines the tasks that are required to build a WCF application.</span></span> <span data-ttu-id="1d699-105">実際のサンプルアプリケーションについては、[はじめにチュートリアル](getting-started-tutorial.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d699-105">For a working sample application, see [Getting Started Tutorial](getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="1d699-106">基本的なタスク</span><span class="sxs-lookup"><span data-stu-id="1d699-106">The Basic Tasks</span></span>  
 <span data-ttu-id="1d699-107">基本的な作業は、次の順序で行います。</span><span class="sxs-lookup"><span data-stu-id="1d699-107">The basic tasks to perform are, in order:</span></span>  
  
1. <span data-ttu-id="1d699-108">サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="1d699-108">Define the service contract.</span></span> <span data-ttu-id="1d699-109">サービス コントラクトでは、サービスの署名、交換するデータ、およびコントラクトに必要なその他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d699-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> <span data-ttu-id="1d699-110">詳細については、「[サービスコントラクトの設計](designing-service-contracts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d699-110">For more information, see [Designing Service Contracts](designing-service-contracts.md).</span></span>  
  
2. <span data-ttu-id="1d699-111">コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="1d699-111">Implement the contract.</span></span> <span data-ttu-id="1d699-112">サービス コントラクトを実装するには、そのコントラクトを実装するクラスを作成し、ランタイムに必要なカスタム動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d699-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> <span data-ttu-id="1d699-113">詳細については、「[サービスコントラクトの実装](implementing-service-contracts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d699-113">For more information, see [Implementing Service Contracts](implementing-service-contracts.md).</span></span>  
  
3. <span data-ttu-id="1d699-114">エンドポイントおよびその他の動作情報を指定して、サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="1d699-114">Configure the service by specifying endpoints and other behavior information.</span></span> <span data-ttu-id="1d699-115">詳細については、「[サービスの構成](configuring-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d699-115">For more information, see [Configuring Services](configuring-services.md).</span></span>  
  
4. <span data-ttu-id="1d699-116">サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="1d699-116">Host the service.</span></span> <span data-ttu-id="1d699-117">詳細については、「[ホスティングサービス](hosting-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d699-117">For more information, see [Hosting Services](hosting-services.md).</span></span>  
  
5. <span data-ttu-id="1d699-118">クライアント アプリケーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="1d699-118">Build a client application.</span></span> <span data-ttu-id="1d699-119">詳細については、「[クライアントの構築](building-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d699-119">For more information, see [Building Clients](building-clients.md).</span></span>  
  
 <span data-ttu-id="1d699-120">このセクションのトピックではこの順に従って説明しますが、手順を最初から実行しないシナリオもあります。</span><span class="sxs-lookup"><span data-stu-id="1d699-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="1d699-121">たとえば、既存のサービスを使用するクライアントを構築する場合は、手順 5. から開始します。</span><span class="sxs-lookup"><span data-stu-id="1d699-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="1d699-122">また、既存のクライアント アプリケーションが使用するサービスを構築する場合は、手順 5. を省略できます。</span><span class="sxs-lookup"><span data-stu-id="1d699-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="1d699-123">サービスコントラクトの開発に慣れたら、「[拡張機能の概要」を](introduction-to-extensibility.md)参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="1d699-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](introduction-to-extensibility.md).</span></span> <span data-ttu-id="1d699-124">サービスで問題が発生した場合は、 [WCF トラブルシューティングクイックスタート](wcf-troubleshooting-quickstart.md)をチェックして、他の問題が同一または類似しているかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1d699-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d699-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d699-125">See also</span></span>

- [<span data-ttu-id="1d699-126">サービス コントラクトの実装</span><span class="sxs-lookup"><span data-stu-id="1d699-126">Implementing Service Contracts</span></span>](implementing-service-contracts.md)
