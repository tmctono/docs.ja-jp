---
ms.openlocfilehash: 53fc2a51a7995e9b6ad43e28429313d2aea9abf1
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "66379235"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-result-in-an-unresponsive-application"></a><span data-ttu-id="efca5-101">VirtualizingStackPanel 内の WPF TreeView またはグループ化された ListBox をスクロールすると、アプリケーションが応答しなくなることがある</span><span class="sxs-lookup"><span data-stu-id="efca5-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can result in an unresponsive application</span></span>

|   |   |
|---|---|
|<span data-ttu-id="efca5-102">説明</span><span class="sxs-lookup"><span data-stu-id="efca5-102">Details</span></span>|<span data-ttu-id="efca5-103">.NET Framework 4.5 では、仮想化されたスタック パネル内の WPF <xref:System.Windows.Controls.TreeView?displayProperty=name> をスクロールすると、ビューポートに余白があった場合 (たとえば、<xref:System.Windows.Controls.TreeView?displayProperty=name> 内の項目間や、ItemsPresenter 要素上)、アプリケーションが応答しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="efca5-103">In .NET Framework 4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=name> in a virtualized stack panel can cause an application to become unresponsive if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=name>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="efca5-104">さらに、場合によっては、ビュー内にサイズの異なる項目があると、余白がない場合でも、不安定になることがあります。</span><span class="sxs-lookup"><span data-stu-id="efca5-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>|
|<span data-ttu-id="efca5-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="efca5-105">Suggestion</span></span>|<span data-ttu-id="efca5-106">このバグは、.NET Framework 4.5.1 にアップグレードすることによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="efca5-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="efca5-107">または、含まれているすべての項目が同じサイズである場合は、仮想化されたスタック パネル内のビュー コレクション (<xref:System.Windows.Controls.TreeView?displayProperty=name> など) から余白を削除できます。</span><span class="sxs-lookup"><span data-stu-id="efca5-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=name>s) within virtualized stack panels if all contained items are the same size.</span></span>|
|<span data-ttu-id="efca5-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="efca5-108">Scope</span></span>|<span data-ttu-id="efca5-109">Major</span><span class="sxs-lookup"><span data-stu-id="efca5-109">Major</span></span>|
|<span data-ttu-id="efca5-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="efca5-110">Version</span></span>|<span data-ttu-id="efca5-111">4.5</span><span class="sxs-lookup"><span data-stu-id="efca5-111">4.5</span></span>|
|<span data-ttu-id="efca5-112">型</span><span class="sxs-lookup"><span data-stu-id="efca5-112">Type</span></span>|<span data-ttu-id="efca5-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="efca5-113">Runtime</span></span>|
|<span data-ttu-id="efca5-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="efca5-114">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
