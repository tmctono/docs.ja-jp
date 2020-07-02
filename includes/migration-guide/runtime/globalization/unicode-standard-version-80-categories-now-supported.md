---
ms.openlocfilehash: a20fad5f9c95e59c14ffd91f4921cf8bfab443cd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621188"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="ad083-101">Unicode 標準バージョン 8.0 のカテゴリのサポート開始</span><span class="sxs-lookup"><span data-stu-id="ad083-101">Unicode standard version 8.0 categories now supported</span></span>

#### <a name="details"></a><span data-ttu-id="ad083-102">説明</span><span class="sxs-lookup"><span data-stu-id="ad083-102">Details</span></span>

<span data-ttu-id="ad083-103">.NET Framework 4.6.2 で、Unicode データが Unicode 標準バージョン 6.3 からバージョン 8.0 にアップグレードされました。</span><span class="sxs-lookup"><span data-stu-id="ad083-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="ad083-104">.NET Framework 4.6.2 で Unicode 文字カテゴリを要求すると、いくつかの結果が以前の .NET Framework バージョンの結果と一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ad083-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="ad083-105">この変更は、主にチェロキーの音節、新タイ ロ文字の母音記号および声調記号に影響します。</span><span class="sxs-lookup"><span data-stu-id="ad083-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ad083-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ad083-106">Suggestion</span></span>

<span data-ttu-id="ad083-107">コードを確認し、ハードコーディングされた Unicode 文字カテゴリに依存するロジックを削除/変更します。</span><span class="sxs-lookup"><span data-stu-id="ad083-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>

| <span data-ttu-id="ad083-108">名前</span><span class="sxs-lookup"><span data-stu-id="ad083-108">Name</span></span>    | <span data-ttu-id="ad083-109">値</span><span class="sxs-lookup"><span data-stu-id="ad083-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ad083-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="ad083-110">Scope</span></span>   |<span data-ttu-id="ad083-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="ad083-111">Minor</span></span>|
|<span data-ttu-id="ad083-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="ad083-112">Version</span></span>|<span data-ttu-id="ad083-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="ad083-113">4.6.2</span></span>|
|<span data-ttu-id="ad083-114">種類</span><span class="sxs-lookup"><span data-stu-id="ad083-114">Type</span></span>|<span data-ttu-id="ad083-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="ad083-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ad083-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ad083-116">Affected APIs</span></span>

-<xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
