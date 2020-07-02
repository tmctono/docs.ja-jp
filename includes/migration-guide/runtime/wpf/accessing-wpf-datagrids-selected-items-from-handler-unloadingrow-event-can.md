---
ms.openlocfilehash: 7ac0cac53ab2fa7657d0ae58f11d9e777631acc9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620438"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="6743e-101">DataGrid の UnloadingRow イベントのハンドラーから WPF DataGrid の選択された項目にアクセスすると、NullReferenceException が発生する可能性がある</span><span class="sxs-lookup"><span data-stu-id="6743e-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="6743e-102">説明</span><span class="sxs-lookup"><span data-stu-id="6743e-102">Details</span></span>

<span data-ttu-id="6743e-103">.NET Framework 4.5 のバグが原因で、行の削除に関連する <xref:System.Windows.Controls.DataGrid> イベントのイベント ハンドラーにより、<xref:System.Windows.Controls.DataGrid> の <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> または <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> プロパティにアクセスする場合に <xref:System.NullReferenceException?displayProperty=fullName> がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6743e-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=fullName> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> properties.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6743e-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6743e-104">Suggestion</span></span>

<span data-ttu-id="6743e-105">この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="6743e-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="6743e-106">名前</span><span class="sxs-lookup"><span data-stu-id="6743e-106">Name</span></span>    | <span data-ttu-id="6743e-107">[値]</span><span class="sxs-lookup"><span data-stu-id="6743e-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6743e-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="6743e-108">Scope</span></span>   |<span data-ttu-id="6743e-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="6743e-109">Minor</span></span>|
|<span data-ttu-id="6743e-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="6743e-110">Version</span></span>|<span data-ttu-id="6743e-111">4.5</span><span class="sxs-lookup"><span data-stu-id="6743e-111">4.5</span></span>|
|<span data-ttu-id="6743e-112">種類</span><span class="sxs-lookup"><span data-stu-id="6743e-112">Type</span></span>|<span data-ttu-id="6743e-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="6743e-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6743e-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="6743e-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
