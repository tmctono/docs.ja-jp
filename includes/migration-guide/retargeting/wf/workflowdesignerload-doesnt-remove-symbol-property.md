---
ms.openlocfilehash: 97a92c6bce80b93e9a8bdd863bf881631eaffb27
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804641"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="f0098-101">WorkflowDesigner.Load ではシンボル プロパティが削除されない</span><span class="sxs-lookup"><span data-stu-id="f0098-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f0098-102">説明</span><span class="sxs-lookup"><span data-stu-id="f0098-102">Details</span></span>|<span data-ttu-id="f0098-103">ワークフロー デザイナーで .NET Framework 4.5 を対象とし、再ホストされた 3.5 ワークフローを <xref:System.Activities.Presentation.WorkflowDesigner.Load> メソッドで読み込むと、ワークフローの保存中に <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f0098-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> is thrown while saving the workflow.</span></span>|
|<span data-ttu-id="f0098-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="f0098-104">Suggestion</span></span>|<span data-ttu-id="f0098-105">このバグは、ワークフロー デザイナーで .NET Framework 4.5 を対象とするときにのみ現れるため、<code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> を 4.0 の .NET Framework に設定することによって回避できます。あるいは、<xref:System.Activities.Presentation.WorkflowDesigner.Load> の代わりに <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> メソッドを使用してワークフローを読み込むことで問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="f0098-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>|
|<span data-ttu-id="f0098-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="f0098-106">Scope</span></span>|<span data-ttu-id="f0098-107">Major</span><span class="sxs-lookup"><span data-stu-id="f0098-107">Major</span></span>|
|<span data-ttu-id="f0098-108">バージョン</span><span class="sxs-lookup"><span data-stu-id="f0098-108">Version</span></span>|<span data-ttu-id="f0098-109">4.5</span><span class="sxs-lookup"><span data-stu-id="f0098-109">4.5</span></span>|
|<span data-ttu-id="f0098-110">型</span><span class="sxs-lookup"><span data-stu-id="f0098-110">Type</span></span>|<span data-ttu-id="f0098-111">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="f0098-111">Retargeting</span></span>|
|<span data-ttu-id="f0098-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f0098-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|

