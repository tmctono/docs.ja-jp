---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556196"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>EnableVisualStyleValidation 互換性スイッチはサポートされていません

`Switch.System.Windows.Forms.EnableVisualStyleValidation` 互換性スイッチは、.NET Core または .NET 5.0 以降上の Windows フォームではサポートされていません。

#### <a name="change-description"></a>変更の説明

.NET Framework では、`Switch.System.Windows.Forms.EnableVisualStyleValidation` 互換スイッチによって、アプリケーションで、数値形式で指定された視覚スタイルの検証を無効にすることが許可されていました。

.NET Core と .NET 5.0 以降では、`Switch.System.Windows.Forms.EnableVisualStyleValidation` スイッチはサポートされていません。

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
