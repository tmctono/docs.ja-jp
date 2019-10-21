---
title: '方法: WorkflowServiceHost を使用してワークフロー サービスの未処理の例外動作を構成する'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: aec2fd80e10ae1959b29c0883d51c4045517d792
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957256"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="96834-102">方法: WorkflowServiceHost を使用してワークフロー サービスの未処理の例外動作を構成する</span><span class="sxs-lookup"><span data-stu-id="96834-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="96834-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> は、<xref:System.ServiceModel.Activities.WorkflowServiceHost> でホストされるワークフロー内で未処理の例外が発生した場合のアクションを指定できるようにする動作です。</span><span class="sxs-lookup"><span data-stu-id="96834-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="96834-104">このトピックでは、この動作を構成ファイルで構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="96834-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="96834-105">WorkflowUnhandledExceptionBehavior を構成するには</span><span class="sxs-lookup"><span data-stu-id="96834-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1. <span data-ttu-id="96834-106">次の例`workflowUnhandledException`に示すように、`behavior` `action`属性を使用して`serviceBehaviors`、ハンドルされない例外が発生したときに実行するアクションを指定して、< > 要素内の < > 要素に < > 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="96834-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="96834-107">前の構成サンプルでは、簡略化された構成を使用しています。</span><span class="sxs-lookup"><span data-stu-id="96834-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="96834-108">詳細については、「[簡略化された構成](../../../../docs/framework/wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96834-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="96834-109">この動作は、次の例に示すように、コードで構成できます。</span><span class="sxs-lookup"><span data-stu-id="96834-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="96834-110">`action` <`workflowUnhandledException`> 要素の属性は、次のいずれかの値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="96834-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="96834-111">**破棄**</span><span class="sxs-lookup"><span data-stu-id="96834-111">**abandon**</span></span>  
     <span data-ttu-id="96834-112">永続化されているインスタンス状態を変更することなく、メモリ内のインスタンスを中止します (つまり、最後の永続性ポイントにロールバックします)。</span><span class="sxs-lookup"><span data-stu-id="96834-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="96834-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="96834-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="96834-114">メモリ内のインスタンスを中止し、永続化されているインスタンスを中断状態に更新します。</span><span class="sxs-lookup"><span data-stu-id="96834-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="96834-115">**cancel**</span><span class="sxs-lookup"><span data-stu-id="96834-115">**cancel**</span></span>  
     <span data-ttu-id="96834-116">インスタンスのキャンセル ハンドラーを呼び出してから、メモリ内のインスタンスを完了状態にします。これにより、そのインスタンスがインスタンス ストアから削除される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="96834-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="96834-117">**terminate**</span><span class="sxs-lookup"><span data-stu-id="96834-117">**terminate**</span></span>  
     <span data-ttu-id="96834-118">メモリ内のインスタンスを完了状態にし、そのインスタンスをインスタンス ストアから削除します。</span><span class="sxs-lookup"><span data-stu-id="96834-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="96834-119">の詳細<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>については、「[ワークフローサービスホストの機能拡張](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96834-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96834-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="96834-120">See also</span></span>

- [<span data-ttu-id="96834-121">ワークフロー サービス ホストの拡張機能</span><span class="sxs-lookup"><span data-stu-id="96834-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="96834-122">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="96834-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
