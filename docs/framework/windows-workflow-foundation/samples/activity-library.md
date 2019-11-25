---
title: アクティビティ ライブラリ
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 15260fc2ad96e1761a8a41ccc84b2c199e3d448a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283153"
---
# <a name="activity-library"></a><span data-ttu-id="ef663-102">アクティビティ ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ef663-102">Activity Library</span></span>
<span data-ttu-id="ef663-103">このセクションには、Windows Workflow Foundation (WF) の高度なカスタムアクティビティを示すサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef663-103">This section contains samples that demonstrate advanced custom activities in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef663-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ef663-104">In This Section</span></span>

 [<span data-ttu-id="ef663-105">SendMail カスタム アクティビティ</span><span class="sxs-lookup"><span data-stu-id="ef663-105">SendMail Custom Activity</span></span>](sendmail-custom-activity.md)  
 <span data-ttu-id="ef663-106"><xref:System.Activities.AsyncCodeActivity> から派生するカスタム アクティビティを作成して、SMTP を使用して電子メールを送信し、ワークフロー アプリケーション内で使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ef663-106">Demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span>  
  
 [<span data-ttu-id="ef663-107">制限された並列 ForEach</span><span class="sxs-lookup"><span data-stu-id="ef663-107">Throttled Parallel ForEach</span></span>](throttled-parallel-foreach.md)  
 <span data-ttu-id="ef663-108">ph x="1" /&gt; アクティビティは、実行するコンカレンシー分岐の数を制限するためのコンカレンシー要因を設定できるという 1 つの例外を除き、`ThrottleParallelForEach` アクティビティと似ていることについて示します。</span><span class="sxs-lookup"><span data-stu-id="ef663-108">Demonstrates how the `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span>
  
 [<span data-ttu-id="ef663-109">データベース アクセス アクティビティ</span><span class="sxs-lookup"><span data-stu-id="ef663-109">Database Access Activities</span></span>](database-access-activities.md)  
 <span data-ttu-id="ef663-110">データベースにアクセスして情報を取得または変更し、 [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081)を使用してデータベースにアクセスできるようにするアクティビティを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ef663-110">Demonstrates how to create activities that allow accessing databases to retrieve or modify information and use [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
 [<span data-ttu-id="ef663-111">.NET Framework 4.5 の外部化されたポリシー アクティビティ</span><span class="sxs-lookup"><span data-stu-id="ef663-111">Externalized Policy Activity in .NET Framework 4.5</span></span>](externalized-policy-activity-in-net-framework-4-5.md)  
 <span data-ttu-id="ef663-112">ExternalizedPolicy4 アクティビティを使用して、WF 3.5 に同梱されているルールエンジンを使用して、[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) の Windows Workflow Foundation にある .NET Framework 3.5 (wf 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> オブジェクトの既存の Windows Workflow Foundation を直接実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ef663-112">Demonstrates how the ExternalizedPolicy4 activity allows executing existing Windows Workflow Foundation in .NET Framework 3.5 (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span> 
  
 [<span data-ttu-id="ef663-113">非ジェネリックの ForEach</span><span class="sxs-lookup"><span data-stu-id="ef663-113">Non-Generic ForEach</span></span>](non-generic-foreach.md)  
 <span data-ttu-id="ef663-114"><xref:System.Activities.Statements.ForEach%601> アクティビティの非ジェネリック バージョンを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ef663-114">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="ef663-115">非ジェネリックの ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="ef663-115">Non-Generic ParallelForEach</span></span>](non-generic-parallelforeach.md)  
 <span data-ttu-id="ef663-116"><xref:System.Activities.Statements.ParallelForEach%601> アクティビティの非ジェネリック バージョンを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ef663-116">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="ef663-117">WorkflowInstanceId の取得</span><span class="sxs-lookup"><span data-stu-id="ef663-117">Get WorkflowInstanceId</span></span>](get-workflowinstanceid.md)  
 <span data-ttu-id="ef663-118">カスタム アクティビティ `GetWorkflowInstanceId` を使用して、ワークフロー インスタンス ID を返す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ef663-118">Demonstrates how to use the custom activity, `GetWorkflowInstanceId`, to return the workflow instance ID.</span></span>
