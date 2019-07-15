---
ms.openlocfilehash: 22c67c687f5581c181acc4aeab8910c4467fd424
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858427"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a><span data-ttu-id="28f91-101">項目が選択されている WPF ListBox、ListView、または DataGrid に対して Items.Refresh を呼び出すと、重複した項目が要素に表示されることがある</span><span class="sxs-lookup"><span data-stu-id="28f91-101">Calling Items.Refresh on a WPF ListBox, ListView, or DataGrid with items selected can cause duplicate items to appear in the element</span></span>

|   |   |
|---|---|
|<span data-ttu-id="28f91-102">説明</span><span class="sxs-lookup"><span data-stu-id="28f91-102">Details</span></span>|<span data-ttu-id="28f91-103">.NET Framework 4.5 では、<xref:System.Windows.Controls.ListBox?displayProperty=name> で項目が選択されているときにコードから ListBox.Items.Refresh を呼び出すと、選択された項目がリストに複製されることがあります。</span><span class="sxs-lookup"><span data-stu-id="28f91-103">In the .NET Framework 4.5, calling ListBox.Items.Refresh from code while items are selected in a <xref:System.Windows.Controls.ListBox?displayProperty=name> can cause the selected items to be duplicated in the list.</span></span> <span data-ttu-id="28f91-104">同様の問題が <xref:System.Windows.Controls.ListView?displayProperty=name> と <xref:System.Windows.Controls.DataGrid?displayProperty=name> で発生します。</span><span class="sxs-lookup"><span data-stu-id="28f91-104">A similar issue occurs with <xref:System.Windows.Controls.ListView?displayProperty=name> and <xref:System.Windows.Controls.DataGrid?displayProperty=name>.</span></span> <span data-ttu-id="28f91-105">これは、.NET Framework 4.6 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="28f91-105">This is fixed in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="28f91-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="28f91-106">Suggestion</span></span>|<span data-ttu-id="28f91-107">この問題は、<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name> が呼び出される前に、プログラムで項目を選択解除して、呼び出しの完了後に再び選択することによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="28f91-107">This issue may be worked around by programatically unselecting items before <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name> is called and then re-selecting them after the call is completed.</span></span> <span data-ttu-id="28f91-108">または、この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="28f91-108">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="28f91-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="28f91-109">Scope</span></span>|<span data-ttu-id="28f91-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="28f91-110">Minor</span></span>|
|<span data-ttu-id="28f91-111">Version</span><span class="sxs-lookup"><span data-stu-id="28f91-111">Version</span></span>|<span data-ttu-id="28f91-112">4.5</span><span class="sxs-lookup"><span data-stu-id="28f91-112">4.5</span></span>|
|<span data-ttu-id="28f91-113">型</span><span class="sxs-lookup"><span data-stu-id="28f91-113">Type</span></span>|<span data-ttu-id="28f91-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="28f91-114">Runtime</span></span>|
|<span data-ttu-id="28f91-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="28f91-115">Affected APIs</span></span>|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|

