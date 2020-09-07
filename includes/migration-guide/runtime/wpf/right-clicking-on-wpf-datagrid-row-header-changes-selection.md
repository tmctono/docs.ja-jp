---
ms.openlocfilehash: e1faee846627b22b88eb888d6241d47d8ea6ea06
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497562"
---
### <a name="right-clicking-on-a-wpf-datagrid-row-header-changes-the-datagrid-selection"></a>WPF DataGrid 行ヘッダーを右クリックすると、DataGrid の選択が変更される

#### <a name="details"></a>説明

複数行が選択されている状態で、選択した <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> 行ヘッダーを右クリックすると、その行のみで <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> の選択が変更されます。

#### <a name="suggestion"></a>提案される解決策

この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Windows.Controls.DataGrid.%23ctor>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.#ctor`

-->
