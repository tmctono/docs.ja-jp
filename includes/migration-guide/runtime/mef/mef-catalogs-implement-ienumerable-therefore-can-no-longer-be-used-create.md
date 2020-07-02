---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620340"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="ac799-101">MEF カタログは IEnumerable を実装するため、シリアライザーの作成には使用できなくなった</span><span class="sxs-lookup"><span data-stu-id="ac799-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="ac799-102">説明</span><span class="sxs-lookup"><span data-stu-id="ac799-102">Details</span></span>

<span data-ttu-id="ac799-103">.NET Framework 4.5 以降では、MEF カタログは IEnumerable を実装するため、シリアライザー (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> オブジェクト) の作成には使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ac799-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="ac799-104">MEF カタログをシリアル化しようとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="ac799-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ac799-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ac799-105">Suggestion</span></span>

<span data-ttu-id="ac799-106">シリアライザーの作成に MEF を使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ac799-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="ac799-107">名前</span><span class="sxs-lookup"><span data-stu-id="ac799-107">Name</span></span>    | <span data-ttu-id="ac799-108">[値]</span><span class="sxs-lookup"><span data-stu-id="ac799-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ac799-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="ac799-109">Scope</span></span>   |<span data-ttu-id="ac799-110">Major</span><span class="sxs-lookup"><span data-stu-id="ac799-110">Major</span></span>|
|<span data-ttu-id="ac799-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="ac799-111">Version</span></span>|<span data-ttu-id="ac799-112">4.5</span><span class="sxs-lookup"><span data-stu-id="ac799-112">4.5</span></span>|
|<span data-ttu-id="ac799-113">種類</span><span class="sxs-lookup"><span data-stu-id="ac799-113">Type</span></span>|<span data-ttu-id="ac799-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="ac799-114">Runtime</span></span>|
