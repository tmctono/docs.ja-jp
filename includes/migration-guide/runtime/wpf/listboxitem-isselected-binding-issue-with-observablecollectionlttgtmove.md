---
ms.openlocfilehash: 196b6a13d32c7767b858d6d68ca775eb49324805
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496848"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a><span data-ttu-id="7e116-101">ObservableCollection&lt;T&gt;.Move に対する ListBoxItem IsSelected のバインディングの問題</span><span class="sxs-lookup"><span data-stu-id="7e116-101">ListBoxItem IsSelected binding issue with ObservableCollection&lt;T&gt;.Move</span></span>

#### <a name="details"></a><span data-ttu-id="7e116-102">説明</span><span class="sxs-lookup"><span data-stu-id="7e116-102">Details</span></span>

<span data-ttu-id="7e116-103">項目が選択された <xref:System.Windows.Controls.ListBox?displayProperty=fullName> にバインドされるコレクションで <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> または <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> を呼び出すと、<xref:System.Windows.Controls.ListBox?displayProperty=fullName> 項目の今後の選択または選択解除で不規則な動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e116-103">Calling <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> or <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> on a collection bound to a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> with items selected can lead to erratic behavior with future selection or unselection of <xref:System.Windows.Controls.ListBox?displayProperty=fullName> items.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7e116-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7e116-104">Suggestion</span></span>

<span data-ttu-id="7e116-105"><xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> ではなく <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> と <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> を呼び出すことで、この問題は解決されます。</span><span class="sxs-lookup"><span data-stu-id="7e116-105">Calling <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> and <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> instead of <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> will work around this issue.</span></span> <span data-ttu-id="7e116-106">または、この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="7e116-106">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="7e116-107">名前</span><span class="sxs-lookup"><span data-stu-id="7e116-107">Name</span></span>    | <span data-ttu-id="7e116-108">[値]</span><span class="sxs-lookup"><span data-stu-id="7e116-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7e116-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="7e116-109">Scope</span></span>   |<span data-ttu-id="7e116-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="7e116-110">Minor</span></span>|
|<span data-ttu-id="7e116-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="7e116-111">Version</span></span>|<span data-ttu-id="7e116-112">4.5</span><span class="sxs-lookup"><span data-stu-id="7e116-112">4.5</span></span>|
|<span data-ttu-id="7e116-113">種類</span><span class="sxs-lookup"><span data-stu-id="7e116-113">Type</span></span>|<span data-ttu-id="7e116-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="7e116-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7e116-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="7e116-115">Affected APIs</span></span>

- <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.ObjectModel.ObservableCollection`1.Move(System.Int32,System.Int32)``
- ``M:System.Collections.ObjectModel.ObservableCollection`1.MoveItem(System.Int32,System.Int32)``

-->
