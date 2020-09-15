---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617166"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a><span data-ttu-id="242d7-101">WebUtility.HtmlEncode と WebUtility.HtmlDecode で BMP が正常に往復する</span><span class="sxs-lookup"><span data-stu-id="242d7-101">WebUtility.HtmlEncode and WebUtility.HtmlDecode round-trip BMP correctly</span></span>

#### <a name="details"></a><span data-ttu-id="242d7-102">説明</span><span class="sxs-lookup"><span data-stu-id="242d7-102">Details</span></span>

<span data-ttu-id="242d7-103">.NET Framework 4.5 を対象とするアプリケーションの場合、基本多言語面 (BMP: Basic Multilingual Plane) の外部にある文字は、<xref:System.Net.WebUtility.HtmlDecode(System.String)> メソッドに渡されたときに正常に往復します。</span><span class="sxs-lookup"><span data-stu-id="242d7-103">For applications that target the .NET Framework 4.5, characters that are outside the Basic Multilingual Plane (BMP) round-trip correctly when they are passed to the <xref:System.Net.WebUtility.HtmlDecode(System.String)> methods.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="242d7-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="242d7-104">Suggestion</span></span>

<span data-ttu-id="242d7-105">この変更は現在のアプリケーションには影響を与えないはずですが、元の動作を復元するには、`<httpRuntime>` 要素の `targetFramework` 属性を "4.5" 以外の文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="242d7-105">This change should have no effect on current applications, but to restore the original behavior, set the `targetFramework` attribute of the `<httpRuntime>` element to a string other than "4.5".</span></span> <span data-ttu-id="242d7-106">また、.NET Framework の対象バージョンに関係なくこの動作を制御するために `unicodeEncodingConformance` 構成要素の `unicodeDecodingConformance` 属性と `<webUtility>` 属性を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="242d7-106">You can also set the `unicodeEncodingConformance` and `unicodeDecodingConformance` attributes of the `<webUtility>` configuration element to control this behavior independently of the targeted version of the .NET Framework.</span></span>

| <span data-ttu-id="242d7-107">名前</span><span class="sxs-lookup"><span data-stu-id="242d7-107">Name</span></span>    | <span data-ttu-id="242d7-108">[値]</span><span class="sxs-lookup"><span data-stu-id="242d7-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="242d7-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="242d7-109">Scope</span></span>   | <span data-ttu-id="242d7-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="242d7-110">Edge</span></span>        |
| <span data-ttu-id="242d7-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="242d7-111">Version</span></span> | <span data-ttu-id="242d7-112">4.5</span><span class="sxs-lookup"><span data-stu-id="242d7-112">4.5</span></span>         |
| <span data-ttu-id="242d7-113">種類</span><span class="sxs-lookup"><span data-stu-id="242d7-113">Type</span></span>    | <span data-ttu-id="242d7-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="242d7-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="242d7-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="242d7-115">Affected APIs</span></span>

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
