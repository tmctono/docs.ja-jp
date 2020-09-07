---
ms.openlocfilehash: 004e2d1883b631e88ab5e164b1120c3b081b7041
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496863"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="f523d-101">ConcurrentQueue&lt;T&gt;.TryPeek は、出力パラメーターを介して誤った null を返すことがあります</span><span class="sxs-lookup"><span data-stu-id="f523d-101">ConcurrentQueue&lt;T&gt;.TryPeek can return an erroneous null via its out parameter</span></span>

#### <a name="details"></a><span data-ttu-id="f523d-102">説明</span><span class="sxs-lookup"><span data-stu-id="f523d-102">Details</span></span>

<span data-ttu-id="f523d-103">一部のマルチ スレッド シナリオでは、<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> は true を返すことができますが、出力パラメーターに (正しいピーク値の代わりに) null 値を入れることがあります。</span><span class="sxs-lookup"><span data-stu-id="f523d-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f523d-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="f523d-104">Suggestion</span></span>

<span data-ttu-id="f523d-105">この問題は、.NET Framework 4.5.1 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="f523d-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="f523d-106">この Framework にアップグレードすると、問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="f523d-106">Upgrading to that Framework will solve the issue.</span></span>

| <span data-ttu-id="f523d-107">名前</span><span class="sxs-lookup"><span data-stu-id="f523d-107">Name</span></span>    | <span data-ttu-id="f523d-108">[値]</span><span class="sxs-lookup"><span data-stu-id="f523d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f523d-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="f523d-109">Scope</span></span>   |<span data-ttu-id="f523d-110">Major</span><span class="sxs-lookup"><span data-stu-id="f523d-110">Major</span></span>|
|<span data-ttu-id="f523d-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="f523d-111">Version</span></span>|<span data-ttu-id="f523d-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f523d-112">4.5</span></span>|
|<span data-ttu-id="f523d-113">種類</span><span class="sxs-lookup"><span data-stu-id="f523d-113">Type</span></span>|<span data-ttu-id="f523d-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="f523d-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f523d-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f523d-115">Affected APIs</span></span>

- <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.ConcurrentQueue`1.TryPeek(`0@)``

-->
