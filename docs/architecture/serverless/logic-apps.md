---
title: Azure Logic Apps サーバーレスアプリ
description: クラウドサービスとオンプレミスシステムの間でアプリとデータを統合する、自動化されたスケーラブルなワークフローの構築を Azure Logic Apps できます。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577455"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="66cb9-103">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="66cb9-103">Azure Logic Apps</span></span>

<span data-ttu-id="66cb9-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)は、クラウドサービスとオンプレミスシステムの間でアプリとデータを統合するための自動化されたワークフローを構築するサーバーレスエンジンを提供します。</span><span class="sxs-lookup"><span data-stu-id="66cb9-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="66cb9-105">ワークフローは、ビジュアルデザイナーを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="66cb9-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="66cb9-106">イベントまたはタイマーに基づいてワークフローをトリガーし、統合アプリケーションへのコネクタを活用して、企業間 (B2B) 通信を容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="66cb9-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="66cb9-107">Logic Apps は Azure Functions とシームレスに統合されます。</span><span class="sxs-lookup"><span data-stu-id="66cb9-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Azure Logic Apps ロゴ](./media/logic-apps-logo.png)

<span data-ttu-id="66cb9-109">クラウドサービス (functions など) をクラウドリソース (キューやデータベースなど) と接続するだけでなく、Logic Apps もできます。</span><span class="sxs-lookup"><span data-stu-id="66cb9-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="66cb9-110">オンプレミスのゲートウェイを使用してオンプレミスのワークフローを調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="66cb9-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="66cb9-111">たとえば、ロジックアプリを使用して、ワークフロー内のクラウドベースのイベントまたは条件付きロジックに応じて、オンプレミスの SQL ストアドプロシージャをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="66cb9-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="66cb9-112">オンプレミスのデータソースへの接続の詳細については、「[オンプレミスデータゲートウェイ](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66cb9-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span></span>

![Logic Apps アーキテクチャ](./media/logic-apps-architecture.png)

<span data-ttu-id="66cb9-114">Azure Functions と同様に、トリガーを使用してロジックアプリのワークフローを開始します。</span><span class="sxs-lookup"><span data-stu-id="66cb9-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="66cb9-115">選択できるトリガーは多数あります。</span><span class="sxs-lookup"><span data-stu-id="66cb9-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="66cb9-116">次のキャプチャでは、使用可能な数百を超える人気のあるものをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="66cb9-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![Logic Apps トリガー](./media/logic-app-triggers.png)

<span data-ttu-id="66cb9-118">アプリがトリガーされたら、ビジュアルデザイナーを使用して、ステップ、ループ、条件、およびアクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="66cb9-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="66cb9-119">前の手順で作成したデータ取り込まれたは、以降の手順で使用できます。</span><span class="sxs-lookup"><span data-stu-id="66cb9-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="66cb9-120">次のワークフローは、CosmosDB データベースから Url を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="66cb9-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="66cb9-121">ホスト`t.co`があるものを検索し、Twitter で検索します。</span><span class="sxs-lookup"><span data-stu-id="66cb9-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="66cb9-122">対応するツイートが見つかった場合は、関数を呼び出すことによって、関連するツイートでドキュメントを更新します。</span><span class="sxs-lookup"><span data-stu-id="66cb9-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![ロジックアプリのワークフロー](./media/logic-app-workflow.png)

<span data-ttu-id="66cb9-124">Logic Apps ダッシュボードには、ワークフローの実行履歴と、各実行が正常に完了したかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66cb9-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="66cb9-125">特定の実行に移動し、各ステップで使用されるデータを調べて、トラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="66cb9-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="66cb9-126">Logic Apps には、編集できる既存のテンプレートも用意されており、複雑なエンタープライズワークフローに適しています。</span><span class="sxs-lookup"><span data-stu-id="66cb9-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="66cb9-127">詳細については、「 [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66cb9-127">To learn more, see [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="66cb9-128">[前へ](application-insights.md)
>[次へ](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="66cb9-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>
