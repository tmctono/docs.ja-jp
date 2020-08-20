---
ms.openlocfilehash: 950c69199219cca615e403c6515239de8864d35d
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137485"
---
### <a name="complexity-of-linq-orderbyfirstordefault-increased"></a>LINQ OrderBy.First{OrDefault} の複雑さが増大

<xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> と <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> の実装が変更され、その結果として操作の複雑さが増大します。

#### <a name="change-description"></a>変更の説明

.NET Core 1.x - 3.x では、<xref:System.Linq.Enumerable.OrderBy%2A> または <xref:System.Linq.Enumerable.OrderByDescending%2A> に続けて、<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> または <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> を呼び出した場合、`O(N)` の複雑さで動作します。 最初の (または既定の) 要素のみが必要であるため、それを検索するのに必要な列挙は 1 つのみです。 ただし、<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> または <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> に指定された述語は厳密には `N` 回呼び出されます。ここで、`N` はシーケンスの長さです。

.NET 5.0 以降のバージョンでは、次のような[変更が加えられました](https://github.com/dotnet/runtime/pull/36643): <xref:System.Linq.Enumerable.OrderBy%2A> または <xref:System.Linq.Enumerable.OrderByDescending%2A> の後に <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> または <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> を呼び出すと、`O(N)` の複雑さではなく `O(N log N)` の複雑さで動作します。 ただし、<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> または <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> に指定された述語の呼び出し回数は、`N` 回より "*少なく*" することができます。これは、全体的なパフォーマンスにとって重要なことです。

> [!NOTE]
> この変更は、.NET Framework での操作の実装と複雑さに一致します。

#### <a name="reason-for-change"></a>変更理由

述語を呼び出す回数を減らすことの利点は、全体的な複雑さが低いことより重要であるため、.NET Core 1.0 で導入された実装は元に戻されました。 詳細については、[こちらの dotnet、ランタイムに関する問題](https://github.com/dotnet/runtime/issues/31554)を参照してください。

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="recommended-action"></a>推奨アクション

開発者側では、何も行う必要はありません。

#### <a name="category"></a>カテゴリ

Core .NET ライブラリ

#### <a name="affected-apis"></a>影響を受ける API

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
