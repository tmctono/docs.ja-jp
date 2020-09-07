---
ms.openlocfilehash: ed669364efe9dd8f57d831a3764dd3fc68cd5e05
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496182"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a><span data-ttu-id="e2c7d-101">ASP.NET 正しくないマルチパート処理により、フォーム データが失われる場合がある。</span><span class="sxs-lookup"><span data-stu-id="e2c7d-101">ASP.NET Incorrect multipart handling may result in lost form data.</span></span>

#### <a name="details"></a><span data-ttu-id="e2c7d-102">説明</span><span class="sxs-lookup"><span data-stu-id="e2c7d-102">Details</span></span>

<span data-ttu-id="e2c7d-103">.NET Framework 4.7.2 以前のバージョンをターゲットとするアプリケーションでは、ASP.Net でマルチパート境界の値が正しく解析されないために、要求の実行中にフォーム データが使用できなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2c7d-103">In applications that target .NET Framework 4.7.2 and earlier versions, ASP.Net might incorrectly parse multipart boundary values, resulting in form data being unavailable during request execution.</span></span> <span data-ttu-id="e2c7d-104">.NET Framework 4.8 以降のバージョンをターゲットとするアプリケーションではマルチパート データが正しく解析されるため、要求の実行中にフォーム値を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e2c7d-104">Applications that target .NET Framework 4.8 or later versions correctly parse multipart data, so form values are available during request execution.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e2c7d-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e2c7d-105">Suggestion</span></span>

<span data-ttu-id="e2c7d-106">.NET Framework 4.8 以降で実行されているアプリケーションで、Framework 4.8 以降をターゲットとする場合は、<code>targetFrameworkVersion</code> 要素を使用して、区切り記号を削除するように既定の動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="e2c7d-106">Starting with applications running on .NET Framework 4.8, when targeting .NET Framework 4.8 or later by using the <code>targetFrameworkVersion</code> element, the default behavior changes to strip delimiters.</span></span> <span data-ttu-id="e2c7d-107">以前のフレームワークのバージョンをターゲットとするか、<code>targetFrameworkVersion</code> を使用しない場合、一部の値の末尾の区切り記号が引き続き返されます。この動作は、<code>appSetting</code> で明示的に制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2c7d-107">When targeting previous framework versions or not using <code>targetFrameworkVersion</code>, trailing delimiters for some values are still returned.This behavior can also be explicitly controlled with an <code>appSetting</code>:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="e2c7d-108">名前</span><span class="sxs-lookup"><span data-stu-id="e2c7d-108">Name</span></span>    | <span data-ttu-id="e2c7d-109">[値]</span><span class="sxs-lookup"><span data-stu-id="e2c7d-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e2c7d-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="e2c7d-110">Scope</span></span>   |<span data-ttu-id="e2c7d-111">不明</span><span class="sxs-lookup"><span data-stu-id="e2c7d-111">Unknown</span></span>|
|<span data-ttu-id="e2c7d-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="e2c7d-112">Version</span></span>|<span data-ttu-id="e2c7d-113">4.8</span><span class="sxs-lookup"><span data-stu-id="e2c7d-113">4.8</span></span>|
|<span data-ttu-id="e2c7d-114">種類</span><span class="sxs-lookup"><span data-stu-id="e2c7d-114">Type</span></span>|<span data-ttu-id="e2c7d-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e2c7d-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e2c7d-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e2c7d-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.Form?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.Files?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.Form`
- `P:System.Web.HttpRequest.Files`
- `P:System.Web.HttpRequest.ContentEncoding`

-->
