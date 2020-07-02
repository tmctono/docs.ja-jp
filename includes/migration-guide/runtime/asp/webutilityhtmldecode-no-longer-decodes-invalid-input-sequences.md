---
ms.openlocfilehash: 0b7d6d9543035ab0a8fdda675ae71572ace12a1f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620163"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a><span data-ttu-id="fe30f-101">WebUtility.HtmlDecode が無効な入力シーケンスをデコードしなくなった</span><span class="sxs-lookup"><span data-stu-id="fe30f-101">WebUtility.HtmlDecode no longer decodes invalid input sequences</span></span>

#### <a name="details"></a><span data-ttu-id="fe30f-102">説明</span><span class="sxs-lookup"><span data-stu-id="fe30f-102">Details</span></span>

<span data-ttu-id="fe30f-103">既定では、デコード メソッドによって無効な入力シーケンスが無効な UTF-16 文字列にデコードされることがなくなりました。</span><span class="sxs-lookup"><span data-stu-id="fe30f-103">By default, decoding methods no longer decode an invalid input sequence into an invalid UTF-16 string.</span></span> <span data-ttu-id="fe30f-104">代わりに、元の入力が返されます。</span><span class="sxs-lookup"><span data-stu-id="fe30f-104">Instead, they return the original input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fe30f-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="fe30f-105">Suggestion</span></span>

<span data-ttu-id="fe30f-106">デコーダーの出力の変更は、UTF-16 データではなくバイナリ データを文字列に格納した場合にのみ影響があります。</span><span class="sxs-lookup"><span data-stu-id="fe30f-106">The change in decoder output should matter only if you store binary data instead of UTF-16 data in strings.</span></span> <span data-ttu-id="fe30f-107">明示的にこの動作を制御するには、[appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) 要素の <code>aspnet:AllowRelaxedUnicodeDecoding</code> 属性を <code>true</code> に設定して従来の動作を有効にするか、<code>false</code> に設定して現在の動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fe30f-107">To explicitly control this behavior, set the <code>aspnet:AllowRelaxedUnicodeDecoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) element to <code>true</code> to enable legacy behavior or to <code>false</code> to enable the current behavior.</span></span>

| <span data-ttu-id="fe30f-108">名前</span><span class="sxs-lookup"><span data-stu-id="fe30f-108">Name</span></span>    | <span data-ttu-id="fe30f-109">[値]</span><span class="sxs-lookup"><span data-stu-id="fe30f-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fe30f-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="fe30f-110">Scope</span></span>   |<span data-ttu-id="fe30f-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="fe30f-111">Minor</span></span>|
|<span data-ttu-id="fe30f-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="fe30f-112">Version</span></span>|<span data-ttu-id="fe30f-113">4.5</span><span class="sxs-lookup"><span data-stu-id="fe30f-113">4.5</span></span>|
|<span data-ttu-id="fe30f-114">種類</span><span class="sxs-lookup"><span data-stu-id="fe30f-114">Type</span></span>|<span data-ttu-id="fe30f-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="fe30f-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fe30f-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="fe30f-116">Affected APIs</span></span>

-<xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|
