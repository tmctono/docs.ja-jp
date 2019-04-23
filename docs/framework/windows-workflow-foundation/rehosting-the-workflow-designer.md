---
title: ワークフロー デザイナーのホスト変更
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 98048ca58bf635f4e87241befa083dc240deaecf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206110"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="d795d-102">ワークフロー デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="d795d-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="d795d-103">[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]作成、変更、および監視ワークフローのために Visual Studio 2012 の外部での環境でホストできます。</span><span class="sxs-lookup"><span data-stu-id="d795d-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="d795d-104"><xref:System.Activities.Presentation.WorkflowDesigner> 型はキャンバス、プロパティ グリッド、および他の要素のラッパーであり、デザイナーのホスト変更シナリオの多くに対応する基本的なプログラミング モデルを公開しています。</span><span class="sxs-lookup"><span data-stu-id="d795d-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="d795d-105">ホストしている、<xref:System.Activities.Presentation.WorkflowDesigner>内では、Windows Presentation Foundation (WPF) アプリケーションは、の一般的な再ホスト シナリオ[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d795d-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d795d-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d795d-106">In This Section</span></span>
 [<span data-ttu-id="d795d-107">タスク 1:新しい Windows Presentation Foundation アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d795d-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="d795d-108">タスク 2:ワークフロー デザイナーをホスティングします。</span><span class="sxs-lookup"><span data-stu-id="d795d-108">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="d795d-109">タスク 3:ツールボックス ペインと PropertyGrid ペインを作成します。</span><span class="sxs-lookup"><span data-stu-id="d795d-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="d795d-110">再ホストされたワークフロー デザイナーにおける Workflow Foundation 4.5 の新機能のサポート</span><span class="sxs-lookup"><span data-stu-id="d795d-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="d795d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d795d-111">See also</span></span>

- [<span data-ttu-id="d795d-112">ワークフロー デザイン操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="d795d-112">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
