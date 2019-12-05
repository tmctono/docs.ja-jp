---
ms.openlocfilehash: add3ff8faed2e7fab245e5b6f1b9158b7bdd06f5
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567373"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a><span data-ttu-id="77bb1-101">ヒントが表示されていると CellFormatting が発生しない</span><span class="sxs-lookup"><span data-stu-id="77bb1-101">CellFormatting event not raised if tooltip is shown</span></span>

<span data-ttu-id="77bb1-102">マウスでポイントしたときと、キーボードで選択したときに、<xref:System.Windows.Forms.DataGridView> にセルのテキストとエラーのヒントが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="77bb1-102">A <xref:System.Windows.Forms.DataGridView> now shows a cell's text and error tooltips when hovered by a mouse and when selected via the keyboard.</span></span> <span data-ttu-id="77bb1-103">ヒントが表示されている場合、<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="77bb1-103">If a tooltip is shown, the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event is not raised.</span></span>

#### <a name="change-description"></a><span data-ttu-id="77bb1-104">変更の説明</span><span class="sxs-lookup"><span data-stu-id="77bb1-104">Change description</span></span>

<span data-ttu-id="77bb1-105">.NET Core 3.1 より前、<xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> プロパティが `true` に設定されている <xref:System.Windows.Forms.DataGridView> では、セルにマウスでポイントしたときにセルのテキストとエラーのヒントが表示されていました。</span><span class="sxs-lookup"><span data-stu-id="77bb1-105">Prior to .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that had the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` showed a tooltip for a cell's text and errors when the cell was hovered by a mouse.</span></span> <span data-ttu-id="77bb1-106">セルをキーボード (たとえば、Tab キー、ショートカット キー、矢印ナビゲーションなどを使用して) から選択したときはヒントが表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="77bb1-106">Tooltips were not shown when a cell was selected via the keyboard (for example, by using the Tab key, shortcut keys, or arrow navigation).</span></span> <span data-ttu-id="77bb1-107">ユーザーがセルを編集したときに <xref:System.Windows.Forms.DataGridView> がまだ編集モードだった場合に <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> プロパティが設定されていないセルをポイントすると、セルのテキストをセルに表示する書式設定をするための <xref:System.Windows.Forms.DataGridView.CellFormatting> イベントが発生しました。</span><span class="sxs-lookup"><span data-stu-id="77bb1-107">If the user edited a cell, and then, while the <xref:System.Windows.Forms.DataGridView> was still in edit mode, hovered over a cell that did not have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set, a <xref:System.Windows.Forms.DataGridView.CellFormatting> event was raised to format the cell's text for display in the cell.</span></span>

<span data-ttu-id="77bb1-108">.NET Core 3.1 以降では、アクセシビリティの標準を満たすため、<xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> プロパティが `true` に設定されている <xref:System.Windows.Forms.DataGridView> には、セルがポイントされたときだけでなく、キーボードを使用して選択されたときにも、セルのテキストとエラーのヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77bb1-108">To meet accessibility standards, starting in .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that has the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` shows tooltips for a cell's text and errors not only when the cell is hovered, but also when it's selected via the keyboard.</span></span> <span data-ttu-id="77bb1-109">この変更の結果、<xref:System.Windows.Forms.DataGridView> が編集モードの間に <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> プロパティが設定されていないセルをポイントしても、<xref:System.Windows.Forms.DataGridView.CellFormatting> イベントは発生*しません*。</span><span class="sxs-lookup"><span data-stu-id="77bb1-109">As a consequence of this change, the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is *not* raised when cells that don't have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set are hovered while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span> <span data-ttu-id="77bb1-110">イベントが発生しないのは、ポイントされたセルの内容が、セルに表示される代わりにヒントとして表示されるためです。</span><span class="sxs-lookup"><span data-stu-id="77bb1-110">The event is not raised because the content of the hovered cell is shown as a tooltip instead of being displayed in the cell.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="77bb1-111">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="77bb1-111">Version introduced</span></span>

<span data-ttu-id="77bb1-112">3.1</span><span class="sxs-lookup"><span data-stu-id="77bb1-112">3.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="77bb1-113">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="77bb1-113">Recommended action</span></span>

<span data-ttu-id="77bb1-114"><xref:System.Windows.Forms.DataGridView> が編集モードのときに、<xref:System.Windows.Forms.DataGridView.CellFormatting> イベントに依存するすべてのコードをリファクターします。</span><span class="sxs-lookup"><span data-stu-id="77bb1-114">Refactor any code that depends on the <xref:System.Windows.Forms.DataGridView.CellFormatting> event while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span>

#### <a name="category"></a><span data-ttu-id="77bb1-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="77bb1-115">Category</span></span>

<span data-ttu-id="77bb1-116">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="77bb1-116">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="77bb1-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="77bb1-117">Affected APIs</span></span>

<span data-ttu-id="77bb1-118">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="77bb1-118">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
