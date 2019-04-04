---
title: '方法: ワークフローを構成する未処理の例外動作 WorkflowServiceHost を使用'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 9a13bb9390e891295491722898bd780bc1cac587
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636158"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="3e669-102">方法: ワークフローを構成する未処理の例外動作 WorkflowServiceHost を使用</span><span class="sxs-lookup"><span data-stu-id="3e669-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="3e669-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> は、<xref:System.ServiceModel.Activities.WorkflowServiceHost> でホストされるワークフロー内で未処理の例外が発生した場合のアクションを指定できるようにする動作です。</span><span class="sxs-lookup"><span data-stu-id="3e669-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="3e669-104">このトピックでは、この動作を構成ファイルで構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e669-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="3e669-105">WorkflowUnhandledExceptionBehavior を構成するには</span><span class="sxs-lookup"><span data-stu-id="3e669-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1.  <span data-ttu-id="3e669-106">追加、<`workflowUnhandledException`> 内の要素を <`behavior`> 内の要素を <`serviceBehaviors`> 要素を使用して、`action`次の例に示すように、ハンドルされない例外が発生したときに実行するアクションを指定する属性。</span><span class="sxs-lookup"><span data-stu-id="3e669-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
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
    >  <span data-ttu-id="3e669-107">前の構成サンプルでは、簡略化された構成を使用しています。</span><span class="sxs-lookup"><span data-stu-id="3e669-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="3e669-108">詳細については、[Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e669-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="3e669-109">この動作は、次の例に示すように、コードで構成できます。</span><span class="sxs-lookup"><span data-stu-id="3e669-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="3e669-110">`action`の属性、<`workflowUnhandledException`> 要素は、次の値のいずれかに設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3e669-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="3e669-111">**abandon**</span><span class="sxs-lookup"><span data-stu-id="3e669-111">**abandon**</span></span>  
     <span data-ttu-id="3e669-112">永続化されているインスタンス状態を変更することなく、メモリ内のインスタンスを中止します (つまり、最後の永続性ポイントにロールバックします)。</span><span class="sxs-lookup"><span data-stu-id="3e669-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="3e669-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="3e669-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="3e669-114">メモリ内のインスタンスを中止し、永続化されているインスタンスを中断状態に更新します。</span><span class="sxs-lookup"><span data-stu-id="3e669-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="3e669-115">**キャンセル**</span><span class="sxs-lookup"><span data-stu-id="3e669-115">**cancel**</span></span>  
     <span data-ttu-id="3e669-116">インスタンスのキャンセル ハンドラーを呼び出してから、メモリ内のインスタンスを完了状態にします。これにより、そのインスタンスがインスタンス ストアから削除される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3e669-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="3e669-117">**terminate**</span><span class="sxs-lookup"><span data-stu-id="3e669-117">**terminate**</span></span>  
     <span data-ttu-id="3e669-118">メモリ内のインスタンスを完了状態にし、そのインスタンスをインスタンス ストアから削除します。</span><span class="sxs-lookup"><span data-stu-id="3e669-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="3e669-119">詳細については<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>を参照してください[ワークフロー サービス ホストの拡張機能](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)します。</span><span class="sxs-lookup"><span data-stu-id="3e669-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e669-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e669-120">See also</span></span>
- [<span data-ttu-id="3e669-121">ワークフロー サービス ホストの拡張機能</span><span class="sxs-lookup"><span data-stu-id="3e669-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="3e669-122">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="3e669-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
