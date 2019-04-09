---
title: WF のステート マシン アクティビティ
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 5aee2a7cb078d9d62c9296f7dda9f28ff812a88a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120914"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="c917a-102">WF のステート マシン アクティビティ</span><span class="sxs-lookup"><span data-stu-id="c917a-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="c917a-103">ステート マシン ワークフローを作成するためには、いくつかのシステム標準アクティビティおよびアクティビティ デザイナーを提供します。</span><span class="sxs-lookup"><span data-stu-id="c917a-103">provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="c917a-104">使い慣れたステート マシン パラダイムを使用して、含まれているアクティビティを実行します。</span><span class="sxs-lookup"><span data-stu-id="c917a-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="c917a-105">ステート マシンの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="c917a-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="c917a-106">ステート マシンの最終状態を表します。</span><span class="sxs-lookup"><span data-stu-id="c917a-106">Represents a terminating state in a state machine.</span></span> <xref:System.Activities.Core.Presentation.FinalState> <span data-ttu-id="c917a-107">アクティビティ デザイナーは、ときに使用を作成、<xref:System.Activities.Statements.State>の最終状態として事前構成済みです。</span><span class="sxs-lookup"><span data-stu-id="c917a-107">is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="c917a-108">詳細については、次を参照してください。 [FinalState アクティビティ デザイナー](/visualstudio/workflow-designer/finalstate-activity-designer)します。</span><span class="sxs-lookup"><span data-stu-id="c917a-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="c917a-109">2 つの状態間の遷移を表します。</span><span class="sxs-lookup"><span data-stu-id="c917a-109">Represents the transition between two states.</span></span> <span data-ttu-id="c917a-110">ない**ツールボックス**項目<xref:System.Activities.Statements.Transition>ドラッグして行を削除する 2 つの状態遷移をワークフロー デザイナーで作成するまたは、ときに表示される三角形で状態をドロップして 1 つの状態が置かれている別.</span><span class="sxs-lookup"><span data-stu-id="c917a-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="c917a-111">詳細については、次を参照してください。 [Transition アクティビティ デザイナー](/visualstudio/workflow-designer/transition-activity-designer)します。</span><span class="sxs-lookup"><span data-stu-id="c917a-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c917a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c917a-112">See also</span></span>

- [<span data-ttu-id="c917a-113">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="c917a-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
