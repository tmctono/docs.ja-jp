---
ms.openlocfilehash: 277a91fbfbf0c6aaaa0dc044ef0c079ad8607699
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497522"
---
### <a name="blockingcollectionlttgttrytakefromany-does-not-throw-anymore"></a><span data-ttu-id="aee2c-101">BlockingCollection&lt;T&gt;.TryTakeFromAny がスローしなくなった</span><span class="sxs-lookup"><span data-stu-id="aee2c-101">BlockingCollection&lt;T&gt;.TryTakeFromAny does not throw anymore</span></span>

#### <a name="details"></a><span data-ttu-id="aee2c-102">説明</span><span class="sxs-lookup"><span data-stu-id="aee2c-102">Details</span></span>

<span data-ttu-id="aee2c-103">入力コレクションの 1 つに完了のマークが付けられた場合、<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> -1 を返さず、<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)>例外をスローしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="aee2c-103">If one of the input collections is marked completed, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer returns -1 and <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer throws an exception.</span></span> <span data-ttu-id="aee2c-104">この変更の結果、コレクションの 1 つが空であったり完了していても、他のコレクションに取得できる項目がある場合にコレクションで作業をすることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="aee2c-104">This change makes it possible to work with collections when one of the collections is either empty or completed, but the other collection still has items that can be retrieved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="aee2c-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="aee2c-105">Suggestion</span></span>

<span data-ttu-id="aee2c-106">-1 を返す TryTakeFromAny またはスローする TakeFromAny が制御フロー目的で使用されていた場合、ブロッキング コレクションが完了する場合、そのようなコードは、その条件を検出するように <code>.Any(b =&gt; b.IsCompleted)</code> を使用するように変更される必要があります。</span><span class="sxs-lookup"><span data-stu-id="aee2c-106">If TryTakeFromAny returning -1 or TakeFromAny throwing were used for control-flow purposes in cases of a blocking collection being completed, such code should now be changed to use <code>.Any(b =&gt; b.IsCompleted)</code> to detect that condition.</span></span>

| <span data-ttu-id="aee2c-107">名前</span><span class="sxs-lookup"><span data-stu-id="aee2c-107">Name</span></span>    | <span data-ttu-id="aee2c-108">[値]</span><span class="sxs-lookup"><span data-stu-id="aee2c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="aee2c-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="aee2c-109">Scope</span></span>   |<span data-ttu-id="aee2c-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="aee2c-110">Minor</span></span>|
|<span data-ttu-id="aee2c-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="aee2c-111">Version</span></span>|<span data-ttu-id="aee2c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="aee2c-112">4.5</span></span>|
|<span data-ttu-id="aee2c-113">種類</span><span class="sxs-lookup"><span data-stu-id="aee2c-113">Type</span></span>|<span data-ttu-id="aee2c-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="aee2c-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="aee2c-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="aee2c-115">Affected APIs</span></span>

- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Threading.CancellationToken)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Int32)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``

-->
