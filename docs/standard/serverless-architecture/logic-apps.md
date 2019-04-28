---
title: Azure Logic Apps でサーバーレス アプリ
description: Azure Logic Apps は、アプリに統合される自動化されたスケーラブルなワークフローの構築を有効にして、クラウド間でデータ サービスし、オンプレミス システムにします。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 14670a8459db3b80b8fbe3139c2675321cf9592c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61712782"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="e4d84-103">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="e4d84-103">Azure Logic Apps</span></span>

<span data-ttu-id="e4d84-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)アプリとクラウド サービス間のデータを統合する自動化されたワークフローを構築するサーバーレス エンジンを提供し、オンプレミス システムにします。</span><span class="sxs-lookup"><span data-stu-id="e4d84-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="e4d84-105">ビジュアル デザイナーを使用してワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4d84-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="e4d84-106">イベントまたはタイマーおよび統合アプリケーションへのコネクタを活用して基にワークフローをトリガーし、企業間取引 (B2B) 通信を容易にできます。</span><span class="sxs-lookup"><span data-stu-id="e4d84-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="e4d84-107">Logic Apps は、Azure Functions とシームレスに統合します。</span><span class="sxs-lookup"><span data-stu-id="e4d84-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Azure Logic Apps のロゴ](./media/logic-apps-logo.png)

<span data-ttu-id="e4d84-109">Logic Apps は、(キュー、およびデータベース) などのクラウド リソースを接続するだけです (関数) と同様、クラウド サービスよりも多く実行できます。</span><span class="sxs-lookup"><span data-stu-id="e4d84-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="e4d84-110">オンプレミス ゲートウェイとオンプレミスでワークフローを調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4d84-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="e4d84-111">たとえば、クラウド ベースのイベントに応答をオンプレミスの SQL ストアド プロシージャまたはワークフローで条件付きロジックをトリガーするのにロジック アプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d84-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="e4d84-112">詳細については[Azure をオンプレミス データ ゲートウェイとオンプレミス データ ソースに接続する](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)します。</span><span class="sxs-lookup"><span data-stu-id="e4d84-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span></span>

![ロジック アプリのアーキテクチャ](./media/logic-apps-architecture.png)

<span data-ttu-id="e4d84-114">Azure 関数のようにトリガーを使用してロジック アプリ ワークフローを開始します。</span><span class="sxs-lookup"><span data-stu-id="e4d84-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="e4d84-115">これは、多くのトリガーから選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="e4d84-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="e4d84-116">次のキャプチャは、最も一般的なもののうち何百も利用できるのほんの一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="e4d84-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![ロジック アプリ トリガー](./media/logic-app-triggers.png)

<span data-ttu-id="e4d84-118">アプリがトリガーされると、手順、ループ、条件、およびアクションを構築するビジュアル デザイナーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d84-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="e4d84-119">前の手順で取り込まれたデータは、以降の手順で使用するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d84-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="e4d84-120">次のワークフローは、CosmosDB データベースから Url を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e4d84-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="e4d84-121">ホストのあるものを見つけた`t.co`Twitter でそれらを検索します。</span><span class="sxs-lookup"><span data-stu-id="e4d84-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="e4d84-122">対応するツイートが見つかると、そのドキュメントを更新する関連ツイートの関数を呼び出すことによって。</span><span class="sxs-lookup"><span data-stu-id="e4d84-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![ロジック アプリ ワークフロー](./media/logic-app-workflow.png)

<span data-ttu-id="e4d84-124">ロジック アプリのダッシュ ボードは、ワークフローとかどうかの各実行が完了したかが正常に実行の履歴を示します。</span><span class="sxs-lookup"><span data-stu-id="e4d84-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="e4d84-125">任意の特定の実行に移動し、トラブルシューティングの各ステップで使用されるデータを検査できます。</span><span class="sxs-lookup"><span data-stu-id="e4d84-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="e4d84-126">Logic Apps には、既存のテンプレートを編集でき、複雑なエンタープライズ ワークフローの場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="e4d84-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="e4d84-127">詳細についてを参照してください。 [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)します。</span><span class="sxs-lookup"><span data-stu-id="e4d84-127">To learn more, see [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e4d84-128">[前へ](application-insights.md)
>[次へ](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="e4d84-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>