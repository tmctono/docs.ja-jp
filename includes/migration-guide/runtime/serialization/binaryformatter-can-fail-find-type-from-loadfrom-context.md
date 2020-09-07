---
ms.openlocfilehash: ccba3cf98a1ca9e199d9a48f00e254bf34b93f72
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496567"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a><span data-ttu-id="1c154-101">BinaryFormatter による LoadFrom コンテキストからの型の検索が失敗する場合がある</span><span class="sxs-lookup"><span data-stu-id="1c154-101">BinaryFormatter can fail to find type from LoadFrom context</span></span>

#### <a name="details"></a><span data-ttu-id="1c154-102">説明</span><span class="sxs-lookup"><span data-stu-id="1c154-102">Details</span></span>

<span data-ttu-id="1c154-103">.NET Framework 4.5 の時点で、<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> の複数の変更により、LoadFrom コンテキストに読み込まれた型の <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> を使った逆シリアル化に違いが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c154-103">As of .NET Framework 4.5, a number of <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> changes may cause differences in deserialization when using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> to deserialize types that had been loaded in the LoadFrom context.</span></span> <span data-ttu-id="1c154-104">これらの変更は <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> が型を読み込む新しい方法によるものであり、後で <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> がその型に逆シリアル化しようとするときに異なる動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="1c154-104">These changes are due to the new ways <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> now loads a type which causes different behavior when a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> attempts to deserialize to that type later on.</span></span> <span data-ttu-id="1c154-105">既定のシリアル化バインダーは LoadFrom コンテキストを自動的に検索しませんが、状況によっては XmlSerializer の以前の動作に基づいて機能する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c154-105">The default serialization binder does not automatically search the LoadFrom context, although it may have worked in some circumstances based on the old behavior of XmlSerializer.</span></span> <span data-ttu-id="1c154-106">変更のため、異なるコンテキストで読み込まれたアセンブリから型が読み込まれるときに、<xref:System.IO.FileNotFoundException?displayProperty=fullName> がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c154-106">Due to the changes, when a type is being loaded from an assembly loaded in a different context, a <xref:System.IO.FileNotFoundException?displayProperty=fullName> may be thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1c154-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="1c154-107">Suggestion</span></span>

<span data-ttu-id="1c154-108">この例外が発生する場合は、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> の <code>Binder</code> プロパティを、正しい型を検索するカスタム バインダーに設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1c154-108">If this exception is seen, the <code>Binder</code> property of the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> can be set to a custom binder that will find the correct type.</span></span><pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre><span data-ttu-id="1c154-109">そして、カスタム バインダーで次のようにします。</span><span class="sxs-lookup"><span data-stu-id="1c154-109">And then the custom binder:</span></span><pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="1c154-110">名前</span><span class="sxs-lookup"><span data-stu-id="1c154-110">Name</span></span>    | <span data-ttu-id="1c154-111">[値]</span><span class="sxs-lookup"><span data-stu-id="1c154-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1c154-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="1c154-112">Scope</span></span>   |<span data-ttu-id="1c154-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="1c154-113">Edge</span></span>|
|<span data-ttu-id="1c154-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="1c154-114">Version</span></span>|<span data-ttu-id="1c154-115">4.5</span><span class="sxs-lookup"><span data-stu-id="1c154-115">4.5</span></span>|
|<span data-ttu-id="1c154-116">種類</span><span class="sxs-lookup"><span data-stu-id="1c154-116">Type</span></span>|<span data-ttu-id="1c154-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="1c154-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1c154-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="1c154-118">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
