---
ms.openlocfilehash: 5a3370e71488e4f9d8d933b504d1d771c78e0385
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620380"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="6fbda-101">SoapFormatter は、ハッシュテーブルなどの順序付けられたコレクション オブジェクトを逆シリアル化できない</span><span class="sxs-lookup"><span data-stu-id="6fbda-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

#### <a name="details"></a><span data-ttu-id="6fbda-102">説明</span><span class="sxs-lookup"><span data-stu-id="6fbda-102">Details</span></span>

<span data-ttu-id="6fbda-103"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> は、特定のバージョンの .NET Framework でシリアル化されたオブジェクトが別のバージョンで正常に逆シリアル化されることを保証しません。</span><span class="sxs-lookup"><span data-stu-id="6fbda-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="6fbda-104">具体的には、(<xref:System.Collections.Hashtable?displayProperty=fullName> のような) 順序付けられたコレクションの中には、4.0 と 4.5 の間でメンバーが追加されたものがあり、このような種類のオブジェクトが .NET Framework 4.5 でシリアル化された場合、.NET Framework 4.0 では逆シリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="6fbda-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=fullName>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET Framework 4.0 if they were serialized with .NET Framework 4.5.</span></span> <span data-ttu-id="6fbda-105">シリアル化データのシリアル化と逆シリアル化の両方が同じバージョンの .NET Framework で行われた場合、問題は発生しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6fbda-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6fbda-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6fbda-106">Suggestion</span></span>

<span data-ttu-id="6fbda-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> のシリアル化は、.NET Framework の変更に対応できる <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> のシリアル化または <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbda-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> to be resilient to .NET Framework changes.</span></span>

| <span data-ttu-id="6fbda-108">名前</span><span class="sxs-lookup"><span data-stu-id="6fbda-108">Name</span></span>    | <span data-ttu-id="6fbda-109">[値]</span><span class="sxs-lookup"><span data-stu-id="6fbda-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6fbda-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="6fbda-110">Scope</span></span>   |<span data-ttu-id="6fbda-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="6fbda-111">Minor</span></span>|
|<span data-ttu-id="6fbda-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="6fbda-112">Version</span></span>|<span data-ttu-id="6fbda-113">4.5</span><span class="sxs-lookup"><span data-stu-id="6fbda-113">4.5</span></span>|
|<span data-ttu-id="6fbda-114">種類</span><span class="sxs-lookup"><span data-stu-id="6fbda-114">Type</span></span>|<span data-ttu-id="6fbda-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="6fbda-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6fbda-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="6fbda-116">Affected APIs</span></span>

-<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
