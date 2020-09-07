---
ms.openlocfilehash: d4e60f2a59980263916718ebcc71cc359952c031
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496367"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a>WPF スペル チェックが予期しない方法で失敗する

#### <a name="details"></a>説明

これには、次の WPF スペル チェックのいくつかの問題が含まれます。<ul><li>WPF スペル チェックで <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName> がスローされる場合がある。</li><li>"別のユーザーとして実行" を使用してアプリケーションが起動された場合、WPF スペル チェックが <xref:System.UnauthorizedAccessException> で失敗する。</li><li>WPF スペル チェックで、ドイツ語の "Hausnummer" などの複合語のスペル ミスが正しく識別されない。</li></ul>

#### <a name="suggestion"></a>提案される解決策

問題 1 - これは .NET Framework 4.6.2 で修正されました。問題 2 - "別のユーザーとして実行" を使用してアプリケーションが起動された場合、WPF スペル チェックがサポートされなくなりました。 .NET Framework 4.6.2 以降では、このように起動されたアプリケーションが予期せずクラッシュしなくなります。代わりに、スペル チェックが自動的に無効になります。 問題 3 - これは .NET Framework 4.6.2 で修正されました。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.6.1|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
