---
ms.openlocfilehash: e9f769af6d85403c2a6f085cbc3462cf549adae9
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496389"
---
### <a name="wpf-treeviewitem-must-be-used-within-a-treeview"></a>WPF TreeViewItem は TreeView 内で使用する必要がある

#### <a name="details"></a>説明

<xref:System.Windows.Controls.TreeView?displayProperty=fullName> の外部での <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> 要素の使用を制限する変更が 4.5 で導入されました。 これは、次のような条件で発生します。<ul><li><xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> のビジュアルの親がパネルではありません。 (<xref:System.Windows.Controls.TreeView?displayProperty=fullName> に対して生成された <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> は、親としてパネルを持ちます)</li><li><xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> は、リスト コントロール (ListBox、DataGrid、ListView など) の &quot;項目ホスト&quot; として機能する <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> の子孫です。 仮想化を有効にする必要はありません。</li><li><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> は、項目のスクロールです (<code>ScrollUnit=&quot;Item&quot;</code>)。</li><li>誰かが要素 <code>v</code> をスクロールして表示させるために <code>VirtualizingStackPanel.MakeVisible(v)</code> を呼び出します。 これは、明示的に行うか、さまざまな方法で暗黙的に行うことができます。おそらく、最も一般的な方法は、<code>v</code> をクリックして、キーボードのフォーカスを与えることです。</li><li><code>v</code> から <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> までのビジュアル親チェーンが <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> を通過します。</li></ul>言い換えると、これは、<xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> が <xref:System.Windows.Controls.TreeView?displayProperty=fullName> の外部で使用されるときに見られ、ユーザーは <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> の子孫をクリックして表示させます。 <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> にフォーカスを取得できる子孫がない場合、この問題は見られません。 これが該当する状況の例は、<xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> が DataTemplate のルートであるときです。 この問題に遭遇したときには、WPF フレームワーク内で InvalidCastException が発生しています。

#### <a name="suggestion"></a>提案される解決策

このための修正プログラムが使用可能になります。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
