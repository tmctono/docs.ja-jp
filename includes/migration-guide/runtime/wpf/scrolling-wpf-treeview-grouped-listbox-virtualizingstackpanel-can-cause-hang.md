---
ms.openlocfilehash: 1be68c2968d0eaa9024007bcf37abf9e44c36f1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622058"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="c498b-101">VirtualizingStackPanel 内の WPF TreeView またはグループ化された ListBox をスクロールすると、ハングすることがある</span><span class="sxs-lookup"><span data-stu-id="c498b-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

#### <a name="details"></a><span data-ttu-id="c498b-102">説明</span><span class="sxs-lookup"><span data-stu-id="c498b-102">Details</span></span>

<span data-ttu-id="c498b-103">.NET Framework v4.5 では、仮想化されたスタック パネル内の WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> をスクロールすると、ビューポートに余白があった場合 (たとえば、<xref:System.Windows.Controls.TreeView?displayProperty=fullName> 内の項目間や、ItemsPresenter 要素上)、ハングすることがあります。</span><span class="sxs-lookup"><span data-stu-id="c498b-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="c498b-104">さらに、場合によっては、ビュー内にサイズの異なる項目があると、余白がない場合でも、不安定になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c498b-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c498b-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c498b-105">Suggestion</span></span>

<span data-ttu-id="c498b-106">このバグは、.NET Framework 4.5.1 にアップグレードすることによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="c498b-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="c498b-107">または、含まれているすべての項目が同じサイズである場合は、仮想化されたスタック パネル内のビュー コレクション (<xref:System.Windows.Controls.TreeView?displayProperty=fullName> など) から余白を削除できます。</span><span class="sxs-lookup"><span data-stu-id="c498b-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=fullName>s) within virtualized stack panels if all contained items are the same size.</span></span>

| <span data-ttu-id="c498b-108">名前</span><span class="sxs-lookup"><span data-stu-id="c498b-108">Name</span></span>    | <span data-ttu-id="c498b-109">[値]</span><span class="sxs-lookup"><span data-stu-id="c498b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c498b-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="c498b-110">Scope</span></span>   |<span data-ttu-id="c498b-111">Major</span><span class="sxs-lookup"><span data-stu-id="c498b-111">Major</span></span>|
|<span data-ttu-id="c498b-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="c498b-112">Version</span></span>|<span data-ttu-id="c498b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="c498b-113">4.5</span></span>|
|<span data-ttu-id="c498b-114">種類</span><span class="sxs-lookup"><span data-stu-id="c498b-114">Type</span></span>|<span data-ttu-id="c498b-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c498b-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c498b-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c498b-116">Affected APIs</span></span>

-<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
