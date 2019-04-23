---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804395"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="a9874-101">ConcurrentQueue\<T>.TryPeek は、出力パラメーターを介して誤った null を返すことがあります</span><span class="sxs-lookup"><span data-stu-id="a9874-101">ConcurrentQueue\<T>.TryPeek can return an erroneous null via its out parameter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a9874-102">説明</span><span class="sxs-lookup"><span data-stu-id="a9874-102">Details</span></span>|<span data-ttu-id="a9874-103">一部のマルチ スレッド シナリオでは、<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> は true を返すことができますが、出力パラメーターに (正しいピーク値の代わりに) null 値を入れることがあります。</span><span class="sxs-lookup"><span data-stu-id="a9874-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>|
|<span data-ttu-id="a9874-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a9874-104">Suggestion</span></span>|<span data-ttu-id="a9874-105">この問題は、.NET Framework 4.5.1 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="a9874-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="a9874-106">この Framework にアップグレードすると、問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="a9874-106">Upgrading to that Framework will solve the issue.</span></span>|
|<span data-ttu-id="a9874-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="a9874-107">Scope</span></span>|<span data-ttu-id="a9874-108">Major</span><span class="sxs-lookup"><span data-stu-id="a9874-108">Major</span></span>|
|<span data-ttu-id="a9874-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="a9874-109">Version</span></span>|<span data-ttu-id="a9874-110">4.5</span><span class="sxs-lookup"><span data-stu-id="a9874-110">4.5</span></span>|
|<span data-ttu-id="a9874-111">型</span><span class="sxs-lookup"><span data-stu-id="a9874-111">Type</span></span>|<span data-ttu-id="a9874-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="a9874-112">Runtime</span></span>|
|<span data-ttu-id="a9874-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a9874-113">Affected APIs</span></span>|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
