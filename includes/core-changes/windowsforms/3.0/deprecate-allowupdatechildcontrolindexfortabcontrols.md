---
ms.openlocfilehash: 3db4b0b42a154c5bc9296889ae9dc4b7ecf1e58e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556199"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>AllowUpdateChildControlIndexForTabControls 互換性スイッチはサポートされていません

`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 互換性スイッチは、.NET Framework 4.6 以降のバージョンの Windows フォームではサポートされていますが、.NET Core または .NET 5.0 以降ではサポートされていません。

#### <a name="change-description"></a>変更の説明

.NET Framework 4.6 以降のバージョンでは、タブを選択すると、そのコントロール コレクションが並べ替えられます。 `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 互換性スイッチを使用すると、この動作が望ましくない場合に、アプリケーションでこの並べ替えをスキップできます。

.NET Core と .NET 5.0 以降では、`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` スイッチはサポートされていません。

#### <a name="version-introduced"></a>導入されたバージョン

3.0

#### <a name="recommended-action"></a>推奨アクション

スイッチを削除します。 そのスイッチはサポートされておらず、代替機能はありません。

#### <a name="category"></a>カテゴリ

Windows フォーム

#### <a name="affected-apis"></a>影響を受ける API

- なし

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
