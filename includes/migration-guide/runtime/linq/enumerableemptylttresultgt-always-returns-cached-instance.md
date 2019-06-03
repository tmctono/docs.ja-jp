---
ms.openlocfilehash: c9efbefc2bce9e21f328680795e72b62bfcd5cbd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379647"
---
### <a name="enumerableemptytresult-always-returns-cached-instance"></a><span data-ttu-id="4b3ac-101">Enumerable.Empty\<TResult> は、常にキャッシュされたインスタンスを返します</span><span class="sxs-lookup"><span data-stu-id="4b3ac-101">Enumerable.Empty\<TResult> always returns cached instance</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4b3ac-102">説明</span><span class="sxs-lookup"><span data-stu-id="4b3ac-102">Details</span></span>|<span data-ttu-id="4b3ac-103">.NET Framework 4.5 以降では、<xref:System.Linq.Enumerable.Empty%60%601> は、常にキャッシュされた内部インスタンス <xref:System.Collections.Generic.IEnumerable%601> を返します。以前は、<xref:System.Linq.Enumerable.Empty%60%601> は、API が呼び出された時点で空の <xref:System.Collections.Generic.IEnumerable%601> をキャッシュしました。つまり、<xref:System.Linq.Enumerable.Empty%60%601> が迅速かつ同時に呼び出されるような条件では、API の別の呼び出しに対して、型の別のインスタンスが返される可能性がありました。</span><span class="sxs-lookup"><span data-stu-id="4b3ac-103">Beginning in .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> always returns a cached internal instance <xref:System.Collections.Generic.IEnumerable%601>.Previously, <xref:System.Linq.Enumerable.Empty%60%601> would cache an empty <xref:System.Collections.Generic.IEnumerable%601> at the time the API was called, meaning that in some conditions in which <xref:System.Linq.Enumerable.Empty%60%601> was called rapidly and concurrently, different instances of the type could be returned for different calls to the API.</span></span>|
|<span data-ttu-id="4b3ac-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="4b3ac-104">Suggestion</span></span>|<span data-ttu-id="4b3ac-105">以前の動作は非確定的なため、コードがそれに依存している可能性は低いです。</span><span class="sxs-lookup"><span data-stu-id="4b3ac-105">Because the previous behavior was non-deterministic, code is unlikely to depend on it.</span></span> <span data-ttu-id="4b3ac-106">ただし、ありそうにないことですが、空の列挙が比較され、ときには等しくないことが予期されている場合には、<xref:System.Linq.Enumerable.Empty%60%601> を使用する代わりに、明示的に空の配列を作成する (<code>new T[0]</code>) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b3ac-106">However, in the unlikely case that empty enumerables are being compared and expected to sometimes be unequal, explicit empty arrays should be created (<code>new T[0]</code>) instead of using <xref:System.Linq.Enumerable.Empty%60%601>.</span></span>|
|<span data-ttu-id="4b3ac-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="4b3ac-107">Scope</span></span>|<span data-ttu-id="4b3ac-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="4b3ac-108">Edge</span></span>|
|<span data-ttu-id="4b3ac-109">Version</span><span class="sxs-lookup"><span data-stu-id="4b3ac-109">Version</span></span>|<span data-ttu-id="4b3ac-110">4.5</span><span class="sxs-lookup"><span data-stu-id="4b3ac-110">4.5</span></span>|
|<span data-ttu-id="4b3ac-111">型</span><span class="sxs-lookup"><span data-stu-id="4b3ac-111">Type</span></span>|<span data-ttu-id="4b3ac-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="4b3ac-112">Runtime</span></span>|
|<span data-ttu-id="4b3ac-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="4b3ac-113">Affected APIs</span></span>|<ul><li><xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
