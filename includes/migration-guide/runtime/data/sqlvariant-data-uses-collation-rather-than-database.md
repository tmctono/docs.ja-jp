---
ms.openlocfilehash: fb339fb35cdcbba4f1c860fae9c17162c4cff596
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497470"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a>sql_variant データはデータベースの照合順序ではなく、sql_variant の照合順序を使用する

#### <a name="details"></a>説明

<code>sql_variant</code> データはデータベースの照合順序ではなく <code>sql_variant</code> の照合順序を使用します。

#### <a name="suggestion"></a>提案される解決策

この変更により、データベースの照合順序が <code>sql_variant</code> の照合順序と異なる場合にデータ破損が生じる可能性に対応できます。 破損したデータに依存するアプリケーションでは、エラーが発生する場合があります。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |透明|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
