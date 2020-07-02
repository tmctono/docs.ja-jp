---
ms.openlocfilehash: eafbdd2d42977381fb4d77748a3c9a2595ff2936
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620375"
---
### <a name="xmlserializer-fails-while-serializing-a-type-that-hides-an-accessible-member-with-an-inaccessible-one"></a><span data-ttu-id="4d730-101">アクセス可能なメンバーを非表示にする型をアクセス不可のメンバーでシリアル化すると、XmlSerializer が失敗する</span><span class="sxs-lookup"><span data-stu-id="4d730-101">XmlSerializer fails while serializing a type that hides an accessible member with an inaccessible one</span></span>

#### <a name="details"></a><span data-ttu-id="4d730-102">説明</span><span class="sxs-lookup"><span data-stu-id="4d730-102">Details</span></span>

<span data-ttu-id="4d730-103">基本型で (パブリックなど) 以前はアクセス可能だった同じ名前のフィールドまたはプロパティを ("新しい" キーワードを使用して) 非表示にするアクセス不可のフィールドまたはプロパティが型に含まれている場合、派生型をシリアル化すると、<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4d730-103">When serializing a derived type, the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> can fail if the type contains an inaccessible field or property that hides (via the 'new' keyword) a field or property of the same name that was previously accessible (public, for example) on the base type.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4d730-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="4d730-104">Suggestion</span></span>

<span data-ttu-id="4d730-105">この問題は、新しい非表示メンバーを <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> にアクセスできるようにする (パブリックにするなど) ことで解決できます。または、次の構成設定で 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> の動作に戻します。これにより、問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="4d730-105">This problem can be solved by making the new, hiding member accessible to the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> (by marking it public, for example).Alternatively, the following config setting will revert to 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> behavior, which will fix the problem:</span></span><pre><code class="lang-xml">&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="4d730-106">名前</span><span class="sxs-lookup"><span data-stu-id="4d730-106">Name</span></span>    | <span data-ttu-id="4d730-107">[値]</span><span class="sxs-lookup"><span data-stu-id="4d730-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4d730-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="4d730-108">Scope</span></span>   |<span data-ttu-id="4d730-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="4d730-109">Minor</span></span>|
|<span data-ttu-id="4d730-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="4d730-110">Version</span></span>|<span data-ttu-id="4d730-111">4.5</span><span class="sxs-lookup"><span data-stu-id="4d730-111">4.5</span></span>|
|<span data-ttu-id="4d730-112">種類</span><span class="sxs-lookup"><span data-stu-id="4d730-112">Type</span></span>|<span data-ttu-id="4d730-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="4d730-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4d730-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="4d730-114">Affected APIs</span></span>

-<xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)?displayProperty=nameWithType></li></ul>|
