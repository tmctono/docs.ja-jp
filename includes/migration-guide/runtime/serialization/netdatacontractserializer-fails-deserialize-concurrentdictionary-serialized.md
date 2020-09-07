---
ms.openlocfilehash: 6c120f155660863ce5ae3cf5bd81ea858a68ef8d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496528"
---
### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a><span data-ttu-id="65796-101">異なる .NET バージョンでシリアル化された ConcurrentDictionary を NetDataContractSerializer で逆シリアル化できない</span><span class="sxs-lookup"><span data-stu-id="65796-101">NetDataContractSerializer fails to deserialize a ConcurrentDictionary serialized with a different .NET version</span></span>

#### <a name="details"></a><span data-ttu-id="65796-102">説明</span><span class="sxs-lookup"><span data-stu-id="65796-102">Details</span></span>

<span data-ttu-id="65796-103">設計上、<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> は、シリアル化と逆シリアル化の両方で、同一の CLR 型を共有する結果になる場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="65796-103">By design, the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="65796-104">したがって、あるバージョンの .NET Framework でシリアル化されたオブジェクトを別のバージョンで逆シリアル化することは保証されません。<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="65796-104">Therefore, it is not guaranteed that an object serialized with one version of the .NET Framework can be deserialized by a different version.<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName></span></span> <span data-ttu-id="65796-105">型は、.NET Framework 4.5 以前でシリアル化された場合、.NET Framework 4.5.1 以降では正しく逆シリアル化されないことがわかっています。</span><span class="sxs-lookup"><span data-stu-id="65796-105">is a type that is known to not to deserialize correctly if serialized with the .NET Framework 4.5 or earlier and deserialized with the .NET Framework 4.5.1 or later.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="65796-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="65796-106">Suggestion</span></span>

<span data-ttu-id="65796-107">この問題の考えられるいくつかの回避策を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="65796-107">There are a number of possible work-arounds for this issue:</span></span><ul><li><span data-ttu-id="65796-108">シリアル化するコンピューターをアップグレードして、.NET Framework 4.5.1 も使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="65796-108">Upgrade the serializing computer to use the .NET Framework 4.5.1, as well.</span></span></li><li><span data-ttu-id="65796-109">シリアル化と逆シリアル化の両方で CLT 型がまったく同じになることが想定されない場合は、<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> ではなく、<xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> を使用します。</span><span class="sxs-lookup"><span data-stu-id="65796-109">Use <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> instead of <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> as this does not expect the exact same CLR types at both serializing and deserializing ends.</span></span></li><li><span data-ttu-id="65796-110">この特定の 4.5-&gt;4.5.1 の問題は見られないため、<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> ではなく、<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> を使用します。</span><span class="sxs-lookup"><span data-stu-id="65796-110">Use <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> instead of <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> since it does not exhibit this particular 4.5-&gt;4.5.1 break.</span></span></li></ul>

| <span data-ttu-id="65796-111">名前</span><span class="sxs-lookup"><span data-stu-id="65796-111">Name</span></span>    | <span data-ttu-id="65796-112">[値]</span><span class="sxs-lookup"><span data-stu-id="65796-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65796-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="65796-113">Scope</span></span>   |<span data-ttu-id="65796-114">マイナー</span><span class="sxs-lookup"><span data-stu-id="65796-114">Minor</span></span>|
|<span data-ttu-id="65796-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="65796-115">Version</span></span>|<span data-ttu-id="65796-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="65796-116">4.5.1</span></span>|
|<span data-ttu-id="65796-117">種類</span><span class="sxs-lookup"><span data-stu-id="65796-117">Type</span></span>|<span data-ttu-id="65796-118">ランタイム</span><span class="sxs-lookup"><span data-stu-id="65796-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="65796-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="65796-119">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)`

-->
