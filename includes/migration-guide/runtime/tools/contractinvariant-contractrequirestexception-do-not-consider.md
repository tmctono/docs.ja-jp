---
ms.openlocfilehash: 17fde81f9734966692c9f41d2213f8682dedea46
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496913"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>Contract.Invariant または Contract.Requires\<TException> が String.IsNullOrEmpty の純粋性を考慮しない

#### <a name="details"></a>説明

.NET Framework 4.6.1 が対象のアプリでは、<xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> の不変コントラクトまたは <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> の実行前の状態のコントラクトが <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> メソッドを呼び出した場合、リライターはコンパイラの警告 CC1036:&quot;Detected call to method 'System.String.IsNullOrWhiteSpace(System.String)' without [Pure] in method.&quot; を生成します。これはコンパイラ エラーではなく、コンパイラ警告です。

#### <a name="suggestion"></a>提案される解決策

この動作については [GitHubの問題 #339](https://github.com/Microsoft/CodeContracts/issues/339) で報告されています。 この警告が表示されないようにするには、コード コントラクト ツールのソース コードの更新バージョンを [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md) からダウンロードしてコンパイルします。 ページ下部から情報をダウンロードできます。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.6.1|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)`
- `M:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)`

-->
