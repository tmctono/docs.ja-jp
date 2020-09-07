---
ms.openlocfilehash: 450bfc56c99a3df9be71be2ef7df6e4e12d4ed76
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497390"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a>NetDataContractSerializer を使用して .NET Framework 4.5 でシリアル化された ConcurrentDictionary は、.NET Framework 4.5.1 または 4.5.2 で逆シリアル化できない

#### <a name="details"></a>説明

型に対する内部的な変更のため、<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> を使って .NET Framework 4.5 でシリアル化された <xref:System.Collections.Concurrent.ConcurrentDictionary%602> オブジェクトは、.NET Framework 4.5.1 または .NET Framework 4.5.2 では逆シリアル化できません。反対の方向 (.NET Framework 4.5.x でシリアル化して、.NET Framework 4.5 で逆シリアル化する) は動作することに注意してください。 同様に、すべての 4.x バージョン間のシリアル化は、.NET Framework 4.6 で機能します。 .NET Framework の 1 つのバージョンでのシリアル化と逆シリアル化は影響を受けません。

#### <a name="suggestion"></a>提案される解決策

.NET Framework 4.5 と .NET Framework 4.5.1/4.5.2 の間で <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> のシリアル化と逆シリアル化を行う必要がある場合は、<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> の代わりに、<xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> または <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> シリアライザーなど、代替のシリアライザーを使う必要があります。または、この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって解決できます。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.5.1|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
