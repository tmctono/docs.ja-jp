---
ms.openlocfilehash: e10b5168d59edd56ff549a3a1e3a09d023fe5e28
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556198"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>DoNotLoadLatestRichEditControl 互換性スイッチはサポートされていません

.NET Framework 4.7.1 で導入された `Switch.System.Windows.Forms.UseLegacyImages` 互換性スイッチは、.NET Core または .NET 5.0 以降上の Windows フォームではサポートされていません。

#### <a name="change-description"></a>変更の説明

.NET Framework 4.6.2 とそれ以前のバージョンでは、<xref:System.Windows.Forms.RichTextBox> コントロールによって Win32 RichEdit コントロール v3.0 がインスタンス化され、.NET Framework 4.7.1 をターゲットとするアプリケーションの場合、<xref:System.Windows.Forms.RichTextBox> コントロールによって RichEdit v4.1 (*msftedit.dll*) がインスタンス化されます。 `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` 互換性スイッチは、.NET Framework 4.7.1 以降のバージョンをターゲットとするアプリケーションが新しい RichEdit v4.1 コントロールをオプトアウトし、代わりに古い RichEdit v3 コントロールを使用できるようにするために導入されました。

.NET Core と .NET 5.0 以降のバージョンでは、`Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` スイッチはサポートされていません。 <xref:System.Windows.Forms.RichTextBox> コントロールの新しいバージョンのみがサポートされています。

#### <a name="version-introduced"></a>導入されたバージョン

3.0

#### <a name="recommended-action"></a>推奨アクション

スイッチを削除します。 そのスイッチはサポートされておらず、代替機能はありません。

#### <a name="category"></a>カテゴリ

Windows フォーム

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
