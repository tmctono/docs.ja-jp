---
ms.openlocfilehash: df6169289fb96df5f7daf8bd58ccaeebc33ad87c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556200"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>UseLegacyContextMenuStripSourceControlValue 互換性スイッチはサポートされていません

.NET Framework 4.7.2 で導入された `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 互換性スイッチは、.NET Core または .NET 5.0 以降上の Windows フォームではサポートされていません。

#### <a name="change-description"></a>変更の説明

.NET Framework 4.7.2 以降、`Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 互換性スイッチを使用すると、開発者は <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> プロパティの新しい動作を無効にできます。これにより、ソース管理への参照が返されるようになりました。 プロパティの以前の動作では、`null` が返されました。 詳細については、[\<AppContextSwitchOverrides> 要素](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)に関するページを参照してください。

.NET Core と .NET 5.0 以降では、`Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` スイッチはサポートされていません。

#### <a name="version-introduced"></a>導入されたバージョン

3.0

#### <a name="recommended-action"></a>推奨アクション

スイッチを削除します。 そのスイッチはサポートされておらず、代替機能はありません。

#### <a name="category"></a>カテゴリ

Windows フォーム

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
