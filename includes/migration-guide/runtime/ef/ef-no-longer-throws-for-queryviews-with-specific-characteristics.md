---
ms.openlocfilehash: ceae6b85c14862b1b1183d01def0dda723ee0c2b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497148"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>EF で特定の特性を持つ QueryViews がスローされなくなった

#### <a name="details"></a>説明

クエリの一部として関連エンティティを含めようとする 0..1 ナビゲーション プロパティを使用して QueryViews に関係するクエリをアプリが実行する場合、Entity Framework で <xref:System.StackOverflowException?displayProperty=fullName> 例外がスローされなくなりました。 たとえば、<code>.Include(e =&gt; e.RelatedNavProp)</code> を呼び出す場合です。

#### <a name="suggestion"></a>提案される解決策

この変更は、.Include を呼び出すクエリの実行時に 1 - 0..1 の関係にある QueryViews を使用するコードにのみ影響します。 これにより信頼性が向上し、ほとんどすべてのアプリに対して透過的になります。 ただし、予期しない動作が発生する場合、次のエントリをアプリの構成ファイルの <code>&lt;appSettings&gt;</code> セクションに追加することにより、この変更を無効にできます。<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.5.2|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
