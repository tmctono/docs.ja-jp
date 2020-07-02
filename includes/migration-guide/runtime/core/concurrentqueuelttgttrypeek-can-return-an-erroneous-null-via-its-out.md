---
ms.openlocfilehash: 02a15f6b9c02002b60c568b9e1d871af49744092
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622047"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="59f81-101">ConcurrentQueue&lt;T&gt;.TryPeek は、出力パラメーターを介して誤った null を返すことがあります</span><span class="sxs-lookup"><span data-stu-id="59f81-101">ConcurrentQueue&lt;T&gt;.TryPeek can return an erroneous null via its out parameter</span></span>

#### <a name="details"></a><span data-ttu-id="59f81-102">説明</span><span class="sxs-lookup"><span data-stu-id="59f81-102">Details</span></span>

<span data-ttu-id="59f81-103">一部のマルチ スレッド シナリオでは、<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> は true を返すことができますが、出力パラメーターに (正しいピーク値の代わりに) null 値を入れることがあります。</span><span class="sxs-lookup"><span data-stu-id="59f81-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="59f81-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="59f81-104">Suggestion</span></span>

<span data-ttu-id="59f81-105">この問題は、.NET Framework 4.5.1 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="59f81-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="59f81-106">この Framework にアップグレードすると、問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="59f81-106">Upgrading to that Framework will solve the issue.</span></span>

| <span data-ttu-id="59f81-107">名前</span><span class="sxs-lookup"><span data-stu-id="59f81-107">Name</span></span>    | <span data-ttu-id="59f81-108">[値]</span><span class="sxs-lookup"><span data-stu-id="59f81-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="59f81-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="59f81-109">Scope</span></span>   |<span data-ttu-id="59f81-110">Major</span><span class="sxs-lookup"><span data-stu-id="59f81-110">Major</span></span>|
|<span data-ttu-id="59f81-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="59f81-111">Version</span></span>|<span data-ttu-id="59f81-112">4.5</span><span class="sxs-lookup"><span data-stu-id="59f81-112">4.5</span></span>|
|<span data-ttu-id="59f81-113">種類</span><span class="sxs-lookup"><span data-stu-id="59f81-113">Type</span></span>|<span data-ttu-id="59f81-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="59f81-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="59f81-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="59f81-115">Affected APIs</span></span>

-<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
