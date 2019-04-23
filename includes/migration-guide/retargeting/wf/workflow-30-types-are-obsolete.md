---
ms.openlocfilehash: 70acbb571921c5f72ecaa26b26136a77532ad220
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774453"
---
### <a name="workflow-30-types-are-obsolete"></a><span data-ttu-id="ea0c9-101">WorkFlow 3.0 タイプは廃止されました</span><span class="sxs-lookup"><span data-stu-id="ea0c9-101">WorkFlow 3.0 types are obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ea0c9-102">説明</span><span class="sxs-lookup"><span data-stu-id="ea0c9-102">Details</span></span>|<span data-ttu-id="ea0c9-103">Windows Workflow Foundation (WWF) 3.0 API (System.Workflow 名前空間からのもの) は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="ea0c9-103">Windows Workflow Foundation (WWF) 3.0 APIs (those from the System.Workflow namespace) are now obsolete.</span></span>|
|<span data-ttu-id="ea0c9-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ea0c9-104">Suggestion</span></span>|<span data-ttu-id="ea0c9-105">新しい WWF 4.0 API (System.Activities) を代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea0c9-105">New WWF 4.0 APIs (in System.Activities) should be used instead.</span></span> <span data-ttu-id="ea0c9-106">新しい API の使用例は[ここ](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)にあり、詳しいガイダンスは[ここ](https://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx)にあります。</span><span class="sxs-lookup"><span data-stu-id="ea0c9-106">An example of using the new APIs can be found [here](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) and further guidance is available [here](https://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx).</span></span> <span data-ttu-id="ea0c9-107">または、WWF 3.0 API はまだサポートされているので、使用でき、ビルド時の警告は、警告を抑制することによって、または以前のコンパイラを使用することによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="ea0c9-107">Alternatively, since the WWF 3.0 APIs are still supported, they may be used and the build-time warning avoided either by suppressing it or by using an older compiler.</span></span>|
|<span data-ttu-id="ea0c9-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="ea0c9-108">Scope</span></span>|<span data-ttu-id="ea0c9-109">Major</span><span class="sxs-lookup"><span data-stu-id="ea0c9-109">Major</span></span>|
|<span data-ttu-id="ea0c9-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="ea0c9-110">Version</span></span>|<span data-ttu-id="ea0c9-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ea0c9-111">4.5</span></span>|
|<span data-ttu-id="ea0c9-112">型</span><span class="sxs-lookup"><span data-stu-id="ea0c9-112">Type</span></span>|<span data-ttu-id="ea0c9-113">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="ea0c9-113">Retargeting</span></span>|
