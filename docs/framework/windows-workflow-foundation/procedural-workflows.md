---
title: 手続き型ワークフロー
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 2ef23f61e67e0b4c08f12322bac429762205ef8d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622850"
---
# <a name="procedural-workflows"></a><span data-ttu-id="9e7ae-102">手続き型ワークフロー</span><span class="sxs-lookup"><span data-stu-id="9e7ae-102">Procedural Workflows</span></span>
<span data-ttu-id="9e7ae-103">手続き型ワークフローでは、手続き型言語と似たフロー制御方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e7ae-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="9e7ae-104">これらの構造には `While` と `If` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e7ae-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="9e7ae-105">これらのワークフローは、<xref:System.Activities.Statements.Flowchart> や <xref:System.Activities.Statements.Sequence> など、他のフロー制御アクティビティを使用して自由に構成できます。</span><span class="sxs-lookup"><span data-stu-id="9e7ae-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="9e7ae-106">実行フローの制御</span><span class="sxs-lookup"><span data-stu-id="9e7ae-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="9e7ae-107">ワークフロー アクティビティ ライブラリには、手続き型言語で使用されるほとんどのフロー制御方法をモデル化するアクティビティがあります。</span><span class="sxs-lookup"><span data-stu-id="9e7ae-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="9e7ae-108">不足している機能には次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e7ae-108">These include:</span></span>  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="9e7ae-109">フロー制御アクティビティを使用するドラッグ アンド ドロップしてから、**アクティビティ**ツールボックス、デザイナー ウィンドウ内の複合アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="9e7ae-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e7ae-110">[!INCLUDE[dublin](../../../includes/dublin-md.md)] を使用して Web ファーム上でワークフローをホストすると、AppFabric のインスタンスは複数の AppFabric サーバー間を移動します。</span><span class="sxs-lookup"><span data-stu-id="9e7ae-110">If using the [!INCLUDE[dublin](../../../includes/dublin-md.md)] to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="9e7ae-111">この機能を利用するには、リソースがすべてのノード間で共有可能になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e7ae-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="9e7ae-112">既定の NET 4 ワークフロー アクティビティには、ローカル リソースにアクセスする操作は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="9e7ae-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="9e7ae-113">AppFabric には特定のワークフローを不変に設定するメカニズムがないため、ワークフローが移動されるとエラーが発生するようなカスタム アクティビティは絶対に作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="9e7ae-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e7ae-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e7ae-114">See also</span></span>

- [<span data-ttu-id="9e7ae-115">Flowchart のワークフロー</span><span class="sxs-lookup"><span data-stu-id="9e7ae-115">Flowchart Workflows</span></span>](flowchart-workflows.md)
