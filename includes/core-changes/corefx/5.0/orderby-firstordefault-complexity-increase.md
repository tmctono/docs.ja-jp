---
ms.openlocfilehash: 950c69199219cca615e403c6515239de8864d35d
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137485"
---
### <a name="complexity-of-linq-orderbyfirstordefault-increased"></a><span data-ttu-id="3ac8b-101">LINQ OrderBy.First{OrDefault} の複雑さが増大</span><span class="sxs-lookup"><span data-stu-id="3ac8b-101">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>

<span data-ttu-id="3ac8b-102"><xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> と <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> の実装が変更され、その結果として操作の複雑さが増大します。</span><span class="sxs-lookup"><span data-stu-id="3ac8b-102">The implementation of <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> and <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> has changed, resulting in increased complexity for the operation.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3ac8b-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="3ac8b-103">Change description</span></span>

<span data-ttu-id="3ac8b-104">.NET Core 1.x - 3.x では、<xref:System.Linq.Enumerable.OrderBy%2A> または <xref:System.Linq.Enumerable.OrderByDescending%2A> に続けて、<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> または <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> を呼び出した場合、`O(N)` の複雑さで動作します。</span><span class="sxs-lookup"><span data-stu-id="3ac8b-104">In .NET Core 1.x - 3.x, calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N)` complexity.</span></span> <span data-ttu-id="3ac8b-105">最初の (または既定の) 要素のみが必要であるため、それを検索するのに必要な列挙は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="3ac8b-105">Since only the first (or default) element is required, only one enumeration is required to find it.</span></span> <span data-ttu-id="3ac8b-106">ただし、<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> または <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> に指定された述語は厳密には `N` 回呼び出されます。ここで、`N` はシーケンスの長さです。</span><span class="sxs-lookup"><span data-stu-id="3ac8b-106">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> is invoked exactly `N` times, where `N` is the length of the sequence.</span></span>

<span data-ttu-id="3ac8b-107">.NET 5.0 以降のバージョンでは、次のような[変更が加えられました](https://github.com/dotnet/runtime/pull/36643): <xref:System.Linq.Enumerable.OrderBy%2A> または <xref:System.Linq.Enumerable.OrderByDescending%2A> の後に <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> または <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> を呼び出すと、`O(N)` の複雑さではなく `O(N log N)` の複雑さで動作します。</span><span class="sxs-lookup"><span data-stu-id="3ac8b-107">In .NET 5.0 and later versions, a [change was made](https://github.com/dotnet/runtime/pull/36643) such that calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N log N)` complexity instead of `O(N)` complexity.</span></span> <span data-ttu-id="3ac8b-108">ただし、<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> または <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> に指定された述語の呼び出し回数は、`N` 回より "*少なく*" することができます。これは、全体的なパフォーマンスにとって重要なことです。</span><span class="sxs-lookup"><span data-stu-id="3ac8b-108">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> may be invoked *less* than `N` times, which is more important for overall performance.</span></span>

> [!NOTE]
> <span data-ttu-id="3ac8b-109">この変更は、.NET Framework での操作の実装と複雑さに一致します。</span><span class="sxs-lookup"><span data-stu-id="3ac8b-109">This change matches the implementation and complexity of the operation in .NET Framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3ac8b-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="3ac8b-110">Reason for change</span></span>

<span data-ttu-id="3ac8b-111">述語を呼び出す回数を減らすことの利点は、全体的な複雑さが低いことより重要であるため、.NET Core 1.0 で導入された実装は元に戻されました。</span><span class="sxs-lookup"><span data-stu-id="3ac8b-111">The benefit of invoking the predicate fewer times outweighs a lower overall complexity, so the implementation that was introduced in .NET Core 1.0 was reverted.</span></span> <span data-ttu-id="3ac8b-112">詳細については、[こちらの dotnet、ランタイムに関する問題](https://github.com/dotnet/runtime/issues/31554)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac8b-112">For more information, see [this dotnet/runtime issue](https://github.com/dotnet/runtime/issues/31554).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3ac8b-113">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="3ac8b-113">Version introduced</span></span>

<span data-ttu-id="3ac8b-114">5.0</span><span class="sxs-lookup"><span data-stu-id="3ac8b-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3ac8b-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="3ac8b-115">Recommended action</span></span>

<span data-ttu-id="3ac8b-116">開発者側では、何も行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3ac8b-116">No action is required on the developer's part.</span></span>

#### <a name="category"></a><span data-ttu-id="3ac8b-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="3ac8b-117">Category</span></span>

<span data-ttu-id="3ac8b-118">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="3ac8b-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3ac8b-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="3ac8b-119">Affected APIs</span></span>

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->
