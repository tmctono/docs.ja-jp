---
ms.openlocfilehash: 75f176133697056bab9349ba1d18d7a0e1aa7da2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620127"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a><span data-ttu-id="814d6-101">Items.Clear で SelectedItems から重複部分が削除されない</span><span class="sxs-lookup"><span data-stu-id="814d6-101">Items.Clear does not remove duplicates from SelectedItems</span></span>

#### <a name="details"></a><span data-ttu-id="814d6-102">説明</span><span class="sxs-lookup"><span data-stu-id="814d6-102">Details</span></span>

<span data-ttu-id="814d6-103">セレクター (複数選択が有効になっている) の <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> コレクションに重複部分があるとします。その場合、同じ項目が複数回表示されます。</span><span class="sxs-lookup"><span data-stu-id="814d6-103">Suppose a Selector (with multiple selection enabled) has duplicates in its <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> collection - the same item appears more than once.</span></span>  <span data-ttu-id="814d6-104">データ ソースからこれらの項目を削除すると (たとえば、Items.Clear を呼び出すことにより)、<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> からそれらの項目を削除できなくなります。最初のインスタンスのみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="814d6-104">Removing those items from the data source (e.g. by calling Items.Clear) fails to remove them from <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; only the first instance is removed.</span></span> <span data-ttu-id="814d6-105">さらに、<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (SelectedItems.Clear() など) を引き続き使用すると、<xref:System.ArgumentException?displayProperty=fullName> などの問題が発生する可能性があります。これは、<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> に、データ ソース内にはもう存在しない項目が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="814d6-105">Furthermore, subsequent use of <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (e.g. SelectedItems.Clear()) can encounter problems such as <xref:System.ArgumentException?displayProperty=fullName>, because <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contains items that are no longer in the data source.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="814d6-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="814d6-106">Suggestion</span></span>

<span data-ttu-id="814d6-107">可能であれば、.NET Framework 4.6.2 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="814d6-107">Upgrade if possible to .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="814d6-108">名前</span><span class="sxs-lookup"><span data-stu-id="814d6-108">Name</span></span>    | <span data-ttu-id="814d6-109">[値]</span><span class="sxs-lookup"><span data-stu-id="814d6-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="814d6-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="814d6-110">Scope</span></span>   |<span data-ttu-id="814d6-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="814d6-111">Minor</span></span>|
|<span data-ttu-id="814d6-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="814d6-112">Version</span></span>|<span data-ttu-id="814d6-113">4.5</span><span class="sxs-lookup"><span data-stu-id="814d6-113">4.5</span></span>|
|<span data-ttu-id="814d6-114">種類</span><span class="sxs-lookup"><span data-stu-id="814d6-114">Type</span></span>|<span data-ttu-id="814d6-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="814d6-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="814d6-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="814d6-116">Affected APIs</span></span>

-<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|
