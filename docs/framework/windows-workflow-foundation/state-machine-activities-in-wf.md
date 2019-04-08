---
title: WF のステート マシン アクティビティ
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: eee507f873cde3aabce09c9b3fdb1620cd79fdab
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710317"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="5bc7e-102">WF のステート マシン アクティビティ</span><span class="sxs-lookup"><span data-stu-id="5bc7e-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="5bc7e-103">には、ステート マシン ワーク フローを作成するための、システム指定のいくつかのアクティビティおよびアクティビティ デザイナーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5bc7e-103">provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="5bc7e-104">使い慣れたステート マシン パラダイムを使用して、含まれているアクティビティを実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc7e-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="5bc7e-105">ステート マシンの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="5bc7e-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="5bc7e-106">ステート マシンの最終状態を表します。</span><span class="sxs-lookup"><span data-stu-id="5bc7e-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="5bc7e-107"><xref:System.Activities.Core.Presentation.FinalState> は、使用すると、最終状態として事前に構成済みの <xref:System.Activities.Statements.State> を作成するアクティビティ デザイナーです。</span><span class="sxs-lookup"><span data-stu-id="5bc7e-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="5bc7e-108">詳細については、[FinalState アクティビティ デザイナー](/visualstudio/workflow-designer/finalstate-activity-designer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc7e-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="5bc7e-109">2 つの状態間の遷移を表します。</span><span class="sxs-lookup"><span data-stu-id="5bc7e-109">Represents the transition between two states.</span></span> <span data-ttu-id="5bc7e-110">ない**ツールボックス**項目<xref:System.Activities.Statements.Transition>ドラッグして行を削除する 2 つの状態遷移をワークフロー デザイナーで作成するまたは、ときに表示される三角形で状態をドロップして 1 つの状態が置かれている別.</span><span class="sxs-lookup"><span data-stu-id="5bc7e-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="5bc7e-111">詳細については、[Transition アクティビティ デザイナー](/visualstudio/workflow-designer/transition-activity-designer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc7e-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bc7e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bc7e-112">See also</span></span>
- [<span data-ttu-id="5bc7e-113">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="5bc7e-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
