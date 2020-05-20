---
title: '方法: ワークフローを作成する'
description: このセクションの3つのオプションのいずれかを実行して、この Workflow Foundation チュートリアルの一部としてワークフローを作成します。
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 7e4575436405e74b7575e55bea37a1a99d879a3e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419565"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="472a1-103">方法: ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="472a1-103">How to: Create a Workflow</span></span>
<span data-ttu-id="472a1-104">ワークフローは、ビルトイン アクティビティおよびカスタム アクティビティから構築できます。</span><span class="sxs-lookup"><span data-stu-id="472a1-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="472a1-105">このセクションのトピックでは、アクティビティなどの組み込みのアクティビティ <xref:System.Activities.Statements.Flowchart> と、前の「 [How To: Create a activity](how-to-create-an-activity.md) 」トピックのカスタムアクティビティの両方を使用するワークフローを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="472a1-105">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="472a1-106">このワークフローは、数値推測ゲームをモデル化しています。</span><span class="sxs-lookup"><span data-stu-id="472a1-106">The workflow models a number guessing game.</span></span> <span data-ttu-id="472a1-107">このセクションのトピックの 1 つだけでチュートリアルを終わることができます。目的のスタイルを選択し、手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="472a1-107">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="472a1-108">ただし、必要に応じて、すべてのトピックを修了することができます。</span><span class="sxs-lookup"><span data-stu-id="472a1-108">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="472a1-109">チュートリアル入門の各トピックは、前のトピックに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="472a1-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="472a1-110">このトピックを完了するには、まず「[方法: アクティビティを作成](how-to-create-an-activity.md)する」を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="472a1-110">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="472a1-111">チュートリアルの完成版をダウンロードするには、「 [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45) - チュートリアル入門)](https://go.microsoft.com/fwlink/?LinkID=248976)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="472a1-111">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="472a1-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="472a1-112">In This Section</span></span>  
 [<span data-ttu-id="472a1-113">方法: シーケンシャル ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="472a1-113">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="472a1-114"><xref:System.Activities.Statements.Sequence> アクティビティを使用してシーケンシャルなワークフローを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="472a1-114">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="472a1-115">方法: フローチャート ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="472a1-115">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="472a1-116"><xref:System.Activities.Statements.Flowchart> アクティビティを使用してフローチャート ワークフローを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="472a1-116">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="472a1-117">方法: ステート マシン ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="472a1-117">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="472a1-118"><xref:System.Activities.Statements.StateMachine> アクティビティを使用してステート マシン ワークフローを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="472a1-118">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="472a1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="472a1-119">See also</span></span>

- [<span data-ttu-id="472a1-120">Windows Workflow Foundation プログラミングの新機能</span><span class="sxs-lookup"><span data-stu-id="472a1-120">Windows Workflow Foundation Programming</span></span>](programming.md)
