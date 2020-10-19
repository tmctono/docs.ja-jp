---
ms.openlocfilehash: 9c84c9f844a2a7efb9633c11634b069ef6b6033b
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804864"
---
### <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a>カスタマイズされたセル スタイルのフォントが DataGridView によってリセットされなくなった

アンビエント フォントが変更されても、セル スタイル フォントがカスタマイズされている場合、アンビエント フォントと一致させるために既定のセルスタイル フォントが <xref:System.Windows.Forms.DataGridViewElement.DataGridView> によってリセットされなくなりました。

#### <a name="change-description"></a>変更内容

以前のバージョンの .NET では、アンビエント フォントが変更されると、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle>、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>、および <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> の各プロパティのユーザー定義フォントが <xref:System.Windows.Forms.DataGridViewElement.DataGridView> によってリセットされ、オーバーライドされます。

.NET 5.0 以降では、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle>、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>、<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> のいずれかのプロパティでフォント設定を構成すると、アンビエント フォントが変更された場合でも、これらの設定が保持されます。 フォントをカスタマイズしないこれらのプロパティのフォントは、いずれもアンビエント フォントの設定に合わせて変更されます。

#### <a name="reason-for-change"></a>変更理由

[.NET Core 3.0 の既定のフォントの変更](../../../../docs/core/compatibility/winforms.md#default-control-font-changed-to-segoe-ui-9-pt)により、さまざまなセル スタイルの既定のフォント設定も変更されました。 この動作は、<xref:System.Windows.Forms.DataGridViewElement.DataGridView> コントロールのカスタム スタイルに依存するアプリには望ましくなく、これらのアプリの .NET Framework から .NET 5.0 への移行を妨げます。

#### <a name="version-introduced"></a>導入されたバージョン

.NET 5.0 RC2

#### <a name="recommended-action"></a>推奨される操作

お客様側では何もする必要はありません。 ただし、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle>、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>、<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> のいずれかのプロパティでフォントをカスタマイズし、そのフォントをアンビエント フォントと一致させるには、各プロパティの <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> を `null` に設定します。

#### <a name="category"></a>カテゴリ

- Windows フォーム

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

-->
