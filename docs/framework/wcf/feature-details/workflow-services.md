---
title: ワークフロー サービス
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: e7295041fe4b17e7e2b1560704badf20992d4b92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929702"
---
# <a name="workflow-services"></a><span data-ttu-id="8f649-102">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="8f649-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="8f649-103">では、ワークフロー ベースのサービスを XAML で宣言によって記述できます。</span><span class="sxs-lookup"><span data-stu-id="8f649-103">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="8f649-104">サービスを実装するワークフローの定義、およびサービスが公開するエンドポイントの説明を、すべて XAML で実行できます。</span><span class="sxs-lookup"><span data-stu-id="8f649-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="8f649-105">このセクションの各トピックでは、宣言によるサービスの記述をサポートするプログラミング モデルについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f649-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8f649-106">In This Section</span></span>  
 [<span data-ttu-id="8f649-107">ワークフロー サービスの概要</span><span class="sxs-lookup"><span data-stu-id="8f649-107">Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services-overview.md)  
 <span data-ttu-id="8f649-108">ワークフロー サービスの作成およびホストに関与するコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="8f649-109">メッセージング アクティビティ</span><span class="sxs-lookup"><span data-stu-id="8f649-109">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 <span data-ttu-id="8f649-110">ワークフローがメッセージを送受信できるようにするアクティビティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="8f649-111">方法: メッセージング アクティビティでワークフロー サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f649-111">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="8f649-112">メッセージング アクティビティを使用してワークフロー サービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="8f649-113">方法: ワークフロー アプリケーションからサービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8f649-113">How To: Access a Service From a Workflow Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="8f649-114">ワークフロー アプリケーションからサービスを呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="8f649-115">相関関係</span><span class="sxs-lookup"><span data-stu-id="8f649-115">Correlation</span></span>](../../../../docs/framework/wcf/feature-details/correlation.md)  
 <span data-ttu-id="8f649-116">相関関係によってメッセージを相互に、またはインスタンスにマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="8f649-117">順番を無視したメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="8f649-117">Out-of-Order Message Processing</span></span>](../../../../docs/framework/wcf/feature-details/out-of-order-message-processing.md)  
 <span data-ttu-id="8f649-118">順番を無視したメッセージを受け入れるようにサービスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="8f649-119">コントラクト優先ワークフロー サービスの開発</span><span class="sxs-lookup"><span data-stu-id="8f649-119">Contract First Workflow Service Development</span></span>](../../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="8f649-120">既存のサービス コントラクトに基づいてワークフロー サービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-120">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="8f649-121">方法: 既存のサービス コントラクトを使用するワークフロー サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f649-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="8f649-122">既存のサービス コントラクトを使用してワークフロー サービスを作成する例を操作手順に従って説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-122">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="8f649-123">ワークフロー サービスのホストの概要</span><span class="sxs-lookup"><span data-stu-id="8f649-123">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 <span data-ttu-id="8f649-124">ワークフロー サービスのホストのさまざまな側面について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-124">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="8f649-125">ワークフロー内でのコントラクトの使用</span><span class="sxs-lookup"><span data-stu-id="8f649-125">Using Contracts in Workflow</span></span>](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)  
 <span data-ttu-id="8f649-126">コントラクトおよびコントラクト推論のさまざまな種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f649-126">Describes the different types of contracts and contract inference.</span></span>
