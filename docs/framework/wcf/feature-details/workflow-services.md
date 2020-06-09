---
title: ワークフロー サービス
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: c7a5c6245702497fcd75341b3ff7ba08dc190fa5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600128"
---
# <a name="workflow-services"></a><span data-ttu-id="b0f34-102">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="b0f34-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="b0f34-103">では、ワークフロー ベースのサービスを XAML で宣言によって記述できます。</span><span class="sxs-lookup"><span data-stu-id="b0f34-103">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="b0f34-104">サービスを実装するワークフローの定義、およびサービスが公開するエンドポイントの説明を、すべて XAML で実行できます。</span><span class="sxs-lookup"><span data-stu-id="b0f34-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="b0f34-105">このセクションの各トピックでは、宣言によるサービスの記述をサポートするプログラミング モデルについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0f34-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b0f34-106">In This Section</span></span>  
 [<span data-ttu-id="b0f34-107">ワークフロー サービスの概要</span><span class="sxs-lookup"><span data-stu-id="b0f34-107">Workflow Services Overview</span></span>](workflow-services-overview.md)  
 <span data-ttu-id="b0f34-108">ワークフロー サービスの作成およびホストに関与するコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="b0f34-109">メッセージング アクティビティ</span><span class="sxs-lookup"><span data-stu-id="b0f34-109">Messaging Activities</span></span>](messaging-activities.md)  
 <span data-ttu-id="b0f34-110">ワークフローがメッセージを送受信できるようにするアクティビティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="b0f34-111">方法: メッセージング アクティビティを使用してワークフロー サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="b0f34-111">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="b0f34-112">メッセージング アクティビティを使用してワークフロー サービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="b0f34-113">方法: ワークフロー アプリケーションからサービスにアクセスする</span><span class="sxs-lookup"><span data-stu-id="b0f34-113">How To: Access a Service From a Workflow Application</span></span>](how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="b0f34-114">ワークフロー アプリケーションからサービスを呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="b0f34-115">関連付け</span><span class="sxs-lookup"><span data-stu-id="b0f34-115">Correlation</span></span>](correlation.md)  
 <span data-ttu-id="b0f34-116">相関関係によってメッセージを相互に、またはインスタンスにマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="b0f34-117">順番を無視したメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="b0f34-117">Out-of-Order Message Processing</span></span>](out-of-order-message-processing.md)  
 <span data-ttu-id="b0f34-118">順番を無視したメッセージを受け入れるようにサービスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="b0f34-119">コントラクト優先ワークフロー サービスの開発</span><span class="sxs-lookup"><span data-stu-id="b0f34-119">Contract First Workflow Service Development</span></span>](../../windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="b0f34-120">既存のサービス コントラクトに基づいてワークフロー サービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-120">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="b0f34-121">方法: 既存のサービス コントラクトを使用するワークフロー サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="b0f34-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="b0f34-122">既存のサービス コントラクトを使用してワークフロー サービスを作成する例を操作手順に従って説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-122">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="b0f34-123">ワークフロー サービスのホストの概要</span><span class="sxs-lookup"><span data-stu-id="b0f34-123">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)  
 <span data-ttu-id="b0f34-124">ワークフロー サービスのホストのさまざまな側面について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-124">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="b0f34-125">ワークフロー内でのコントラクトの使用</span><span class="sxs-lookup"><span data-stu-id="b0f34-125">Using Contracts in Workflow</span></span>](using-contracts-in-workflow.md)  
 <span data-ttu-id="b0f34-126">コントラクトおよびコントラクト推論のさまざまな種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f34-126">Describes the different types of contracts and contract inference.</span></span>
