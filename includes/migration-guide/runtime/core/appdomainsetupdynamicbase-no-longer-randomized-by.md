---
ms.openlocfilehash: 26c50ac8b0e570e31a38b1913f73acbe21fae08b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496203"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a>AppDomainSetup.DynamicBase が UseRandomizedStringHashAlgorithm でランダム化されなくなった

#### <a name="details"></a>説明

.NET Framework 4.6 より前では、UseRandomizedStringHashAlgorithm がアプリの構成ファイルで有効になっている場合、<xref:System.AppDomainSetup.DynamicBase> の値がアプリケーション ドメイン間、またはプロセス間でランダム化されます。 .NET Framework 4.6 以降では、<xref:System.AppDomainSetup.DynamicBase> は実行されているアプリの異なるインスタンス間、および異なるアプリ ドメイン間で安定した結果を返します。 それでも動的ベースはアプリによって異なります。この変更では、同じアプリの異なるインスタンスのランダムな名前付け要素のみが削除されます。

#### <a name="suggestion"></a>提案される解決策

<code>UseRandomizedStringHashAlgorithm</code> を有効にすると、<xref:System.AppDomainSetup.DynamicBase> がランダム化されなくなることに注意してください。 ランダム ベースが必要な場合は、この API を使用するのではなく、アプリのコードで生成する必要があります。

| 名前    | 値       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.6|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.AppDomainSetup.DynamicBase`

-->
