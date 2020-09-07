---
ms.openlocfilehash: 6f22d6211ec9238fd1c7786643ca95db02bfca64
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496798"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="11096-101">MEF カタログは IEnumerable を実装するため、シリアライザーの作成には使用できなくなった</span><span class="sxs-lookup"><span data-stu-id="11096-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="11096-102">説明</span><span class="sxs-lookup"><span data-stu-id="11096-102">Details</span></span>

<span data-ttu-id="11096-103">.NET Framework 4.5 以降では、MEF カタログは IEnumerable を実装するため、シリアライザー (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> オブジェクト) の作成には使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="11096-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="11096-104">MEF カタログをシリアル化しようとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="11096-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="11096-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="11096-105">Suggestion</span></span>

<span data-ttu-id="11096-106">シリアライザーの作成に MEF を使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="11096-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="11096-107">名前</span><span class="sxs-lookup"><span data-stu-id="11096-107">Name</span></span>    | <span data-ttu-id="11096-108">[値]</span><span class="sxs-lookup"><span data-stu-id="11096-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="11096-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="11096-109">Scope</span></span>   |<span data-ttu-id="11096-110">Major</span><span class="sxs-lookup"><span data-stu-id="11096-110">Major</span></span>|
|<span data-ttu-id="11096-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="11096-111">Version</span></span>|<span data-ttu-id="11096-112">4.5</span><span class="sxs-lookup"><span data-stu-id="11096-112">4.5</span></span>|
|<span data-ttu-id="11096-113">種類</span><span class="sxs-lookup"><span data-stu-id="11096-113">Type</span></span>|<span data-ttu-id="11096-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="11096-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="11096-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="11096-115">Affected APIs</span></span>

<span data-ttu-id="11096-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="11096-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
