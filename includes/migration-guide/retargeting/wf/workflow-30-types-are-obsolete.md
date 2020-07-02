---
ms.openlocfilehash: 358103d5816eb61c88738e9626fb02c563b507f8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617249"
---
### <a name="workflow-30-types-are-obsolete"></a><span data-ttu-id="694c9-101">WorkFlow 3.0 タイプは廃止されました</span><span class="sxs-lookup"><span data-stu-id="694c9-101">WorkFlow 3.0 types are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="694c9-102">説明</span><span class="sxs-lookup"><span data-stu-id="694c9-102">Details</span></span>

<span data-ttu-id="694c9-103">Windows Workflow Foundation (WWF) 3.0 API (System.Workflow 名前空間からのもの) は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="694c9-103">Windows Workflow Foundation (WWF) 3.0 APIs (those from the System.Workflow namespace) are now obsolete.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="694c9-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="694c9-104">Suggestion</span></span>

<span data-ttu-id="694c9-105">新しい WWF 4.0 API (System.Activities) を代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="694c9-105">New WWF 4.0 APIs (in System.Activities) should be used instead.</span></span> <span data-ttu-id="694c9-106">新しい API の使用例は[ここ](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)にあり、詳しいガイダンスは[ここ](https://docs.microsoft.com/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5)にあります。</span><span class="sxs-lookup"><span data-stu-id="694c9-106">An example of using the new APIs can be found [here](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) and further guidance is available [here](https://docs.microsoft.com/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span></span> <span data-ttu-id="694c9-107">または、WWF 3.0 API はまだサポートされているので、使用でき、ビルド時の警告は、警告を抑制することによって、または以前のコンパイラを使用することによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="694c9-107">Alternatively, since the WWF 3.0 APIs are still supported, they may be used and the build-time warning avoided either by suppressing it or by using an older compiler.</span></span>

| <span data-ttu-id="694c9-108">名前</span><span class="sxs-lookup"><span data-stu-id="694c9-108">Name</span></span>    | <span data-ttu-id="694c9-109">[値]</span><span class="sxs-lookup"><span data-stu-id="694c9-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="694c9-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="694c9-110">Scope</span></span>   | <span data-ttu-id="694c9-111">Major</span><span class="sxs-lookup"><span data-stu-id="694c9-111">Major</span></span>       |
| <span data-ttu-id="694c9-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="694c9-112">Version</span></span> | <span data-ttu-id="694c9-113">4.5</span><span class="sxs-lookup"><span data-stu-id="694c9-113">4.5</span></span>         |
| <span data-ttu-id="694c9-114">種類</span><span class="sxs-lookup"><span data-stu-id="694c9-114">Type</span></span>    | <span data-ttu-id="694c9-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="694c9-115">Retargeting</span></span> |
