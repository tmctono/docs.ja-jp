---
title: WorkflowHostingEndpoint 再開ブックマーク
ms.date: 03/30/2017
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
ms.openlocfilehash: 5c3c996a73d8f88e925d459fae3eb785996eada4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340543"
---
# <a name="workflowhostingendpoint-resume-bookmark"></a><span data-ttu-id="5e8db-102">WorkflowHostingEndpoint 再開ブックマーク</span><span class="sxs-lookup"><span data-stu-id="5e8db-102">WorkflowHostingEndpoint Resume Bookmark</span></span>
<span data-ttu-id="5e8db-103">このサンプルでは、<xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> を <xref:System.ServiceModel.Activities.WorkflowServiceHost> と共に使用して、ワークフロー インスタンスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e8db-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="5e8db-104">使用例</span><span class="sxs-lookup"><span data-stu-id="5e8db-104">Demonstrates</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint><span data-ttu-id="5e8db-105">,</span><span class="sxs-lookup"><span data-stu-id="5e8db-105">,</span></span> <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a><span data-ttu-id="5e8db-106">説明</span><span class="sxs-lookup"><span data-stu-id="5e8db-106">Discussion</span></span>  
 <span data-ttu-id="5e8db-107">このサンプルでは、<xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> を使用して、<xref:System.ServiceModel.Activities.WorkflowServiceHost> を使用してホストされるワークフロー インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e8db-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create a workflow instance hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> <span data-ttu-id="5e8db-108">機能拡張ポイントは、<xref:System.ServiceModel.Activities.WorkflowServiceHost>次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e8db-108">is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="5e8db-109">新しいワークフロー インスタンスの作成</span><span class="sxs-lookup"><span data-stu-id="5e8db-109">Creating new workflow instances.</span></span>  
  
-   <span data-ttu-id="5e8db-110"><xref:System.ServiceModel.Activities.WorkflowServiceHost> でホストされているワークフロー インスタンスでのブックマークの再開</span><span class="sxs-lookup"><span data-stu-id="5e8db-110">Resuming bookmarks on a workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="5e8db-111">含まれているサンプルのエンドポイントでは、ワークフローを作成してインスタンス ID を返したり、特定の ID を持つインスタンスを作成したりするための操作を提供するコントラクトを公開します。</span><span class="sxs-lookup"><span data-stu-id="5e8db-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and return an instance ID, or to create an instance with a specific ID.</span></span> <span data-ttu-id="5e8db-112">サンプルのコンソール アプリケーションでは、基本のワークフロー定義を含む <xref:System.ServiceModel.Activities.WorkflowServiceHost> インスタンスが作成されて、`CreationEndpoint` がホストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5e8db-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a basic workflow definition, and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="5e8db-113">その後、エンドポイントで `Create` 操作が呼び出され、新しいワークフロー インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5e8db-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5e8db-114">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="5e8db-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="5e8db-115">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="5e8db-115">Build the solution.</span></span>  
  
2. <span data-ttu-id="5e8db-116">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e8db-116">Run the application.</span></span> <span data-ttu-id="5e8db-117">`CreationEndpoint` コンソールには、ワークフロー インスタンスの作成時にインスタンス ID を含むメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e8db-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="5e8db-118">メッセージ"Hello World!"</span><span class="sxs-lookup"><span data-stu-id="5e8db-118">The message "Hello World!"</span></span> <span data-ttu-id="5e8db-119">ブックマークの再開を成功したワークフローで出力されます。</span><span class="sxs-lookup"><span data-stu-id="5e8db-119">is printed by the workflow on successful resumption of the bookmark.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5e8db-120">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e8db-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5e8db-121">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5e8db-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5e8db-122">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="5e8db-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5e8db-123">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5e8db-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
