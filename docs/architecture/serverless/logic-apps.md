---
title: Azure Logic Apps - サーバーレス アプリ
description: Azure Logic Apps では、クラウド サービスとオンプレミス システムにまたがったアプリとデータを統合する、自動化されたスケーラブルなワークフローを構築できます。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 11fdf5b5f176eb0d66eee6dde7638d3eae1e1f55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171846"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="7cb04-103">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="7cb04-103">Azure Logic Apps</span></span>

<span data-ttu-id="7cb04-104">[Azure Logic Apps](/azure/logic-apps) はサーバーレス エンジンを備えており、クラウド サービスとオンプレミス システムの間でアプリやデータを統合する、自動化されたワークフローを構築できます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-104">[Azure Logic Apps](/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="7cb04-105">ワークフローはビジュアル デザイナーを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="7cb04-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="7cb04-106">イベントまたはタイマーに基づいてワークフローをトリガーし、統合アプリケーションへのコネクタを活用し、企業間 (B2B) 通信を容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="7cb04-107">Logic Apps は Azure Functions とシームレスに統合されます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Azure Logic Apps ロゴ](./media/logic-apps-logo.png)

<span data-ttu-id="7cb04-109">Logic Apps では、クラウド サービス (関数など) をクラウド リソース (キューやデータベースなど) と接続する以上のことができます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="7cb04-110">オンプレミス ゲートウェイでオンプレミス ワークフローを調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="7cb04-111">たとえば、ワークフロー内のラウドベース イベントや条件付きロジックに対する応答として、Logic App を使用し、オンプレミス SQL ストアド プロシージャをトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="7cb04-112">Azure のオンプレミス データ ゲートウェイを使用してオンプレミスのデータ ソースに接続する方法の詳細は[こちら](/azure/analysis-services/analysis-services-gateway)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7cb04-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](/azure/analysis-services/analysis-services-gateway).</span></span>

![Logic Apps アーキテクチャ](./media/logic-apps-architecture.png)

<span data-ttu-id="7cb04-114">Azure Functions と同様に、Logic App ワークフローはトリガーで開始できます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="7cb04-115">さまざまなトリガーから選択できます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="7cb04-116">次のキャプチャでは、利用できるたくさんのトリガーの中から人気のトリガーのほんの一部が選ばれています。</span><span class="sxs-lookup"><span data-stu-id="7cb04-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![Logic Apps トリガー](./media/logic-app-triggers.png)

<span data-ttu-id="7cb04-118">アプリがトリガーされたら、ビジュアル デザイナーを使用し、ステップ、ループ、条件、アクションを構築できます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="7cb04-119">前の手順で取り込まれたデータはすべて、後続の手順で利用できます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="7cb04-120">次のワークフローでは、CosmosDB データベースから URL が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="7cb04-121">ホストが `t.co` の URL が見つけられ、Twitter 上のものが検索されます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="7cb04-122">該当するツイートが見つかった場合、関数を呼び出すことで、関連するツイートでドキュメントが更新されます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![Logic App ワークフロー](./media/logic-app-workflow.png)

<span data-ttu-id="7cb04-124">Logic Apps ダッシュボードには、ワークフローの実行履歴と各実行の成功/失敗が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="7cb04-125">特定の実行を表示したり、各手順で使用されたデータを検査し、問題を解決したりできます。</span><span class="sxs-lookup"><span data-stu-id="7cb04-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="7cb04-126">Logic Apps には自分で編集できるテンプレートがあり、複雑な企業ワークフローに適しています。</span><span class="sxs-lookup"><span data-stu-id="7cb04-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="7cb04-127">詳細については、[Azure Logic Apps](/azure/logic-apps)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cb04-127">To learn more, see [Azure Logic Apps](/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7cb04-128">[前へ](application-insights.md)
>[次へ](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="7cb04-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>
