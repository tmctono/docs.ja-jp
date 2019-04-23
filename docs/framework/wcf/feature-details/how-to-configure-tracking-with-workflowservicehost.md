---
title: '方法: WorkflowServiceHost を使用して追跡を構成する'
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: e0631cdb47bc88f7f588f4dfe6c44ea3d44f4e60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336565"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a><span data-ttu-id="b145e-102">方法: WorkflowServiceHost を使用して追跡を構成する</span><span class="sxs-lookup"><span data-stu-id="b145e-102">How to: Configure Tracking with WorkflowServiceHost</span></span>
<span data-ttu-id="b145e-103">このトピックでは、[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] でホストされている <xref:System.ServiceModel.Activities.WorkflowServiceHost> ワークフロー サービスの追跡を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b145e-103">This topic explains how to configure tracking for a [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="b145e-104">これは、Web.config ファイルにサービスの動作を指定することによって指定します。</span><span class="sxs-lookup"><span data-stu-id="b145e-104">It is configured through a Web.config file by specifying a service behavior.</span></span>  
  
### <a name="configure-tracking-in-configuration"></a><span data-ttu-id="b145e-105">構成での追跡の構成</span><span class="sxs-lookup"><span data-stu-id="b145e-105">Configure Tracking in Configuration</span></span>  
  
1. <span data-ttu-id="b145e-106">次の例に示すように、<<xref:System.Activities.Tracking.EtwTrackingParticipant>> 要素を構成ファイルで使用し、`behavior` を追加します。</span><span class="sxs-lookup"><span data-stu-id="b145e-106">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b145e-107">前の構成サンプルでは、簡略化された構成を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b145e-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="b145e-108">詳細については、次を参照してください。 [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)します。</span><span class="sxs-lookup"><span data-stu-id="b145e-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="b145e-109">前の構成サンプルでは、<xref:System.Activities.Tracking.EtwTrackingParticipant> を追加し、追跡プロファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b145e-109">The preceding configuration sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="b145e-110">追跡プロファイルは、<`trackingProfile`> 要素内の <`tracking`> 要素で作成されます。</span><span class="sxs-lookup"><span data-stu-id="b145e-110">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element.</span></span> <span data-ttu-id="b145e-111">追跡プロファイルには、実行時にワークフロー インスタンスの状態が変化したときに生成されるワークフロー イベントを追跡参加要素が定期受信できるようにする、追跡クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b145e-111">The tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="b145e-112">追跡プロファイルを作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="b145e-112">The following example shows how to create a tracking profile.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <tracking>   
         <trackingProfile name="Sample Tracking Profile">  
            <workflow activityDefinitionId="*">  
               <workflowInstanceQueries>  
                 <workflowInstanceQuery>  
                    <states>  
                       <state name="Started"/>  
                       <state name="Completed"/>  
                    </states>  
                </workflowInstanceQuery>  
             </workflowInstanceQueries>  
           </workflow>  
         </trackingProfile>   
       </tracking>  
    </system.serviceModel>  
    ```  
  
     <span data-ttu-id="b145e-113">追跡プロファイルの詳細については、次を参照してください。[追跡プロファイル](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="b145e-113">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="b145e-114">追跡全般の詳細については、次を参照してください。[ワークフロー追跡とトレース](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)します。</span><span class="sxs-lookup"><span data-stu-id="b145e-114">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
### <a name="configure-tracking-in-code"></a><span data-ttu-id="b145e-115">コードでの追跡の構成</span><span class="sxs-lookup"><span data-stu-id="b145e-115">Configure Tracking in Code</span></span>  
  
1. <span data-ttu-id="b145e-116">次の例に示すように、コードで <xref:System.Activities.Tracking.EtwTrackingParticipant> を動作を使用して <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> を追加します。</span><span class="sxs-lookup"><span data-stu-id="b145e-116">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> behavior in code, as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     <span data-ttu-id="b145e-117">前のコード サンプルでは、<xref:System.Activities.Tracking.EtwTrackingParticipant> を追加し、追跡プロファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b145e-117">The preceding code sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="b145e-118">追跡プロファイルは、前のセクションで説明したように <`trackingProfile`> 要素内の <`tracking`> 要素で作成されます。</span><span class="sxs-lookup"><span data-stu-id="b145e-118">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element as shown in the previous section.</span></span>  
  
     <span data-ttu-id="b145e-119">追跡プロファイルの詳細については、次を参照してください。[追跡プロファイル](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="b145e-119">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="b145e-120">追跡全般の詳細については、次を参照してください。[ワークフロー追跡とトレース](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)します。</span><span class="sxs-lookup"><span data-stu-id="b145e-120">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span> <span data-ttu-id="b145e-121">プログラムによる追跡を構成する例を参照してください。[ワークフローの追跡を構成する](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)します。</span><span class="sxs-lookup"><span data-stu-id="b145e-121">For an example of configuring tracking programmatically see [Configuring Tracking for a Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b145e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b145e-122">See also</span></span>

- [<span data-ttu-id="b145e-123">WCF サービスの簡略化された構成</span><span class="sxs-lookup"><span data-stu-id="b145e-123">Simplified Configuration for WCF Services</span></span>](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)
- [<span data-ttu-id="b145e-124">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="b145e-124">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="b145e-125">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="b145e-125">Tracking Profiles</span></span>](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
