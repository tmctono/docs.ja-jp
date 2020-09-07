---
ms.openlocfilehash: 61749f59f9379a6d18bb013b2612a07cb7822b3a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497737"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="65aef-101">WPF の PageRangeSelection の新しい列挙値</span><span class="sxs-lookup"><span data-stu-id="65aef-101">New enum values in WPF's PageRangeSelection</span></span>

#### <a name="details"></a><span data-ttu-id="65aef-102">説明</span><span class="sxs-lookup"><span data-stu-id="65aef-102">Details</span></span>

<span data-ttu-id="65aef-103">新しい 2 つのメンバー (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> および <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) が <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> 列挙型に追加されました。</span><span class="sxs-lookup"><span data-stu-id="65aef-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> enum.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="65aef-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="65aef-104">Suggestion</span></span>

<span data-ttu-id="65aef-105">ほとんどの場合、これらの変更はユーザー コードに影響しません。</span><span class="sxs-lookup"><span data-stu-id="65aef-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="65aef-106">ただし、<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> 型に対する <xref:System.Enum.GetNames(System.Type)> または <xref:System.Enum.GetValues(System.Type)> 呼び出しに特定の数の要素が存在することに依存するコードは、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65aef-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> type should be modified, though.</span></span>

| <span data-ttu-id="65aef-107">名前</span><span class="sxs-lookup"><span data-stu-id="65aef-107">Name</span></span>    | <span data-ttu-id="65aef-108">[値]</span><span class="sxs-lookup"><span data-stu-id="65aef-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65aef-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="65aef-109">Scope</span></span>   |<span data-ttu-id="65aef-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="65aef-110">Edge</span></span>|
|<span data-ttu-id="65aef-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="65aef-111">Version</span></span>|<span data-ttu-id="65aef-112">4.5</span><span class="sxs-lookup"><span data-stu-id="65aef-112">4.5</span></span>|
|<span data-ttu-id="65aef-113">種類</span><span class="sxs-lookup"><span data-stu-id="65aef-113">Type</span></span>|<span data-ttu-id="65aef-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="65aef-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="65aef-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="65aef-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.PageRangeSelection`

-->
