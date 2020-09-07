---
ms.openlocfilehash: ccba3cf98a1ca9e199d9a48f00e254bf34b93f72
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496567"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a>BinaryFormatter による LoadFrom コンテキストからの型の検索が失敗する場合がある

#### <a name="details"></a>説明

.NET Framework 4.5 の時点で、<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> の複数の変更により、LoadFrom コンテキストに読み込まれた型の <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> を使った逆シリアル化に違いが発生する場合があります。 これらの変更は <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> が型を読み込む新しい方法によるものであり、後で <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> がその型に逆シリアル化しようとするときに異なる動作が発生します。 既定のシリアル化バインダーは LoadFrom コンテキストを自動的に検索しませんが、状況によっては XmlSerializer の以前の動作に基づいて機能する可能性があります。 変更のため、異なるコンテキストで読み込まれたアセンブリから型が読み込まれるときに、<xref:System.IO.FileNotFoundException?displayProperty=fullName> がスローされる可能性があります。

#### <a name="suggestion"></a>提案される解決策

この例外が発生する場合は、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> の <code>Binder</code> プロパティを、正しい型を検索するカスタム バインダーに設定することができます。<pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre>そして、カスタム バインダーで次のようにします。<pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
