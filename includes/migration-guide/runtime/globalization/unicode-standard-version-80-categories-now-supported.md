---
ms.openlocfilehash: f389a9e9bcf4ac1777db66731a085d74889c4a98
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496570"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="5e641-101">Unicode 標準バージョン 8.0 のカテゴリのサポート開始</span><span class="sxs-lookup"><span data-stu-id="5e641-101">Unicode standard version 8.0 categories now supported</span></span>

#### <a name="details"></a><span data-ttu-id="5e641-102">説明</span><span class="sxs-lookup"><span data-stu-id="5e641-102">Details</span></span>

<span data-ttu-id="5e641-103">.NET Framework 4.6.2 で、Unicode データが Unicode 標準バージョン 6.3 からバージョン 8.0 にアップグレードされました。</span><span class="sxs-lookup"><span data-stu-id="5e641-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="5e641-104">.NET Framework 4.6.2 で Unicode 文字カテゴリを要求すると、いくつかの結果が以前の .NET Framework バージョンの結果と一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e641-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="5e641-105">この変更は、主にチェロキーの音節、新タイ ロ文字の母音記号および声調記号に影響します。</span><span class="sxs-lookup"><span data-stu-id="5e641-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5e641-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="5e641-106">Suggestion</span></span>

<span data-ttu-id="5e641-107">コードを確認し、ハードコーディングされた Unicode 文字カテゴリに依存するロジックを削除/変更します。</span><span class="sxs-lookup"><span data-stu-id="5e641-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>

| <span data-ttu-id="5e641-108">名前</span><span class="sxs-lookup"><span data-stu-id="5e641-108">Name</span></span>    | <span data-ttu-id="5e641-109">値</span><span class="sxs-lookup"><span data-stu-id="5e641-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5e641-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="5e641-110">Scope</span></span>   |<span data-ttu-id="5e641-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="5e641-111">Minor</span></span>|
|<span data-ttu-id="5e641-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="5e641-112">Version</span></span>|<span data-ttu-id="5e641-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="5e641-113">4.6.2</span></span>|
|<span data-ttu-id="5e641-114">種類</span><span class="sxs-lookup"><span data-stu-id="5e641-114">Type</span></span>|<span data-ttu-id="5e641-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="5e641-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="5e641-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="5e641-116">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Char.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)`

-->
