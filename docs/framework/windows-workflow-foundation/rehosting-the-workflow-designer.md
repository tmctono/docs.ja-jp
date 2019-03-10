---
title: ワークフロー デザイナーのホスト変更
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 29b3a205e97ad84ef8d0ef878b41c02058a8e5dc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703739"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="92ffc-102">ワークフロー デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="92ffc-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="92ffc-103">[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]作成、変更、および監視ワークフローのために Visual Studio 2012 の外部での環境でホストできます。</span><span class="sxs-lookup"><span data-stu-id="92ffc-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="92ffc-104">
  <xref:System.Activities.Presentation.WorkflowDesigner> 型はキャンバス、プロパティ グリッド、および他の要素のラッパーであり、デザイナーのホスト変更シナリオの多くに対応する基本的なプログラミング モデルを公開しています。</span><span class="sxs-lookup"><span data-stu-id="92ffc-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="92ffc-105">ホストしている、<xref:System.Activities.Presentation.WorkflowDesigner>内では、Windows Presentation Foundation (WPF) アプリケーションは、の一般的な再ホスト シナリオ[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="92ffc-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>

## <a name="in-this-section"></a><span data-ttu-id="92ffc-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="92ffc-106">In This Section</span></span>
 [<span data-ttu-id="92ffc-107">タスク 1:新しい Windows Presentation Foundation アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="92ffc-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="92ffc-108">タスク 2:ワークフロー デザイナーをホスティングします。</span><span class="sxs-lookup"><span data-stu-id="92ffc-108">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="92ffc-109">タスク 3:ツールボックス ペインと PropertyGrid ペインを作成します。</span><span class="sxs-lookup"><span data-stu-id="92ffc-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="92ffc-110">再ホストされたワークフロー デザイナーにおける Workflow Foundation 4.5 の新機能のサポート</span><span class="sxs-lookup"><span data-stu-id="92ffc-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="92ffc-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="92ffc-111">See also</span></span>
- [<span data-ttu-id="92ffc-112">ワークフロー デザイン操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="92ffc-112">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
