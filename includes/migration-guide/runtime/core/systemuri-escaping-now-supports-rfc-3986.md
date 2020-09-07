---
ms.openlocfilehash: e7001fcfdf88fd9e710fbb702f2ed39d63b1e080
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496678"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a><span data-ttu-id="0844d-101">System.Uri エスケープで RFC 3986 がサポート対象に</span><span class="sxs-lookup"><span data-stu-id="0844d-101">System.Uri escaping now supports RFC 3986</span></span>

#### <a name="details"></a><span data-ttu-id="0844d-102">説明</span><span class="sxs-lookup"><span data-stu-id="0844d-102">Details</span></span>

<span data-ttu-id="0844d-103">URI エスケープは、.NET Framework 4.5 で、[RFC 3986](https://tools.ietf.org/html/rfc3986) をサポートするように変更されました。</span><span class="sxs-lookup"><span data-stu-id="0844d-103">URI escaping has changed in .NET Framework 4.5 to support [RFC 3986](https://tools.ietf.org/html/rfc3986).</span></span> <span data-ttu-id="0844d-104">具体的な変更内容:</span><span class="sxs-lookup"><span data-stu-id="0844d-104">Specific changes include:</span></span><ul><li><span data-ttu-id="0844d-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> は、予約されている文字を RFC 3986 に基づいてエスケープします。</span><span class="sxs-lookup"><span data-stu-id="0844d-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> escapes reserved characters based on RFC 3986.</span></span></li><li><span data-ttu-id="0844d-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> は、予約されている文字をエスケープしません。</span><span class="sxs-lookup"><span data-stu-id="0844d-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> does not escape reserved characters.</span></span></li><li><span data-ttu-id="0844d-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> は、無効なエスケープ シーケンスが発生した場合に例外をスローしません。</span><span class="sxs-lookup"><span data-stu-id="0844d-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> does not throw an exception if it encounters an invalid escape sequence.</span></span></li><li><span data-ttu-id="0844d-108">予約されていないエスケープ文字はエスケープ解除されます。</span><span class="sxs-lookup"><span data-stu-id="0844d-108">Unreserved escaped characters are un-escaped.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="0844d-109">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0844d-109">Suggestion</span></span>

<ul><li><span data-ttu-id="0844d-110">無効なエスケープ シーケンスの場合、<xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> のスローに依存しないように、アプリケーションを更新します。</span><span class="sxs-lookup"><span data-stu-id="0844d-110">Update applications to not rely on <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> to throw in the case of an invalid escape sequence.</span></span> <span data-ttu-id="0844d-111">このようなシーケンスは、直接削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0844d-111">Such sequences must be detected directly now.</span></span></li><li><span data-ttu-id="0844d-112">同様に、エスケープおよびエスケープ解除された URI とデータ文字列は、.NET Framework 4.0 と .NET Framework 4.5 で異なる場合があるため、.NET のバージョン間で直接比較しないでください。</span><span class="sxs-lookup"><span data-stu-id="0844d-112">Similarly, expect that Escaped and Unescaped URI and Data strings may vary from .NET Framework 4.0 and .NET Framework 4.5 and should not be compared across .NET versions directly.</span></span> <span data-ttu-id="0844d-113">代わりに、1 つの .NET バージョンで解析と正規化を行ってから比較してください。</span><span class="sxs-lookup"><span data-stu-id="0844d-113">Instead, they should be parsed and normalized in a single .NET version before any comparisons are made.</span></span></li></ul>

| <span data-ttu-id="0844d-114">名前</span><span class="sxs-lookup"><span data-stu-id="0844d-114">Name</span></span>    | <span data-ttu-id="0844d-115">[値]</span><span class="sxs-lookup"><span data-stu-id="0844d-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0844d-116">スコープ</span><span class="sxs-lookup"><span data-stu-id="0844d-116">Scope</span></span>   |<span data-ttu-id="0844d-117">マイナー</span><span class="sxs-lookup"><span data-stu-id="0844d-117">Minor</span></span>|
|<span data-ttu-id="0844d-118">バージョン</span><span class="sxs-lookup"><span data-stu-id="0844d-118">Version</span></span>|<span data-ttu-id="0844d-119">4.5</span><span class="sxs-lookup"><span data-stu-id="0844d-119">4.5</span></span>|
|<span data-ttu-id="0844d-120">種類</span><span class="sxs-lookup"><span data-stu-id="0844d-120">Type</span></span>|<span data-ttu-id="0844d-121">ランタイム</span><span class="sxs-lookup"><span data-stu-id="0844d-121">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0844d-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="0844d-122">Affected APIs</span></span>

- <xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.EscapeDataString(System.String)`
- `M:System.Uri.EscapeUriString(System.String)`
- `M:System.Uri.UnescapeDataString(System.String)`

-->
