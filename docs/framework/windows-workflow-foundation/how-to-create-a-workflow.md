---
title: '方法: ワークフローを作成する'
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 4b24e57cce4d42645fc1750ac932e5f24cf24913
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134798"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="875c0-102">方法: ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="875c0-102">How to: Create a Workflow</span></span>
<span data-ttu-id="875c0-103">ワークフローは、ビルトイン アクティビティおよびカスタム アクティビティから構築できます。</span><span class="sxs-lookup"><span data-stu-id="875c0-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="875c0-104">このセクションのトピックをステップ実行など、両方の組み込みのアクティビティを使用するワークフローを作成、<xref:System.Activities.Statements.Flowchart>アクティビティ、およびカスタム アクティビティ、前の[方法。アクティビティ作成](how-to-create-an-activity.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="875c0-104">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="875c0-105">このワークフローは、数値推測ゲームをモデル化しています。</span><span class="sxs-lookup"><span data-stu-id="875c0-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="875c0-106">このセクションのトピックの 1 つだけでチュートリアルを終わることができます。目的のスタイルを選択し、手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="875c0-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="875c0-107">ただし、必要に応じて、すべてのトピックを修了することができます。</span><span class="sxs-lookup"><span data-stu-id="875c0-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="875c0-108">チュートリアル入門の各トピックは、前のトピックに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="875c0-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="875c0-109">このトピックを完了する必要がありますを完了して[方法。アクティビティ作成](how-to-create-an-activity.md)です。</span><span class="sxs-lookup"><span data-stu-id="875c0-109">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="875c0-110">チュートリアルの完成版をダウンロードするには、「 [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45) - チュートリアル入門)](https://go.microsoft.com/fwlink/?LinkID=248976)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="875c0-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="875c0-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="875c0-111">In This Section</span></span>  
 [<span data-ttu-id="875c0-112">方法: シーケンシャル ワークフローの作成</span><span class="sxs-lookup"><span data-stu-id="875c0-112">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="875c0-113"><xref:System.Activities.Statements.Sequence> アクティビティを使用してシーケンシャルなワークフローを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="875c0-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="875c0-114">方法: フローチャート ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="875c0-114">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="875c0-115"><xref:System.Activities.Statements.Flowchart> アクティビティを使用してフローチャート ワークフローを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="875c0-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="875c0-116">方法: ステート マシン ワークフローの作成</span><span class="sxs-lookup"><span data-stu-id="875c0-116">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="875c0-117"><xref:System.Activities.Statements.StateMachine> アクティビティを使用してステート マシン ワークフローを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="875c0-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875c0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="875c0-118">See also</span></span>

- [<span data-ttu-id="875c0-119">Windows Workflow Foundation プログラミングの新機能</span><span class="sxs-lookup"><span data-stu-id="875c0-119">Windows Workflow Foundation Programming</span></span>](programming.md)
