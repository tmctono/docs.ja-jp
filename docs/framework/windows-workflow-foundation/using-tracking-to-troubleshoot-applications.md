---
title: 追跡を使用したアプリケーションのトラブルシューティング
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: 62c46ca36c89c023bfc775eb76ba454c9a4162c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142065"
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="0f756-102">追跡を使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0f756-102">Using Tracking to Troubleshoot Applications</span></span>
<span data-ttu-id="0f756-103">Windows Workflow Foundation (WF) では、Windows Workflow Foundation のアプリケーションまたはサービスの実行の詳細を提供するワークフロー関連の情報を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="0f756-103">Windows Workflow Foundation (WF) enables you to track workflow-related information to give details into the execution of a Windows Workflow Foundation application or service.</span></span> <span data-ttu-id="0f756-104">Windows Workflow Foundation ホストは、ワークフロー インスタンスの実行中にワークフロー イベントをキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="0f756-104">Windows Workflow Foundation hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="0f756-105">ワークフローは、エラーまたは例外を生成する場合は、追跡の詳細をその処理のトラブルシューティング、Windows Workflow Foundation を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f756-105">If your workflow generates faults or exceptions, you can use the Windows Workflow Foundation tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="0f756-106">WF の追跡を使用した WF のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0f756-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="0f756-107">Windows Workflow Foundation アクティビティの処理内のエラーを検出するために照会する追跡プロファイルの追跡を有効にできます、 <xref:System.Activities.Tracking.ActivityStateRecord> Faulted の状態にします。</span><span class="sxs-lookup"><span data-stu-id="0f756-107">To detect faults within the processing of a Windows Workflow Foundation activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="0f756-108">対応するクエリは、次のコードで指定されています。</span><span class="sxs-lookup"><span data-stu-id="0f756-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="0f756-109">エラーがエラー ハンドラー (<xref:System.Activities.Statements.TryCatch> アクティビティなど) 内で反映および処理される場合、<xref:System.Activities.Tracking.FaultPropagationRecord> を使用して検出できます。</span><span class="sxs-lookup"><span data-stu-id="0f756-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="0f756-110"><xref:System.Activities.Tracking.FaultPropagationRecord> は、エラーのソース アクティビティとエラー ハンドラーの名前を示します。</span><span class="sxs-lookup"><span data-stu-id="0f756-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="0f756-111"><xref:System.Activities.Tracking.FaultPropagationRecord> には、エラーに関する例外スタックの形式でエラーの詳細が含まれます。<xref:System.Activities.Tracking.FaultPropagationRecord> を定期受信するクエリを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="0f756-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="0f756-112">エラーがワークフロー内で処理されない場合は、ワークフロー インスタンスでハンドルされない例外になり、ワークフロー インスタンスは中止されます。</span><span class="sxs-lookup"><span data-stu-id="0f756-112">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="0f756-113">ハンドルされない例外の詳細を把握するために、追跡プロファイルでは、次のように `state name="UnhandledException"` を持つワークフロー インスタンス レコードを照会する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f756-113">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="0f756-114">ワークフロー インスタンスが未処理の例外を検出すると、<xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>オブジェクトは、Windows Workflow Foundation の追跡を有効になっている場合に生成されます。</span><span class="sxs-lookup"><span data-stu-id="0f756-114">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if Windows Workflow Foundation tracking has been enabled.</span></span>  
  
 <span data-ttu-id="0f756-115">この追跡レコードには、例外スタックの形式でエラーの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f756-115">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="0f756-116">ハンドルされない例外になったエラー (たとえば、アクティビティ) のソースの詳細があります。Windows Workflow Foundation のエラー イベントにサブスクライブする、追跡参加要素を追加することで追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0f756-116">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a Windows Workflow Foundation, enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="0f756-117">この参加要素は、`ActivityStateQuery (state="Faulted")`、<xref:System.Activities.Tracking.FaultPropagationRecord>、および `WorkflowInstanceQuery (state="UnhandledException")` を照会する追跡プロファイルで構成します。</span><span class="sxs-lookup"><span data-stu-id="0f756-117">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="0f756-118">ETW 追跡参加要素を使用して追跡を有効にした場合、エラー イベントは ETW セッションに書き出されます。</span><span class="sxs-lookup"><span data-stu-id="0f756-118">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="0f756-119">イベントはイベント ビューアーを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="0f756-119">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="0f756-120">ノードの下で確認できます\*\*イベント ビューアーは アプリケーションとサービス ログ Microsoft->-> Windows アプリケーション サーバー-アプリケーション-> \*\*分析チャネルにします。</span><span class="sxs-lookup"><span data-stu-id="0f756-120">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f756-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f756-121">See also</span></span>

- [<span data-ttu-id="0f756-122">Windows Server App Fabric の監視</span><span class="sxs-lookup"><span data-stu-id="0f756-122">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="0f756-123">App Fabric でアプリケーションの監視</span><span class="sxs-lookup"><span data-stu-id="0f756-123">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
