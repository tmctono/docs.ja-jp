---
ms.openlocfilehash: ddc98448101c65003001ad05e67f29d75d99ad44
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616090"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="94fb5-101">WorkflowDesigner.Load ではシンボル プロパティが削除されない</span><span class="sxs-lookup"><span data-stu-id="94fb5-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

#### <a name="details"></a><span data-ttu-id="94fb5-102">説明</span><span class="sxs-lookup"><span data-stu-id="94fb5-102">Details</span></span>

<span data-ttu-id="94fb5-103">ワークフロー デザイナーで .NET Framework 4.5 を対象とし、再ホストされた 3.5 ワークフローを <xref:System.Activities.Presentation.WorkflowDesigner.Load> メソッドで読み込むと、ワークフローの保存中に <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="94fb5-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> is thrown while saving the workflow.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="94fb5-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="94fb5-104">Suggestion</span></span>

<span data-ttu-id="94fb5-105">このバグは、ワークフロー デザイナーで .NET Framework 4.5 を対象とするときにのみ現れるため、`WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` を 4.0 の .NET Framework に設定することによって回避できます。あるいは、<xref:System.Activities.Presentation.WorkflowDesigner.Load> の代わりに <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> メソッドを使用してワークフローを読み込むことで問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="94fb5-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>

| <span data-ttu-id="94fb5-106">名前</span><span class="sxs-lookup"><span data-stu-id="94fb5-106">Name</span></span>    | <span data-ttu-id="94fb5-107">[値]</span><span class="sxs-lookup"><span data-stu-id="94fb5-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="94fb5-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="94fb5-108">Scope</span></span>   | <span data-ttu-id="94fb5-109">Major</span><span class="sxs-lookup"><span data-stu-id="94fb5-109">Major</span></span>       |
| <span data-ttu-id="94fb5-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="94fb5-110">Version</span></span> | <span data-ttu-id="94fb5-111">4.5</span><span class="sxs-lookup"><span data-stu-id="94fb5-111">4.5</span></span>         |
| <span data-ttu-id="94fb5-112">種類</span><span class="sxs-lookup"><span data-stu-id="94fb5-112">Type</span></span>    | <span data-ttu-id="94fb5-113">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="94fb5-113">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="94fb5-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="94fb5-114">Affected APIs</span></span>

- <xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType>
