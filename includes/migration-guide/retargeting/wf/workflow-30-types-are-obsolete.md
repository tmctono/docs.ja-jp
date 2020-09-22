---
ms.openlocfilehash: 1f85b1ce95ca07329aff77af4ec894622e0818d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606615"
---
### <a name="workflow-30-types-are-obsolete"></a><span data-ttu-id="ec65b-101">WorkFlow 3.0 タイプは廃止されました</span><span class="sxs-lookup"><span data-stu-id="ec65b-101">WorkFlow 3.0 types are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="ec65b-102">説明</span><span class="sxs-lookup"><span data-stu-id="ec65b-102">Details</span></span>

<span data-ttu-id="ec65b-103">Windows Workflow Foundation (WWF) 3.0 API (System.Workflow 名前空間からのもの) は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="ec65b-103">Windows Workflow Foundation (WWF) 3.0 APIs (those from the System.Workflow namespace) are now obsolete.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ec65b-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ec65b-104">Suggestion</span></span>

<span data-ttu-id="ec65b-105">新しい WWF 4.0 API (System.Activities) を代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec65b-105">New WWF 4.0 APIs (in System.Activities) should be used instead.</span></span> <span data-ttu-id="ec65b-106">新しい API の使用例は[ここ](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)にあり、詳しいガイダンスは[ここ](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5)にあります。</span><span class="sxs-lookup"><span data-stu-id="ec65b-106">An example of using the new APIs can be found [here](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) and further guidance is available [here](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span></span> <span data-ttu-id="ec65b-107">または、WWF 3.0 API はまだサポートされているので、使用でき、ビルド時の警告は、警告を抑制することによって、または以前のコンパイラを使用することによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="ec65b-107">Alternatively, since the WWF 3.0 APIs are still supported, they may be used and the build-time warning avoided either by suppressing it or by using an older compiler.</span></span>

| <span data-ttu-id="ec65b-108">名前</span><span class="sxs-lookup"><span data-stu-id="ec65b-108">Name</span></span>    | <span data-ttu-id="ec65b-109">[値]</span><span class="sxs-lookup"><span data-stu-id="ec65b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ec65b-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="ec65b-110">Scope</span></span>   | <span data-ttu-id="ec65b-111">Major</span><span class="sxs-lookup"><span data-stu-id="ec65b-111">Major</span></span>       |
| <span data-ttu-id="ec65b-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="ec65b-112">Version</span></span> | <span data-ttu-id="ec65b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="ec65b-113">4.5</span></span>         |
| <span data-ttu-id="ec65b-114">種類</span><span class="sxs-lookup"><span data-stu-id="ec65b-114">Type</span></span>    | <span data-ttu-id="ec65b-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="ec65b-115">Retargeting</span></span> |
