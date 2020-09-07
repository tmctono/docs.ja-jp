---
ms.openlocfilehash: 972601874d80d82ebae8b79779acfed82e5570cb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496532"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a><span data-ttu-id="5c693-101">項目が選択されている WPF ListBox、ListView、または DataGrid に対して Items.Refresh を呼び出すと、重複した項目が要素に表示されることがある</span><span class="sxs-lookup"><span data-stu-id="5c693-101">Calling Items.Refresh on a WPF ListBox, ListView, or DataGrid with items selected can cause duplicate items to appear in the element</span></span>

#### <a name="details"></a><span data-ttu-id="5c693-102">説明</span><span class="sxs-lookup"><span data-stu-id="5c693-102">Details</span></span>

<span data-ttu-id="5c693-103">.NET Framework 4.5 では、<xref:System.Windows.Controls.ListBox?displayProperty=fullName> で項目が選択されているときにコードから ListBox.Items.Refresh を呼び出すと、選択された項目がリストに複製されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5c693-103">In the .NET Framework 4.5, calling ListBox.Items.Refresh from code while items are selected in a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> can cause the selected items to be duplicated in the list.</span></span> <span data-ttu-id="5c693-104">同様の問題が <xref:System.Windows.Controls.ListView?displayProperty=fullName> と <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> で発生します。</span><span class="sxs-lookup"><span data-stu-id="5c693-104">A similar issue occurs with <xref:System.Windows.Controls.ListView?displayProperty=fullName> and <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.</span></span> <span data-ttu-id="5c693-105">これは、.NET Framework 4.6 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="5c693-105">This is fixed in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5c693-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="5c693-106">Suggestion</span></span>

<span data-ttu-id="5c693-107">この問題は、<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> が呼び出される前に、プログラムで項目を選択解除して、呼び出しの完了後に再び選択することによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="5c693-107">This issue may be worked around by programmatically unselecting items before <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> is called and then re-selecting them after the call is completed.</span></span> <span data-ttu-id="5c693-108">または、この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="5c693-108">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="5c693-109">名前</span><span class="sxs-lookup"><span data-stu-id="5c693-109">Name</span></span>    | <span data-ttu-id="5c693-110">[値]</span><span class="sxs-lookup"><span data-stu-id="5c693-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5c693-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="5c693-111">Scope</span></span>   |<span data-ttu-id="5c693-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="5c693-112">Minor</span></span>|
|<span data-ttu-id="5c693-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="5c693-113">Version</span></span>|<span data-ttu-id="5c693-114">4.5</span><span class="sxs-lookup"><span data-stu-id="5c693-114">4.5</span></span>|
|<span data-ttu-id="5c693-115">種類</span><span class="sxs-lookup"><span data-stu-id="5c693-115">Type</span></span>|<span data-ttu-id="5c693-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="5c693-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5c693-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="5c693-117">Affected APIs</span></span>

- <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Data.CollectionView.Refresh`

-->
