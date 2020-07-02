---
ms.openlocfilehash: a8f51dfa1c82e3b166449d2432dfe8a9b96564b9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620199"
---
### <a name="blockingcollectionlttgttrytakefromany-does-not-throw-anymore"></a><span data-ttu-id="2fdf7-101">BlockingCollection&lt;T&gt;.TryTakeFromAny がスローしなくなった</span><span class="sxs-lookup"><span data-stu-id="2fdf7-101">BlockingCollection&lt;T&gt;.TryTakeFromAny does not throw anymore</span></span>

#### <a name="details"></a><span data-ttu-id="2fdf7-102">説明</span><span class="sxs-lookup"><span data-stu-id="2fdf7-102">Details</span></span>

<span data-ttu-id="2fdf7-103">入力コレクションの 1 つに完了のマークが付けられた場合、<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> -1 を返さず、<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)>例外をスローしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2fdf7-103">If one of the input collections is marked completed, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer returns -1 and <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer throws an exception.</span></span> <span data-ttu-id="2fdf7-104">この変更の結果、コレクションの 1 つが空であったり完了していても、他のコレクションに取得できる項目がある場合にコレクションで作業をすることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2fdf7-104">This change makes it possible to work with collections when one of the collections is either empty or completed, but the other collection still has items that can be retrieved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2fdf7-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2fdf7-105">Suggestion</span></span>

<span data-ttu-id="2fdf7-106">-1 を返す TryTakeFromAny またはスローする TakeFromAny が制御フロー目的で使用されていた場合、ブロッキング コレクションが完了する場合、そのようなコードは、その条件を検出するように <code>.Any(b =&gt; b.IsCompleted)</code> を使用するように変更される必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fdf7-106">If TryTakeFromAny returning -1 or TakeFromAny throwing were used for control-flow purposes in cases of a blocking collection being completed, such code should now be changed to use <code>.Any(b =&gt; b.IsCompleted)</code> to detect that condition.</span></span>

| <span data-ttu-id="2fdf7-107">名前</span><span class="sxs-lookup"><span data-stu-id="2fdf7-107">Name</span></span>    | <span data-ttu-id="2fdf7-108">[値]</span><span class="sxs-lookup"><span data-stu-id="2fdf7-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2fdf7-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="2fdf7-109">Scope</span></span>   |<span data-ttu-id="2fdf7-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="2fdf7-110">Minor</span></span>|
|<span data-ttu-id="2fdf7-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="2fdf7-111">Version</span></span>|<span data-ttu-id="2fdf7-112">4.5</span><span class="sxs-lookup"><span data-stu-id="2fdf7-112">4.5</span></span>|
|<span data-ttu-id="2fdf7-113">種類</span><span class="sxs-lookup"><span data-stu-id="2fdf7-113">Type</span></span>|<span data-ttu-id="2fdf7-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2fdf7-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2fdf7-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2fdf7-115">Affected APIs</span></span>

-<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li></ul>|
