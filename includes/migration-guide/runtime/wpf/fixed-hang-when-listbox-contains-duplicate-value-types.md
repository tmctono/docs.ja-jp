---
ms.openlocfilehash: 7637c2d96aef93b4cf8f2314c1dd1edba51d553c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496975"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a><span data-ttu-id="c161e-101">ListBox に重複する値型が含まれている場合のハングの修正</span><span class="sxs-lookup"><span data-stu-id="c161e-101">Fixed a hang when ListBox contains duplicate value-types</span></span>

#### <a name="details"></a><span data-ttu-id="c161e-102">説明</span><span class="sxs-lookup"><span data-stu-id="c161e-102">Details</span></span>

<span data-ttu-id="c161e-103">Items コレクションに重複する値型オブジェクトが含まれていると、<xref:System.Windows.Controls.ItemsControl> の仮想化がスクロール中にハングする場合がある問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="c161e-103">Fixed a problem where a virtualizing<xref:System.Windows.Controls.ItemsControl> can hang during scrolling when its Items collection contains duplicate value-typed objects.</span></span>

| <span data-ttu-id="c161e-104">名前</span><span class="sxs-lookup"><span data-stu-id="c161e-104">Name</span></span>    | <span data-ttu-id="c161e-105">[値]</span><span class="sxs-lookup"><span data-stu-id="c161e-105">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c161e-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="c161e-106">Scope</span></span>   |<span data-ttu-id="c161e-107">Major</span><span class="sxs-lookup"><span data-stu-id="c161e-107">Major</span></span>|
|<span data-ttu-id="c161e-108">バージョン</span><span class="sxs-lookup"><span data-stu-id="c161e-108">Version</span></span>|<span data-ttu-id="c161e-109">4.8</span><span class="sxs-lookup"><span data-stu-id="c161e-109">4.8</span></span>|
|<span data-ttu-id="c161e-110">種類</span><span class="sxs-lookup"><span data-stu-id="c161e-110">Type</span></span>|<span data-ttu-id="c161e-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c161e-111">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c161e-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c161e-112">Affected APIs</span></span>

<span data-ttu-id="c161e-113">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="c161e-113">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
