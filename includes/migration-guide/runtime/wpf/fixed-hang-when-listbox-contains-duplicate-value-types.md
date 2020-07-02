---
ms.openlocfilehash: 5d5423d18091545ad9d50325900f5a9a4fff6dd9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622013"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a><span data-ttu-id="e0280-101">ListBox に重複する値型が含まれている場合のハングの修正</span><span class="sxs-lookup"><span data-stu-id="e0280-101">Fixed a hang when ListBox contains duplicate value-types</span></span>

#### <a name="details"></a><span data-ttu-id="e0280-102">説明</span><span class="sxs-lookup"><span data-stu-id="e0280-102">Details</span></span>

<span data-ttu-id="e0280-103">Items コレクションに重複する値型オブジェクトが含まれていると、<xref:System.Windows.Controls.ItemsControl> の仮想化がスクロール中にハングする場合がある問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="e0280-103">Fixed a problem where a virtualizing<xref:System.Windows.Controls.ItemsControl> can hang during scrolling when its Items collection contains duplicate value-typed objects.</span></span>

| <span data-ttu-id="e0280-104">名前</span><span class="sxs-lookup"><span data-stu-id="e0280-104">Name</span></span>    | <span data-ttu-id="e0280-105">[値]</span><span class="sxs-lookup"><span data-stu-id="e0280-105">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e0280-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="e0280-106">Scope</span></span>   |<span data-ttu-id="e0280-107">Major</span><span class="sxs-lookup"><span data-stu-id="e0280-107">Major</span></span>|
|<span data-ttu-id="e0280-108">バージョン</span><span class="sxs-lookup"><span data-stu-id="e0280-108">Version</span></span>|<span data-ttu-id="e0280-109">4.8</span><span class="sxs-lookup"><span data-stu-id="e0280-109">4.8</span></span>|
|<span data-ttu-id="e0280-110">種類</span><span class="sxs-lookup"><span data-stu-id="e0280-110">Type</span></span>|<span data-ttu-id="e0280-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e0280-111">Runtime</span></span>|
