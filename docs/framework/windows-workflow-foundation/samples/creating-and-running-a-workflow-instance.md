---
title: ワークフロー インスタンスの作成と実行
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: fe00ebec8d81e77ff982a36419f1b0a988fcd4ab
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2019
ms.locfileid: "70016048"
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="a4363-102">ワークフロー インスタンスの作成と実行</span><span class="sxs-lookup"><span data-stu-id="a4363-102">Creating and Running a Workflow Instance</span></span>

<span data-ttu-id="a4363-103">このサンプルでは、ワークフロー インスタンスを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a4363-103">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="a4363-104">ここでは、ワークフロー インスタンスを同期的または非同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a4363-104">It shows how to execute it synchronously and asynchronously.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="a4363-105">使用例</span><span class="sxs-lookup"><span data-stu-id="a4363-105">Demonstrates</span></span>

<span data-ttu-id="a4363-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="a4363-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>

## <a name="discussion"></a><span data-ttu-id="a4363-107">説明</span><span class="sxs-lookup"><span data-stu-id="a4363-107">Discussion</span></span>

<span data-ttu-id="a4363-108">サンプルの最初の部分では <xref:System.Activities.WorkflowInvoker.Invoke%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="a4363-108">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="a4363-109">これはワークフローを実行する最も基本的な方法です。</span><span class="sxs-lookup"><span data-stu-id="a4363-109">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="a4363-110"><xref:System.Activities.WorkflowInvoker.Invoke%2A> を使用して実行するワークフローは同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a4363-110">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>

<span data-ttu-id="a4363-111">サンプルの 2 番目の部分は <xref:System.Activities.WorkflowApplication> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4363-111">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="a4363-112"><xref:System.Activities.WorkflowApplication> を使用すると、各インスタンスをより細かく制御できるようになり、実行中のワークフローと対話したり、ワークフローを非同期的に実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="a4363-112"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4363-113">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4363-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a4363-114">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a4363-114">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="a4363-115">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780)にアクセスして、すべての[!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (wcf) とサンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="a4363-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4363-116">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a4363-116">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`

## <a name="see-also"></a><span data-ttu-id="a4363-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4363-117">See also</span></span>

- [<span data-ttu-id="a4363-118">WorkflowInvoker と WorkflowApplication の使用</span><span class="sxs-lookup"><span data-stu-id="a4363-118">Using WorkflowInvoker and WorkflowApplication</span></span>](../using-workflowinvoker-and-workflowapplication.md)
