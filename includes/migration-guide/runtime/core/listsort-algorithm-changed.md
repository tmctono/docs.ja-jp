---
ms.openlocfilehash: 09bd2c6312493f8b6369d05d8f1c4e88e4c05ece
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496382"
---
### <a name="listsort-algorithm-changed"></a><span data-ttu-id="79b5f-101">List.Sort アルゴリズムが変更された</span><span class="sxs-lookup"><span data-stu-id="79b5f-101">List.Sort algorithm changed</span></span>

#### <a name="details"></a><span data-ttu-id="79b5f-102">説明</span><span class="sxs-lookup"><span data-stu-id="79b5f-102">Details</span></span>

<span data-ttu-id="79b5f-103">.NET Framework 4.5 以降では、<xref:System.Collections.Generic.List%601?displayProperty=fullName> の並べ替えアルゴリズムが (クイック並べ替えではなく、内省的な並べ替えになるように) 変更されました。</span><span class="sxs-lookup"><span data-stu-id="79b5f-103">Beginning in .NET Framework 4.5, <xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort algorithm has changed (to be an introspective sort instead of a quick sort).</span></span> <span data-ttu-id="79b5f-104"><xref:System.Collections.Generic.List%601?displayProperty=fullName> の並べ替えは安定しますが、この変更により、さまざまなシナリオが不安定な方法で並べ替えられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79b5f-104"><xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort has never been stable, but this change may cause different scenarios to sort in unstable ways.</span></span> <span data-ttu-id="79b5f-105">これは単に、同等の項目が API の後続の呼び出しで異なる順序で並べ替えられる可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="79b5f-105">That simply means that equivalent items may sort in different orders in subsequent calls of the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="79b5f-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="79b5f-106">Suggestion</span></span>

<span data-ttu-id="79b5f-107">以前の並べ替えアルゴリズムも不安定であるため (ただし、方法は若干異なる)、特定の順序で常に並べ替える同等の項目に依存するコードがあってはなりません。</span><span class="sxs-lookup"><span data-stu-id="79b5f-107">Because the old sort algorithm was also unstable (though in slightly different ways), there should be no code that depends on equivalent items always sorting in a particular order.</span></span> <span data-ttu-id="79b5f-108">それに依存していて、以前の動作で問題がないコードのインスタンスが存在する場合は、適切な順序で項目を決定論的に並べ替える比較子を使用するようにそのコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79b5f-108">If there are instances of code depending upon that and being lucky with the old behavior, that code should be updated to use a comparer that will deterministically sort the items in the desired order.</span></span>

| <span data-ttu-id="79b5f-109">名前</span><span class="sxs-lookup"><span data-stu-id="79b5f-109">Name</span></span>    | <span data-ttu-id="79b5f-110">[値]</span><span class="sxs-lookup"><span data-stu-id="79b5f-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="79b5f-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="79b5f-111">Scope</span></span>   |<span data-ttu-id="79b5f-112">透明</span><span class="sxs-lookup"><span data-stu-id="79b5f-112">Transparent</span></span>|
|<span data-ttu-id="79b5f-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="79b5f-113">Version</span></span>|<span data-ttu-id="79b5f-114">4.5</span><span class="sxs-lookup"><span data-stu-id="79b5f-114">4.5</span></span>|
|<span data-ttu-id="79b5f-115">種類</span><span class="sxs-lookup"><span data-stu-id="79b5f-115">Type</span></span>|<span data-ttu-id="79b5f-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="79b5f-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="79b5f-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="79b5f-117">Affected APIs</span></span>

- <xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Generic.List`1.Sort``
- ``M:System.Collections.Generic.List`1.Sort(System.Collections.Generic.IComparer{`0})``
- ``M:System.Collections.Generic.List`1.Sort(System.Comparison{`0})``
- ``M:System.Collections.Generic.List`1.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{`0})``

-->
