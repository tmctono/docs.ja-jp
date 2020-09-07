---
ms.openlocfilehash: c78122a2fe69c78625d6cb7fa9ddf41c49c2e737
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497717"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>CellEditEnding ハンドラーから DataGrid.CommitEdit を呼び出すと、フォーカスが削除される

#### <a name="details"></a>説明

<xref:System.Windows.Controls.DataGrid?displayProperty=fullName> の <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> イベント ハンドラーのいずれかから <xref:System.Windows.Controls.DataGrid.CommitEdit> を呼び出すと、<xref:System.Windows.Controls.DataGrid?displayProperty=fullName> からフォーカスが失われます。

#### <a name="suggestion"></a>提案される解決策

このバグは .NET framework 4.5.2 で修正されたため、.NET Framework をアップグレードすることによって回避できます。 または、<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName> を呼び出した後で <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> を明示的に再選択することによって回避できます。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.CommitEdit`
- `M:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)`

-->
