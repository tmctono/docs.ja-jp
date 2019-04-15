---
ms.openlocfilehash: edd194fef27d97976f1ff45daec1cd56382bbb55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235467"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="aa31e-101">WPF の PageRangeSelection の新しい列挙値</span><span class="sxs-lookup"><span data-stu-id="aa31e-101">New enum values in WPF's PageRangeSelection</span></span>

|   |   |
|---|---|
|<span data-ttu-id="aa31e-102">説明</span><span class="sxs-lookup"><span data-stu-id="aa31e-102">Details</span></span>|<span data-ttu-id="aa31e-103">新しい 2 つのメンバー (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> および <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>) が <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> 列挙型に追加されました。</span><span class="sxs-lookup"><span data-stu-id="aa31e-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> enum.</span></span>|
|<span data-ttu-id="aa31e-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="aa31e-104">Suggestion</span></span>|<span data-ttu-id="aa31e-105">ほとんどの場合、これらの変更はユーザー コードに影響しません。</span><span class="sxs-lookup"><span data-stu-id="aa31e-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="aa31e-106">ただし、<xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> 型に対する <xref:System.Enum.GetNames(System.Type)> または <xref:System.Enum.GetValues(System.Type)> 呼び出しに特定の数の要素が存在することに依存するコードは、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa31e-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> type should be modified, though.</span></span>|
|<span data-ttu-id="aa31e-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="aa31e-107">Scope</span></span>|<span data-ttu-id="aa31e-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="aa31e-108">Edge</span></span>|
|<span data-ttu-id="aa31e-109">Version</span><span class="sxs-lookup"><span data-stu-id="aa31e-109">Version</span></span>|<span data-ttu-id="aa31e-110">4.5</span><span class="sxs-lookup"><span data-stu-id="aa31e-110">4.5</span></span>|
|<span data-ttu-id="aa31e-111">型</span><span class="sxs-lookup"><span data-stu-id="aa31e-111">Type</span></span>|<span data-ttu-id="aa31e-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="aa31e-112">Runtime</span></span>|
|<span data-ttu-id="aa31e-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="aa31e-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
