---
ms.openlocfilehash: c78122a2fe69c78625d6cb7fa9ddf41c49c2e737
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497717"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="38cef-101">CellEditEnding ハンドラーから DataGrid.CommitEdit を呼び出すと、フォーカスが削除される</span><span class="sxs-lookup"><span data-stu-id="38cef-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

#### <a name="details"></a><span data-ttu-id="38cef-102">説明</span><span class="sxs-lookup"><span data-stu-id="38cef-102">Details</span></span>

<span data-ttu-id="38cef-103"><xref:System.Windows.Controls.DataGrid?displayProperty=fullName> の <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> イベント ハンドラーのいずれかから <xref:System.Windows.Controls.DataGrid.CommitEdit> を呼び出すと、<xref:System.Windows.Controls.DataGrid?displayProperty=fullName> からフォーカスが失われます。</span><span class="sxs-lookup"><span data-stu-id="38cef-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> to lose focus.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="38cef-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="38cef-104">Suggestion</span></span>

<span data-ttu-id="38cef-105">このバグは .NET framework 4.5.2 で修正されたため、.NET Framework をアップグレードすることによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="38cef-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="38cef-106">または、<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName> を呼び出した後で <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> を明示的に再選択することによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="38cef-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span></span>

| <span data-ttu-id="38cef-107">名前</span><span class="sxs-lookup"><span data-stu-id="38cef-107">Name</span></span>    | <span data-ttu-id="38cef-108">[値]</span><span class="sxs-lookup"><span data-stu-id="38cef-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="38cef-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="38cef-109">Scope</span></span>   |<span data-ttu-id="38cef-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="38cef-110">Edge</span></span>|
|<span data-ttu-id="38cef-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="38cef-111">Version</span></span>|<span data-ttu-id="38cef-112">4.5</span><span class="sxs-lookup"><span data-stu-id="38cef-112">4.5</span></span>|
|<span data-ttu-id="38cef-113">種類</span><span class="sxs-lookup"><span data-stu-id="38cef-113">Type</span></span>|<span data-ttu-id="38cef-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="38cef-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="38cef-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="38cef-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.CommitEdit`
- `M:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)`

-->
