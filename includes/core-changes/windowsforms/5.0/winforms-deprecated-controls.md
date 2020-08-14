---
ms.openlocfilehash: d3bfeda8309af83d8e4199999ed91263a17caeea
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556205"
---
### <a name="removed-status-bar-controls"></a><span data-ttu-id="263fc-101">削除されたステータス バー コントロール</span><span class="sxs-lookup"><span data-stu-id="263fc-101">Removed status bar controls</span></span>

<span data-ttu-id="263fc-102">.NET 5.0 より、一部の Windows フォーム コントロールが利用できません。</span><span class="sxs-lookup"><span data-stu-id="263fc-102">Starting in .NET 5.0, some Windows Forms controls are no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="263fc-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="263fc-103">Change description</span></span>

<span data-ttu-id="263fc-104">.NET 5.0 以降では、Windows フォームのステータス バー関連のコントロールの一部が利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="263fc-104">Starting with .NET 5.0, some of the status bar-related Windows Forms controls are no longer available.</span></span> <span data-ttu-id="263fc-105">デザインとサポートが改善された代替コントロールは .NET Framework 2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="263fc-105">Replacement controls that have better design and support were introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="263fc-106">非推奨コントロールは前にデザイナー ツールボックスから削除されましたが、引き続き利用できました。</span><span class="sxs-lookup"><span data-stu-id="263fc-106">The deprecated controls were previously removed from designer toolboxes but were still available to be used.</span></span> <span data-ttu-id="263fc-107">現在は、完全に削除されています。</span><span class="sxs-lookup"><span data-stu-id="263fc-107">Now, they have been completely removed.</span></span>

<span data-ttu-id="263fc-108">次の型は現在なくなっています。</span><span class="sxs-lookup"><span data-stu-id="263fc-108">The following types are no longer available:</span></span>

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

#### <a name="version-introduced"></a><span data-ttu-id="263fc-109">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="263fc-109">Version introduced</span></span>

<span data-ttu-id="263fc-110">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="263fc-110">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="263fc-111">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="263fc-111">Recommended action</span></span>

<span data-ttu-id="263fc-112">これらのコントロールに対する代わりの API とそのシナリオに移行します。</span><span class="sxs-lookup"><span data-stu-id="263fc-112">Move to the replacement APIs for these controls and their scenarios:</span></span>

| <span data-ttu-id="263fc-113">古いコントロール (API)</span><span class="sxs-lookup"><span data-stu-id="263fc-113">Old Control (API)</span></span> | <span data-ttu-id="263fc-114">推奨される代替機能</span><span class="sxs-lookup"><span data-stu-id="263fc-114">Recommended Replacement</span></span>                          |
|-------------------|--------------------------------------------------|
| <span data-ttu-id="263fc-115">StatusBar</span><span class="sxs-lookup"><span data-stu-id="263fc-115">StatusBar</span></span>         | <xref:System.Windows.Forms.StatusStrip>          |
| <span data-ttu-id="263fc-116">StatusBarPanel</span><span class="sxs-lookup"><span data-stu-id="263fc-116">StatusBarPanel</span></span>    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

#### <a name="category"></a><span data-ttu-id="263fc-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="263fc-117">Category</span></span>

<span data-ttu-id="263fc-118">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="263fc-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="263fc-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="263fc-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle` 

-->
