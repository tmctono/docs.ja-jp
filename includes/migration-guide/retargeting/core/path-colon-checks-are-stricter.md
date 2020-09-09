---
ms.openlocfilehash: 6af63c0a58a3273aa98fa70f22e3637b481806b4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496630"
---
### <a name="path-colon-checks-are-stricter"></a>パスのコロン確認が厳密化

#### <a name="details"></a>説明

.NET Framework 4.6.2 では、以前はサポートされていなかったパスをサポートするために (長さと形式の両方で) 数多くの変更が加えられました。 ドライブの区切り (コロン) 構文がより厳密に確認されるようになった結果、それ以前は許容されていた、選ばれた少数のパス API の一部の URI パスがブロックされるようになりました。

#### <a name="suggestion"></a>提案される解決策

影響を受ける API に URI を渡す場合、まず、文字列を正規のパスに変更します。

- URL から手動でスキームを削除します (たとえば、URL から `file://` を削除します)。

- <xref:System.Uri> クラスに URI を渡し、<xref:System.Uri.LocalPath> を使用します。

あるいは、`Switch.System.IO.UseLegacyPathHandling` AppContext スイッチを `true` に設定し、新しいパス正規化を無効にします。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   | エッジ        |
| バージョン | 4.6.2       |
| 種類    | 再ターゲット中 |

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
