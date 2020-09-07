---
ms.openlocfilehash: 25ce391f917bd270d4d9a75f608e4a8ec763d15c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497688"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a><span data-ttu-id="dbd77-101">Items.Clear で SelectedItems から重複部分が削除されない</span><span class="sxs-lookup"><span data-stu-id="dbd77-101">Items.Clear does not remove duplicates from SelectedItems</span></span>

#### <a name="details"></a><span data-ttu-id="dbd77-102">説明</span><span class="sxs-lookup"><span data-stu-id="dbd77-102">Details</span></span>

<span data-ttu-id="dbd77-103">セレクター (複数選択が有効になっている) の <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> コレクションに重複部分があるとします。その場合、同じ項目が複数回表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbd77-103">Suppose a Selector (with multiple selection enabled) has duplicates in its <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> collection - the same item appears more than once.</span></span>  <span data-ttu-id="dbd77-104">データ ソースからこれらの項目を削除すると (たとえば、Items.Clear を呼び出すことにより)、<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> からそれらの項目を削除できなくなります。最初のインスタンスのみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dbd77-104">Removing those items from the data source (e.g. by calling Items.Clear) fails to remove them from <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; only the first instance is removed.</span></span> <span data-ttu-id="dbd77-105">さらに、<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (SelectedItems.Clear() など) を引き続き使用すると、<xref:System.ArgumentException?displayProperty=fullName> などの問題が発生する可能性があります。これは、<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> に、データ ソース内にはもう存在しない項目が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="dbd77-105">Furthermore, subsequent use of <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (e.g. SelectedItems.Clear()) can encounter problems such as <xref:System.ArgumentException?displayProperty=fullName>, because <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contains items that are no longer in the data source.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dbd77-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="dbd77-106">Suggestion</span></span>

<span data-ttu-id="dbd77-107">可能であれば、.NET Framework 4.6.2 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="dbd77-107">Upgrade if possible to .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="dbd77-108">名前</span><span class="sxs-lookup"><span data-stu-id="dbd77-108">Name</span></span>    | <span data-ttu-id="dbd77-109">[値]</span><span class="sxs-lookup"><span data-stu-id="dbd77-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dbd77-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="dbd77-110">Scope</span></span>   |<span data-ttu-id="dbd77-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="dbd77-111">Minor</span></span>|
|<span data-ttu-id="dbd77-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="dbd77-112">Version</span></span>|<span data-ttu-id="dbd77-113">4.5</span><span class="sxs-lookup"><span data-stu-id="dbd77-113">4.5</span></span>|
|<span data-ttu-id="dbd77-114">種類</span><span class="sxs-lookup"><span data-stu-id="dbd77-114">Type</span></span>|<span data-ttu-id="dbd77-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="dbd77-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="dbd77-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dbd77-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.MultiSelector.SelectedItems`

-->
